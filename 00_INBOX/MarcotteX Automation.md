# Architecture d'Automatisation T1 : Cabinet Comptable
**Statut :** Conception Finale (Architecte Senior)
**Stack :** n8n + Odoo + JotForm + Azure + Twilio + Mailgun

---
## 1. Vision Globale
L'objectif est de transformer le processus T1 en un flux **"Pull"** automatisé : le système s'occupe de la chasse aux documents, et l'humain n'intervient dans **Odoo** que lorsque le dossier est complet et prêt pour la saisie.

### Principes Directeurs
- **Confidentialité :** Résidence des données au Canada (Loi 25).
- **Zéro Bruit :** Création de tâches Odoo uniquement pour les dossiers complets (soumissions finales).
- **Interactivité :** Relances multicanaux (Mailgun/Twilio) avec escalade et réponse intelligente.

---
## 2. La Stack Technologique

| Composante | Solution | Rôle |
| :--- | :--- | :--- |
| **Interface Client** | **JotForm** | Collecte de données et fichiers (Template Annuel). |
| **Orchestrateur** | **n8n (Self-hosted)** | Chef d'orchestre sur Azure Web App for Containers (Canada East). |
| **SSOT & Gestion** | **Odoo** | CRM, Gestion des tâches (Tasks) et dossiers clients. |
| **Stockage Fichiers** | **Azure Blob Storage** | Hébergement des 2TB+ de fichiers à Montréal (Canada East). |
| **Emails** | **Mailgun** | Envoi transactionnel, suivi d'ouverture et gestion des bounces. |
| **SMS & Voix** | **Twilio** | SMS interactifs et appels IVR automatisés. |

---
## 3. Workflow de Relance (Escalade Multicanale)

L'orchestration est pilotée par n8n en mode **Stateless (Polling)** :

1. **Email Initial (T+0) via Mailgun :** Envoi du lien personnalisé (Tokenized Prefill sécurisé).
2. **Suivi Mailgun (T+2) :** n8n vérifie via l'API Mailgun si le mail a été "Opened". Si non, ajustement du canal possible.
3. **Rappel Email (T+4) via Mailgun :** Deuxième tentative si aucune tâche n'est créée dans Odoo.
4. **SMS Interactif (T+7) via Twilio :** Envoi avec lien court.
    - *Logique de réponse :* Si le client répond "AIDE", n8n déplace la tâche/statut dans Odoo vers "Bloqué - Aide requise" et notifie le préparateur.
5. **Appel Vocal IVR (T+10) via Twilio :**
    - *"Appuyez sur 1 pour parler à un adjoint"* -> Création d'une alerte prioritaire dans Odoo.
    - *"Appuyez sur 2 pour recevoir le lien par SMS"* -> Déclenche instantanément un nœud `Twilio SMS` via n8n.

---
## 4. Ingestion & Intégration (Le "Happy Path")

```mermaid
graph TD
  A[JotForm Webhook] --> B{n8n Orchestrator}
  B --> C[Download Files from JotForm]
  B --> D[Upload to Azure Blob Storage Montréal]
  D --> E[Create ir.attachment in Odoo]
  B --> F[Create Task in Odoo - Stage: Prêt pour saisie]
  E --> F
  F --> G[Purge JotForm Submission - Loi 25]
  ```  
## 5. Configuration Azure (Infrastructure MSP)

Cette section détaille les ressources à provisionner par la firme TI sur le tenant Azure existant pour assurer la conformité Loi 25 et la performance.

- **Région :** `Canada East (Québec)` pour la résidence de données locale.
- **Compute (n8n) :** - **Azure Web App for Containers** : Plan Linux (B1 ou B2).
	- Permet le déploiement de l'image Docker n8n officielle sans gestion d'OS par le MSP.
- **Base de Données :**
	- **Azure Database for PostgreSQL (Flexible Server)** : Pour la persistance des workflows et des historiques d'exécution.
- **Stockage (GED) :**
	- **Azure Blob Storage (V2)** : 
		- **Container Principal** : Stockage des documents fiscaux (2 TB+).
		- **Politique de cycle de vie (Lifecycle Management)** :
			- **Hot** : Documents de l'année courante (accès rapide).
			- **Cool** : Archivage automatique après 12 mois sans accès.
			- **Archive** : Stockage long terme (7 ans+) pour conformité fiscale.
- **Sécurité & Networking :**
	- **Private Endpoints** : Pour sécuriser les échanges entre Odoo, n8n et le Blob Storage hors internet public.
	- **Azure Key Vault** : Centralisation des secrets (API Keys Mailgun, Twilio, Odoo).

---

## 6. Maintenance & Évolutivité Annuelle

Stratégie de "Snapshot" annuel pour minimiser le code-drift et faciliter la transition entre les années fiscales.

- **Pattern "Golden Standard" :**
	1. Le cabinet clone le formulaire JotForm maître (Template) chaque mois de janvier.
	2. Mise à jour du champ caché `tax_year` dans JotForm (ex: `2024`).
	3. Le nom du formulaire doit suivre la convention : `T1_Workflow_{YEAR}`.
- **Discovery Dynamique n8n :**
	- Le workflow n8n n'utilise pas d'ID de formulaire hardcodé.
	- Il effectue un `GET /user/forms` via l'API JotForm pour trouver le `form_id` dont le titre correspond à l'année fiscale en cours.
- **Gestion des Environnements (ALM) :**
	- **Instance Staging** : Branchée sur un clone du formulaire et une base Odoo de test.
	- **Instance Prod** : Connectée via **Git (Source Control intégré)**.
	- Le déploiement se fait par un "Pull" Git sur l'instance de production après validation des tests en staging.
- **Surveillance (Monitoring) :**
	- Utilisation d'**UptimeRobot** ou Azure Monitor pour alerter le concepteur en cas d'arrêt de l'instance durant la période critique (mars-avril).

## 7. Configuration Requise sur Odoo

Pour permettre à n8n d'agir comme orchestrateur, certaines configurations spécifiques doivent être appliquées sur l'instance Odoo du cabinet.

### A. Accès API & Sécurité
- **Utilisateur Dédié (Bot) :** Créer un utilisateur nommé `n8n_automation`.
	- **Droits :** Accès en écriture sur les modules `Project` (pour les tâches) et `Documents` (pour la GED).
	- **Authentification :** Générer une **API Key** (Odoo v14+) au lieu d'utiliser le mot de passe de l'utilisateur.
- **Protocole :** S'assurer que le MSP a ouvert l'accès au endpoint `/xmlrpc/2/object`.

### B. Module de Stockage Azure (GED)
Pour que les 2 TB de fichiers soient réellement hébergés sur le Blob Storage Montréal :
- **Installation :** Installer le module `cloud_storage_azure` (ou équivalent communautaire certifié).
- **Paramétrage :** - `Azure Storage Connection String` : À récupérer depuis le Key Vault Azure.
	- `Container Name` : ex: `odoo-documents`.
- **Force Storage :** Configurer les types de documents (PDF, Images) pour qu'ils soient systématiquement poussés vers le stockage externe via le paramètre `ir.config_parameter` : `ir_attachment.location = 'remote'`.

### C. Structure du Projet T1 (Tasks)
- **ID de Projet :** Créer un projet maître `Impôts T1 {Année}`.
- **Stages (Étapes) :** Configurer les étapes suivantes pour le tracking n8n :
	1. `En attente client` (Statut par défaut).
	2. `Bloqué - Aide requise` (Cible des relances interactives).
	3. `Dossier Complet / Prêt` (Cible du webhook de soumission JotForm).
	4. `En cours de saisie`.
	5. `Révision / Finalisé`.

### D. Champs Personnalisés (Optional mais recommandé)
Pour l'intégrité du workflow, ajouter ces champs sur l'objet `project.task` :
- `x_jotform_submission_id` : Pour éviter les doublons et permettre la traçabilité.
- `x_tax_year` : Année fiscale liée à la tâche.
- `x_last_contact_date` : Date de la dernière relance effectuée par n8n (utile pour les rapports de performance).

### E. Configuration du Chatter (Notifications)
- S'assurer que l'utilisateur `n8n_automation` est abonné aux tâches créées.
- Toute interaction (Client qui demande de l'aide via SMS/Voix) doit être poussée par n8n comme une **Note Interne** dans le Chatter pour garantir l'historique de communication.
- 
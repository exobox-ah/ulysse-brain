 MarcotteX Automation  
## Architecture d’Automatisation T1 – Cabinet Comptable

**Statut** : Conception finale  
**Rôle** : Document d’architecture de solutions (niveau architecte senior)  
**Stack principale** : n8n (self‑hosted) + Odoo + JotForm + Azure + Twilio + Mailgun  

---

## 1. Vision et principes

### 1.1 Vision globale

L’objectif est de transformer le processus T1 en un flux **pull** où le système orchestre la chasse aux documents et aux données et où les humains interviennent uniquement lorsque le dossier est complet et prêt pour la saisie dans Odoo. Le système coordonne la collecte d’informations, les relances multicanales et la gestion des états de dossier pour maximiser le taux de complétion tout en réduisant le bruit opérationnel[web:6][web:16].

### 1.2 Principes directeurs

- **Confidentialité & conformité**  
  - Résidence des données dans des régions canadiennes (Azure Canada East, stockage au Canada) pour répondre aux exigences de la Loi 25, tout en documentant les risques liés à la juridiction de fournisseurs étrangers (CLOUD Act, FISA)[web:3][web:5].
  - Évaluation des facteurs relatifs à la vie privée (AIPD) spécifique au projet T1, incluant les transferts vers Mailgun, Twilio, JotForm et tout autre sous‑traitant[web:2][web:4][web:14].

- **Zéro bruit opérationnel**  
  - Création de tâches de préparation dans Odoo uniquement lorsque le dossier répond aux critères de “dossier complet” définis par des règles métier explicites.
  - Les états intermédiaires sont visibles à la demande (consultation dossier) mais ne déclenchent pas de travail non planifié.

- **Interactivité intelligente**  
  - Relances multicanales combinant emails, SMS et appels IVR avec logique de branchement (consentement, préférences, historique de réaction).
  - Réponses intelligentes “AIDE” / “STOP” / demandes spécifiques rebasculant le dossier vers des flux dédiés (aide humaine, désinscription, papier, etc.).

- **Observabilité & gouvernance**  
  - Journaux techniques (workflows, erreurs, retries) et journaux métier (qui a reçu quoi, quand, et pourquoi) centralisés et corrélables.
  - Gestion des rôles, droits d’accès et audit pour n8n et Odoo.

---

## 2. Stack technologique et rôles

### 2.1 Composants principaux

| Composante         | Solution                     | Rôle                                                                                  |
|--------------------|-----------------------------|---------------------------------------------------------------------------------------|
| Interface client   | JotForm                     | Collecte de données structurées et fichiers, formulaires T1 annuels[web:13]           |
| Orchestrateur      | n8n (self‑hosted)           | Chef d’orchestre des workflows, relances, complétude, synchronisation Odoo[web:6]     |
| SSOT & gestion     | Odoo                        | CRM, gestion des dossiers T1, tâches, états et préférences clients[web:16]            |
| Stockage fichiers  | Azure Blob Storage          | Stockage des pièces justificatives, 2TB+ de documents, région Canada East.           |
| Infra d’exécution  | Azure (Web App / conteneurs)| Hébergement de n8n, DB, et composants auxiliaires au Canada.                         |
| Emails             | Mailgun                     | Envoi d’emails transactionnels, relances, suivi d’ouverture / clics[web:9]           |
| SMS & voix         | Twilio                      | SMS, réponses interactives, IVR pour escalade voix.                                  |

### 2.2 Contraintes de conformité et sous‑traitants

- Inventaire des sous‑traitants (Azure, Odoo hosting, n8n, Mailgun, Twilio, JotForm) avec :  
  - Finalité, catégorie de données, localisation des serveurs, garanties contractuelles[web:4][web:11].
  - Clauses de transferts transfrontaliers et mesures de sécurité (chiffrement, contrôle d’accès).
- Documentation explicite des risques résiduels liés au CLOUD Act / FISA, même avec résidence des données au Canada[web:3][web:5].

---

## 3. Architecture logique n8n / Odoo / Azure

### 3.1 n8n – modèle d’orchestration

- **Mode d’exécution et scalabilité**  
  - n8n déployé en mode “queue” avec un nœud maître (scheduler/API) et un ou plusieurs exécuteurs séparés pour absorber les pics de charge saisonniers T1[web:18].
  - Persistance via base de données (PostgreSQL ou équivalent) pour permettre la reprise de workflows longs et la gestion fiable des états[web:18].

- **Organisation des workflows**  
  - Workflow maître annuel : `T1_Orchestrator_YYYY` (gestion des campagnes, dates de déclenchement, policies globales).
  - Sous‑workflows spécialisés :  
    - `T1_Reminders_Multichannel` : logique de relance email/SMS/IVR[web:6].
    - `T1_Completeness_Evaluator` : calcul de complétude dossier.
    - `T1_Odoo_Sync` : synchronisation statuts/coordonnées Odoo[web:16].
    - `T1_Notifications_Internal` : notifications équipes internes (préparateurs, adjoints).
    - `T1_Error_Handler` : bus d’erreurs global.

### 3.2 Bus d’erreurs et observabilité

- Workflow dédié `T1_Error_Handler` recevant, via mécanismes d’erreurs n8n, les incidents de tous les workflows[web:6] :
  - Journalisation dans une table technique (Odoo ou DB séparée).
  - Classification (type d’erreur, système concerné, criticité).
  - Politique de retries avec backoff exponentiel pour les erreurs transitoires.
  - Notification (email / canal interne) pour les erreurs fonctionnelles ou récurrentes.

- Monitoring et logs :
  - Niveaux de logs configurés au niveau conteneur / App Service.
  - Dashboards pour : taux de complétion, taux d’erreurs, volumes de relances, temps moyen de complétion.

---

## 4. Modèle métier : cycle de vie d’un dossier T1

### 4.1 États de dossier (vue d’état)

Cycle de vie proposé (à implémenter dans Odoo et reflété dans n8n) :

- `Brouillon` : dossier créé, aucune action client.
- `Partiel – Client en progression` : formulaire entamé ou quelques pièces reçues, mais complétude insuffisante.
- `Complet – Prêt pour saisie` : règles de complétude respectées, création automatique de tâches de préparation.
- `En préparation` : équipe comptable en saisie.
- `En révision` : revue qualité interne.
- `Envoyé – En attente de signature` : déclaration transmise au client pour signature.
- `Clôturé` : T1 finalisé et archivé.

### 4.2 Règles de complétude

- **Définition formelle**
  - Par type de client (salarié, travailleur autonome, location, investissement, etc.), définir les listes minimales de pièces et champs JotForm obligatoires.
  - Intégrer des tolérances métier (ex. relevés secondaires manquants mais note explicative) dans un moteur de règles simple dans `T1_Completeness_Evaluator`.

- **Évaluateur de complétude (n8n)**
  - Lecture des métadonnées de fichiers sur Azure Blob (nom, type MIME, taille, tags).
  - Lecture des données structurées de JotForm (sections complétées, réponses clés)[web:13].
  - Calcul d’un “score de complétude” et détermination d’un état : `Partiel` ou `Complet`.

- **Relation avec Odoo**
  - Passage automatique à `Complet – Prêt pour saisie` déclenche :
    - Création de tâches Odoo pour les préparateurs[web:16].
    - Arrêt des relances clients.
  - État `Partiel – Client en progression` reste visible mais n’entraîne pas de tâche de production.

---

## 5. Workflow de relance multicanale

### 5.1 Séquence de base

Séquence standard (paramétrable par campagne) :

1. **Email initial (T+0)** via Mailgun
   - Envoi d’un lien personnalisé (prefill tokenisé et sécurisé) vers JotForm[web:9][web:13].
   - Contenu incluant contexte fiscal, identité du cabinet et lien vers politique de confidentialité Loi 25[web:4][web:11].

2. **Suivi ouverture email (T+2)**
   - Interrogation API Mailgun pour vérifier ouverture / clic[web:9].
   - Si aucune ouverture → marquer “non réactif email” dans un état interne.

3. **Rappel email (T+4)**
   - Deuxième envoi si aucune progression significative dans JotForm et aucun changement d’état dans Odoo.

4. **SMS interactif (T+7)** via Twilio
   - SMS avec lien court vers le formulaire ou la page de reprise.
   - Gestion de mots‑clés :
     - “AIDE” → statut Odoo `Bloqué – Aide requise` + notification à un adjoint.
     - “STOP” → désactivation des relances SMS pour ce dossier (journalisée dans Odoo)[web:6].

5. **Appel vocal IVR (T+10)** via Twilio
   - Message vocal avec options :
     - Touche 1 : parler à un adjoint → création d’alerte prioritaire dans Odoo.
     - Touche 2 : renvoi immédiat d’un SMS avec lien.

### 5.2 Intelligence de canal et préférences

- **Machine d’états de relance**
  - Stockage, pour chaque client / campagne, de :
    - Dernier canal utilisé, score de réactivité, consentement email/SMS/voix, préférences explicites[web:6].
  - Branches conditionnelles :
    - Si email ouvert mais aucun clic → prioriser SMS[web:1][web:9].
    - Si formulaire ouvert mais abandonné → email ou SMS de “récupération” proposant assistance[web:7].

- **Limitation de fréquence (anti‑spam)**
  - Règles globales : nombre maximum de messages / canal / saison.
  - Pause automatique si une plainte ou un ton négatif est détecté (via mot‑clé ou action interne).

- **Désinscription / opposition**
  - Lien de désinscription email mappé sur un champ “Restrictions de contact” dans Odoo, même si le message est transactionnel[web:1][web:4].
  - Gestion centralisée des “STOP SMS” et preuve de réception conservée.

---

## 6. Gestion des coordonnées, cas particuliers et surcharge

### 6.1 Mise à jour des coordonnées

- Synchronisation **bidirectionnelle** Odoo ↔ JotForm ↔ moteur de relance :
  - Si le client corrige son email ou téléphone dans le formulaire, n8n met à jour immédiatement Odoo et le contexte de campagne[web:13][web:16].
  - Les relances ultérieures utilisent les nouvelles coordonnées; les anciennes sont désactivées.

### 6.2 Cas particuliers

- **Clients “papier only / techno‑phobes”**
  - Segment Odoo (“Préférences : Papier/Téléphone”) qui bypass les messages digitaux et crée directement une tâche d’appel humain ou l’envoi d’un kit papier.

- **Situations sensibles**
  - Options spécifiques dans le formulaire (décès, divorce, changement de situation majeure) qui déclenchent un statut `Revue Humaine Obligatoire` et coupent les relances automatisées.

### 6.3 Gestion de la capacité (surcharge)

- Paramètre global de “throttle” côté orchestration :
  - Si le nombre de dossiers `Complet – Prêt pour saisie` dépasse une capacité donnée, ralentissement ou suspension des étapes tardives de relance (T+7, T+10) pour éviter de saturer l’équipe[web:18].

---

## 7. Sécurité, audit et environnements

### 7.1 n8n

- Sécurité et gouvernance :
  - RBAC activé, séparation des rôles (dev, ops, fonctionnel)[web:6][web:18].
  - Chiffrement des credentials et secrets (ex. Azure Key Vault ou équivalent).
  - Journalisation des changements de workflows (qui a modifié quoi, quand).

- Environnements et déploiement :
  - Environnement de staging pour tests complets (fake Mailgun/Twilio, sandbox Odoo)[web:6][web:12].
  - Versionnement Git des workflows (export JSON) et pipeline de déploiement vers la production.

### 7.2 Odoo

- Rôles et contrôle d’accès :
  - Profils distincts (préparateur, réviseur, adjoint, admin) avec visibilité limitée sur les pièces T1 et les statuts[web:16].
  - Restrictions sur qui peut changer les coordonnées clientes ou forcer un statut de dossier.

- Audit métier :
  - Journal complet des changements d’état de dossier (date, auteur, motif).
  - Journal des communications : emails/SMS/voix envoyés, canaux, résultats (ouvert, cliqué, réponse), utilisable en cas de plainte ou demande d’accès Loi 25[web:4][web:11].

### 7.3 Sauvegarde et restauration

- Sauvegardes régulières pour :
  - Base n8n, base Odoo, et conteneurs de Blob Storage.
  - Tests périodiques de restauration, en particulier avant la haute saison T1[web:18].

---

## 8. UX client, consentement et Loi 25

### 8.1 Formulaire JotForm

- Bloc de consentement spécifique Loi 25 :
  - Finalités de collecte (préparation T1), catégories de données, localisation des données (Canada), mention des principaux sous‑traitants[web:4][web:14].
  - Informations sur les droits d’accès, de rectification et de retrait du consentement[web:4][web:11].

- Ergonomie :
  - Sauvegarde et reprise de session (lien de reprise envoyé par email/SMS)[web:7][web:13].
  - Sections claires par type de revenu/situation, avec logique conditionnelle pour réduire le bruit.

### 8.2 Contenu des messages

- Rappel systématique du contexte :
  - “Vous recevez ce message dans le cadre de la préparation de votre déclaration T1 avec [Nom du cabinet].”[web:1][web:11]
- Option d’escalade humaine disponible à chaque étape :
  - Lien ou mot‑clé “AIDE” pour sortir du flux automatisé et passer à l’assistance.

---

## 9. Vue des flux de données (résumé)

### 9.1 Flux principaux

- Client → JotForm : données personnelles et fiscales, pièces justificatives[web:13].
- JotForm → n8n : webhook avec réponses et fichiers (ou liens de fichiers)[web:13].
- n8n → Azure Blob : stockage organisé (par client, par année, par type de pièce).
- n8n ↔ Odoo : synchronisation des clients, coordonnées, statuts de dossier, tâches[web:16].
- n8n → Mailgun : déclenchement d’emails, suivi d’ouverture et de clics[web:9].
- n8n → Twilio : envoi de SMS et appels IVR, réception des réponses (AIDE/STOP).
- n8n → équipes internes : notifications email/canal interne en cas de blocage, erreurs ou demandes d’aide.

### 9.2 Documentation de conformité

- Tableau (hors de ce document) listant pour chaque flux :
  - Données, finalité, base légale, localisation, sous‑traitant, durée de conservation[web:4][web:11].

---
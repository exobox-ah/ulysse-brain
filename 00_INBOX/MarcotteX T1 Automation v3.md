# MarcotteX Automation V3 : Architecture T1 Cabinet Comptable
**Statut :** Architecture Validée (V3)
**Rôle :** Document de référence technique & conformité
**Stack :** JotForm (Ent.) + Azure Functions (C#) + n8n + Odoo + Azure Blob

---

## 1. Vision et Principes Directeurs
L'objectif est de transformer le processus T1 en un flux **"Pull"** automatisé. Le système orchestre la chasse aux documents, et l'humain n'intervient dans **Odoo** que lorsque le dossier est **100% complet** et validé par le middleware.

### 1.1 Principes de Conformité (Loi 25 & Gouvernance)
- **Souveraineté des Données :** Utilisation de **JotForm Enterprise** (Serveur dédié Montréal) pour la production, garantissant que les données (y compris les brouillons "Save & Continue") ne quittent jamais le Canada.
- **Stratégie de Développement (Risk Mitigation) :** Développement initial sur JotForm Gold (US) avec données fictives, bascule vers Enterprise pour le "Go Live".
- **Documentation des Risques :** Reconnaissance explicite des risques CLOUD Act/FISA dans l'ÉFVP, mitigés par le chiffrement au repos et la juridiction contractuelle canadienne.

### 1.2 Principes d'Architecture (Le "Router Pattern")
- **Anti-Corruption Layer (ACL) :** L'orchestrateur C# (Azure Function) agit comme un pare-feu logique. Il ne laisse entrer dans le système interne (n8n/Odoo) que des données nettoyées, validées et structurées.
- **Micro-Workflows :** n8n n'est plus un monolithe décisionnel, mais une collection de "travailleurs spécialisés" (Micro-services) déclenchés par le C#.
- **Zéro Bruit :** Aucune tâche n'est créée dans Odoo tant que le middleware C# n'a pas validé la complétude du dossier (Règles métier strictes).

---

## 2. La Stack Technologique V3

| Composante | Technologie | Rôle & Responsabilité |
| :--- | :--- | :--- |
| **Front-End** | **JotForm Enterprise** | Interface client, logique d'affichage conditionnelle, upload fichiers. Hébergement Canada (Montréal). |
| **Middleware** | **Azure Functions (C#)** | **Le Cerveau.** Validation HMAC, nettoyage données, décision de routage. |
| **Orchestrateur** | **n8n (Self-hosted)** | **Les Bras.** Exécution des appels API (Odoo, Twilio, Mailgun) sur ordre du C#. |
| **Core Business** | **Odoo v17+** | CRM, Gestion des tâches, "Single Source of Truth". |
| **Stockage** | **Azure Blob Storage** | "Cold Storage" des documents fiscaux (Tiering Hot/Archive) à Montréal. |
| **Comms** | **Mailgun & Twilio** | Canaux transactionnels (Email/SMS/Voix) avec gestion des consentements. |

---

## 3. Architecture Logicielle : Le "Router Pattern"

L'ajout de l'Azure Function transforme l'architecture en un système robuste et découplé, isolant la complexité du parsing et garantissant l'intégrité des données avant qu'elles n'atteignent l'ERP.

### 3.1 Le Flux de Données (Happy Path)
``` mermaid 

sequenceDiagram
    participant Client
    participant JF as JotForm (Ent)
    participant AF as Azure Function (C#)
    participant N8N as n8n (Micro-flows)
    participant AZ as Azure Blob
    participant Odoo

    Client->>JF: Soumet T1 Questionnaire
    JF->>AF: Webhook (Payload Brut + Signature HMAC)
    
    rect rgb(240, 248, 255)
        Note over AF: Zone de Purification (ACL)
        AF->>AF: Valide Signature (Security)
        AF->>AF: Normalise JSON (Mapping DTO)
        AF->>AF: Applique Règles Métier (Complétude)
    end

    AF->>N8N: Déclenche "wf-ingest-t1" (JSON Propre)
    
    N8N->>JF: Télécharge Fichiers (Via API)
    N8N->>AZ: Upload Fichiers (Container T1-2024)
    N8N->>Odoo: Crée/Update Contact
    N8N->>Odoo: Crée Tâche "Prêt pour saisie"
    N8N->>Odoo: Attache Liens Blob Storage
    
    N8N->>JF: Delete Submission (Purge Loi 25)
```  

### 3.2 Rôle Critique du Middleware C# (ACL)

L'Azure Function agit comme une couche d'anti-corruption (ACL) pour protéger la logique interne du cabinet des spécificités techniques de JotForm.

1.  **Stabilité des Identifiants (ID Abstraction) :**
    * *Problème :* Les IDs de champs JotForm (`q12_nom`, `q45_nas`) changent lors du clonage annuel du formulaire.
    * *Solution C# :* Le middleware mappe ces IDs dynamiques vers un modèle de données canonique stable (Business Objects). n8n et Odoo ne consomment que ce modèle stable, ce qui rend les workflows pérennes d'une année à l'autre.
    
2.  **Sécurité & Filtrage (Security Gateway) :**
    * Validation cryptographique de la signature **HMAC SHA-256** de JotForm.
    * Rejet immédiat des requêtes mal formées ou malveillantes avant qu'elles ne consomment des ressources n8n.

3.  **Logique de Décision (Business Logic) :**
    * Centralisation des règles complexes (ex: validation des dépendances entre type de revenu et documents fournis).
    * Le code typé (C#) est plus fiable et testable unitairement que des arbres de décision visuels complexes dans n8n.

---

## 4. Stratégie de Déploiement (Gold vers Enterprise)

Pour démarrer le développement immédiatement sans attendre la finalisation administrative du contrat Enterprise.

### Phase 1 : Développement (Actuel)
- **Compte :** JotForm Gold (Standard US).
- **Données :** Données fictives uniquement (Anonymisation stricte).
- **Config n8n/C# :** Utilisation de variables d'environnement pour l'URL de l'API (`api.jotform.com`).

### Phase 2 : Migration & Go-Live (Février)
- **Action :** Activation de l'instance Enterprise (`cabinet.jotform.com`).
- **Migration :** Clonage des formulaires via l'outil d'importation JotForm Enterprise.
- **Switch Technique :**
    - Mise à jour des variables d'environnement (`JOTFORM_BASE_URL`, `FORM_ID`).
    - Activation du SSO (Single Sign-On) pour les employés.
- **Conformité :** À partir de ce point, les données réelles (y compris les brouillons) sont 100% hébergées au Canada.

---

## 5. Configuration Infrastructure Azure (MSP)

Détails pour la firme TI gérant le tenant Azure existant.

- **Resource Group :** `rg-tax-automation-prod`
- **Azure Function App :**
    - Stack : .NET 8 Isolated (LTS).
    - Plan : Consumption (Coût minimal) ou Premium (si VNET Integration strict requis).
- **Azure Web App (n8n) :**
    - Plan : B1 ou B2 (Linux).
    - Container : Image Docker officielle n8n.
- **Storage Account :**
    - Région : **Canada East (Québec)**.
    - Réplication : LRS (Local) ou ZRS (Zone).
    - Containers : `input-quarantine`, `tax-documents-2024`.
- **Key Vault :** Stockage centralisé des secrets (API Keys Twilio, Mailgun, Odoo, JotForm).

---

## 6. Bibliothèque de Micro-Workflows n8n

L'Azure Function agit comme un "Dispatcher" qui appelle ces workflows atomiques selon le besoin :

1.  **`wf-ingest-t1`** : Réception d'un dossier validé, upload Azure Blob, création Tâche Odoo.
2.  **`wf-client-alert`** : Envoi de notification multicanale (Email -> SMS) générique.
3.  **`wf-escalation-ivr`** : Gestion spécifique de l'appel vocal Twilio et capture des touches (DTMF).
4.  **`wf-update-status`** : Webhook inverse (Odoo -> Client) pour notifier le client d'un changement d'état (ex: "Déclaration transmise").

---

## 7. Configuration Odoo (Destination)

- **Module :** `Standard` (Éviter le code custom Odoo complexe).
- **Projet :** "Impôts T1 2024".
- **Étapes du Pipeline (Kanban) :**
    - `Réception Données` (Automatique via n8n).
    - `Analyse Préliminaire`.
    - `En Cours de Traitement`.
    - `Bloqué / Attente Client` (Déclenché par réponse SMS "AIDE").
    - `Terminé / Transmis`.
- **GED :** Module `cloud_storage_azure` configuré pour décharger les fichiers lourds vers le Blob Storage Azure, gardant la base de données Odoo légère et performante.

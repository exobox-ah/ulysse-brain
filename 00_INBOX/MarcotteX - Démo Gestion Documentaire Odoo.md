# Projet Marcotte : Démo Fonctionnelle & Preuve de Concept (PoC) DMS

**Date visée :** Semaine du 6 janvier 2025
**Responsable :** Consultant
**Partenaires techniques :** Odovia (Odoo), MSP (Simulé sur poste consultant)

---

## 1. Objectifs de la Démo
L'objectif est de valider l'architecture hybride **Odoo + Explorateur Windows** pour la gestion documentaire (DMS), en démontrant trois points clés aux associés :
1.  **Transparence :** Les fichiers sont stockés dans le Cloud (Azure) mais accessibles comme un disque local (`Z:`).
2.  **Automatisation Totale :** La structure des dossiers (Année/Fiscalité) se crée **automatiquement** dès la création d'un client, sans intervention humaine.
3.  **Fluidité :** Le pont entre l'interface Web Odoo et les logiciels de production (Word/Excel) est instantané grâce au bouton "Ouvrir localement".

---

## 2. Architecture Technique (Stack)

| Composante | Solution Retenue pour la PoC | Responsable |
| :--- | :--- | :--- |
| **ERP / Interface Web** | Odoo (Env. Test existant) + Muk DMS | Odovia |
| **Stockage Données** | Azure Blob Storage (Tenant Consultant) | Consultant |
| **Protocole Réseau** | WebDAV (Module `muk_webdav`) | Odovia |
| **Client Windows** | RaiDrive Professional (Mode Disque Local) | Consultant |
| **Authentification** | Clé API Odoo (Token Persistant) | Consultant |
| **Pont Web-Local** | Protocole Custom (`marcotte://`) + PowerShell | Consultant / MSP |

---

## 3. Scénario de la Démo (Le Script)

### Acte 1 : L'Automatisme "Zéro Touche"
1.  **Action :** Dans Odoo, création manuelle d'une nouvelle compagnie (ex: "Entreprise Démo Inc.").
2.  **Point Critique :** Saisir le **No Dossier** dans le champ "Référence" (ex: `999001`). Expliquer que c'est la clé unique utilisée par CCH.
3.  **Sauvegarde :** On clique sur "Sauvegarder".
4.  **Résultat immédiat :**
    * Sans cliquer sur aucun autre bouton, on bascule vers l'onglet "Documents".
    * L'arborescence est déjà là, sous le numéro de dossier : `999001 > 2025 > 01-Comptabilité...`.

### Acte 2 : L'Expérience "Lecteur U:" (La Preuve)
1.  **Action :** Ouverture de l'Explorateur de fichiers Windows (Dossier Jaune).
2.  **Navigation :** Clic sur le lecteur `U: (Marcotte Docs)`.
3.  **Constat :** Le dossier `999001` (le numéro interne) vient d'apparaître sous nos yeux.
4.  **Manipulation :**
    * On entre dans `U:\999001\2025\02-Fiscalité`.
    * On y glisse un PDF.
    * On retourne dans Odoo : le PDF est là.

### Acte 3 : Le Pont "Ouvrir Local" (La Productivité)
1.  **Contexte :** L'utilisateur est dans Odoo et veut éditer un fichier Excel complexe.
2.  **Action :** Clic sur le bouton **"📂 Ouvrir Local"** dans la vue document Odoo.
3.  **Magie :**
    * L'Explorateur Windows s'ouvre au premier plan et **surligne** le fichier Excel.
4.  **Clôture :** Double-clic, modification dans Excel, sauvegarde (CTRL+S).

---

## 4. Spécifications Techniques pour Odovia
*À livrer pour la semaine du 6 janvier.*

### A. Installation Modules & Serveur
* Installer la suite **Muk DMS** complète (Core, Views, Fields, WebDAV).
* Installer le connecteur **Azure Blob Storage** (clés fournies par consultant).
* **Reverse Proxy (Nginx) :** Configuration critique pour autoriser les verbes WebDAV.

### B. Action Automatisée (Trigger)
* **Modèle :** `res.partner` (Contact)
* **Déclencheur :** À la création (`On Creation`)
* **Action :** Exécuter du code Python
* **Code :** Voir Snippet 1 (Annexes).

### C. Bouton : "Ouvrir Local" (Custom Protocol)
* **Modèle :** `muk_dms.file`
* **Type :** Action URL (`ir.actions.act_url`)
* **Code :** Voir Snippet 2 (Annexes).

---

## 5. Configuration Poste Client (Consultant)

### A. RaiDrive Professional
* **Mount :** `U: (Current)`
* **Address :** `https://[url-test].odoo.com/api/dms/webdav/`
* **Auth :** Basic (User: Odoo Username / App Password)

* **Mount :** `Z: (Archive)`
* **Address :** `[AzurefileURL]`
* **Auth :** Microsoft Entra Id 

### B. Protocole Custom & Script
1.  **Registre :** Clé `marcotte://` pointant vers le script PowerShell.
2.  **Script PowerShell :** Mode `Hidden`, nettoie l'URL, lance `explorer.exe /select`.

---

# ANNEXES : SNIPPETS DE CODE

### Snippet 1 : Python - Action Automatisée (Trigger Création Contact)
*À coller dans une "Automation Rule". Crée le dossier basé sur le champ `ref` (NoDossier).*

```python
# CODE POUR ODOVIA - TRIGGER SUR CREATION CONTACT
import datetime

# 1. Configuration
current_year = str(datetime.date.today().year)
subfolders = ["01-Comptabilité", "02-Fiscalité", "03-Paie", "04-Correspondance"]

# 2. Récupération du NoDossier (Reference)
# C'est la clé du dossier. Si pas de ref, on utilise le nom par défaut pour éviter un crash démo.
folder_name = record.ref
if not folder_name:
    folder_name = f"{record.name} (SansNoDossier)"

# 3. Récupération ou Création du dossier racine "Clients"
root_storage = env['muk_dms.directory'].search([('parent_directory', '=', False), ('name', '=', 'Clients')], limit=1)
if not root_storage:
    root_storage = env['muk_dms.directory'].create({'name': 'Clients'})

# 4. Création du dossier du Client (Nommé selon le NoDossier)
client_dir = env['muk_dms.directory'].create({
    'name': folder_name, 
    'parent_directory': root_storage.id,
    'res_model': 'res.partner', # Lien technique vers la fiche contact
    'res_id': record.id
})

# 5. Création du dossier Année
year_dir = env['muk_dms.directory'].create({
    'name': current_year,
    'parent_directory': client_dir.id
})

# 6. Création des sous-dossiers
for sub in subfolders:
    env['muk_dms.directory'].create({
        'name': sub,
        'parent_directory': year_dir.id
    })
```

### Snippet 2 : Python - Bouton URL (Protocole Custom)
```python

# Construit l'URL pour le protocole custom # Format attendu : marcotte://Z:/Chemin/Vers/Fichier.ext base_drive = "Z:" 
# record.path retourne le chemin relatif (ex: /Clients/999001/2025/Fichier.pdf) 

full_path = record.path url = f"marcotte://{base_drive}{full_path}" return { 'type': 'ir.actions.act_url', 'url': url, 'target': 'self' }

```
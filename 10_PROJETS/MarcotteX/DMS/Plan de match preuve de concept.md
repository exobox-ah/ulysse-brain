### 1. LE CERVEAU : L'Action Serveur Odoo (Python)

C'est le détonateur. On crée un bouton dans Odoo qui ne télécharge pas le fichier, mais qui envoie l'ordre à Windows de l'ouvrir localement.

**Configuration dans Odoo :**

- **Modèle :** `documents.document` (Module Documents)
    
- **Type d'Action :** Exécuter du code Python
    

Python

```
# CODE ACTION SERVEUR ODOO
# ---------------------------------------------------------
# Hypothèse : Le nom du document dans Odoo = Nom du fichier sur Z:
# Hypothèse : Le montage Z: est la racine du stockage

file_name = record.attachment_id.name or record.name
drive_letter = "Z:/"

# On nettoie le chemin (juste au cas)
clean_name = file_name.strip()

# On construit l'URI du protocole custom
# Format : odoolocal://Z:/MonDossier/MonFichier.pdf
target_path = f"{drive_letter}{clean_name}"
custom_url = f"odoolocal://{target_path}"

# On retourne l'action URL pour que le navigateur la lance
action = {
    'type': 'ir.actions.act_url',
    'url': custom_url,
    'target': 'self',
}
```

---

### 2. LE CLIENT : L'Intercepteur Windows (PowerShell & Reg)

Ici, on "hacke" le registre Windows pour qu'il comprenne que `odoolocal://` n'est pas une page web, mais une commande locale.

A. Le Script Launcher (Launcher.ps1)

Crée ce fichier dans C:\MarcotteX\Launcher.ps1.

PowerShell

```
param (
    [string]$Uri
)

# 1. Nettoyage du protocole (On enlève 'odoolocal://')
# Note: Les navigateurs ajoutent parfois un '/' final, on gère ça.
$CleanPath = $Uri -replace "odoolocal://", ""
$CleanPath = $CleanPath -replace "/$", ""

# 2. Décodage des caractères URL (ex: %20 devient Espace)
$RealFilePath = [Uri]::UnescapeDataString($CleanPath)

# 3. Vérification de sécurité (Basic)
# On s'assure que ça pointe bien vers Z: pour éviter d'exécuter n'importe quoi
if ($RealFilePath -like "Z:*") {
    if (Test-Path $RealFilePath) {
        # Lancement du fichier avec l'app par défaut
        Start-Process $RealFilePath
    } else {
        [System.Windows.Forms.MessageBox]::Show("Fichier introuvable sur Z: `n$RealFilePath", "Erreur Harmonie", 0, 16)
    }
} else {
    [System.Windows.Forms.MessageBox]::Show("Sécurité : Tentative d'ouverture hors du lecteur Z:", "Alerte Harmonie", 0, 48)
}
```

B. Le Registre (Protocol.reg)

Double-clique dessus pour l'injecter. Cela associe le protocole au script.

Extrait de code

```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\odoolocal]
@="URL:Odoo Local File Protocol"
"URL Protocol"=""

[HKEY_CLASSES_ROOT\odoolocal\shell]

[HKEY_CLASSES_ROOT\odoolocal\shell\open]

[HKEY_CLASSES_ROOT\odoolocal\shell\open\command]
@="powershell.exe -ExecutionPolicy Bypass -File \"C:\\MarcotteX\\Launcher.ps1\" -Uri \"%1\""
```

---

### 3. L'INFRASTRUCTURE : Docker Compose (Le Labo)

Pas besoin de complexité. Une instance propre pour tester l'action serveur.

**Fichier `docker-compose.yml`**

YAML

```
version: '3.1'
services:
  web:
    image: odoo:17.0
    depends_on:
      - db
    ports:
      - "8069:8069"
    volumes:
      - odoo-web-data:/var/lib/odoo
      - ./config:/etc/odoo
    environment:
      - HOST=db
      - USER=odoo
      - PASSWORD=odoo

  db:
    image: postgres:15
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=odoo
      - POSTGRES_USER=odoo
    volumes:
      - odoo-db-data:/var/lib/postgresql/data

volumes:
  odoo-web-data:
  odoo-db-data:
```

---

### 4. LE STOCKAGE : Azure CLI (La Voûte)

Commandes rapides pour monter ton infra stockage si elle n'existe pas encore.

Bash

```
# 1. Créer le Resource Group
az group create --name MarcotteX-RG --location canadacentral

# 2. Créer le Storage Account (LRS pour le labo, moins cher)
az storage account create \
  --name marcottexstorage \
  --resource-group MarcotteX-RG \
  --sku Standard_LRS

# 3. Créer le File Share (SMB)
az storage share create \
  --name documents-vault \
  --account-name marcottexstorage
```

Pour le montage Windows (Z:) :

Dans le portail Azure > Storage Account > File Shares > documents-vault > Connect > Onglet Windows. Copie le script PowerShell fourni par Azure et exécute-le sur ton Lenovo.

---

### PLAN D'ATTAQUE (Architecte Ulysse)

1. **Mount Z:** Lance le script Azure sur ton PC pour avoir le lecteur `Z:`. Mets-y un fichier test `Test.pdf`.
    
2. **Deploy Docker:** `docker-compose up -d`.
    
3. **Config Windows:** Crée le dossier `C:\MarcotteX`, mets le `.ps1` dedans, et lance le `.reg`.
    
4. **Config Odoo:**
    
    - Installe le module `Documents`.
        
    - Crée un record document nommé `Test.pdf` (pas besoin d'uploader le vrai fichier, juste le record).
        
    - Crée l'Action Serveur (code ci-dessus) et ajoute-la au menu "Action" du modèle Document.
        
5. **Test de Feu:** Va sur le document dans Odoo, clique Action -> "Ouvrir en Local".
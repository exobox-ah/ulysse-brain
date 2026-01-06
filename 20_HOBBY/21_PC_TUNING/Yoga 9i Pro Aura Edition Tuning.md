# 🛠️ Master Log : Optimisation "Zero-Latency" Yoga Pro 9i

**Date de validation :** 22 Décembre 2025
**Statut :** 🟢 LOCKED (Production Ready)
**Machine :** Lenovo Yoga Pro 9i "Aura Edition"
**Specs :** Core Ultra 9 285H EvoPro | RTX 5070 Laptop (8GB) | 64GB LPDDR5x | 2 x SSD 1TB PCIe 4.0
**OS :** Windows 11 Pro (24H2)

---

## 0. 💻 Specs & Hardware (Lenovo Yoga Pro 9i)
*Configuration : Core Ultra 9 285H + RTX 5070 (Certifié Evo).*

* **CPU :** Intel Core Ultra 9 285H
    * *Certification :* Intel Evo Edition (Sticker).
    * *Architecture :* Arrow Lake (Mobile).
    * *Optimisation :* Parking Off + Scaling On (5-100%).
* **GPU :** NVIDIA GeForce RTX 5070 8GB
    * *Architecture :* Blackwell (Support HAGS Natif via puce AMP).
    * *Optimisation :* HAGS On (Obligatoire) + Reflex Boost.
* **RAM :** 64 Go LPDDR5X
    * *État :* Cache système `LargeSystemCache` = 0.
* **SSD :** 1TB SK Hynix (HFS001TEM4X182N) x2
    * *Interface :* PCIe 4.0 x4 (Validé).
    * *Optimisation :* Link Power Management OFF.

## 1. ⚡ CPU, Boot & Gestion d'Énergie (Fondations)
*Objectif : Système "Éveillé", Démarrage "Propre", Latence CPU minimale.*

### 🛠️ Système & Démarrage (Admin)
- [x] **Désactiver Hibernation & Fast Boot :**
    - **Commande :** `powercfg -h off` (Terminal Admin).
    - **Effet 1 (Fast Boot) :** Force un "Cold Boot" à chaque allumage (pilotes chargés à neuf, zéro bug mémoire).
    - **Effet 2 (Deep Sleep) :** Supprime le fichier `hiberfil.sys`. Empêche le PC d'hiberner et de faire planter le Dock/USB.

### 🔌 Plan d'Alimentation (Windows)
- [x] **Power Plan :**
    - Sélectionner : **Bitsum Highest Performance**.
    - Action : Cliquer sur **Make Active**.
- [x] **Minuteurs de Veille :**
    - **Écran :** 10-15 min (Selon préférence).
    - **Mise en veille (Sleep) :** ⚫ **JAMAIS** (Never).
        - *Critique :* Bloque le "Modern Standby" qui déconnecte la carte réseau et le Dock.

### 🧠 ParkControl (Réglages CPU)
- [x] **Réglages Secteur (Plugged In / AC) :**
    - **Parking AC :** ⚫ **Disabled** (OFF).
        - *Pourquoi :* Empêche les cœurs d'entrer en sommeil profond (C6). Latence de réveil = 0ms.
    - **Freq Scaling AC :** ⚫ **Enabled** (ON).
        - *Pourquoi :* Autorise le Core Ultra 9 à monter en Turbo (5.4GHz) pour le Single Core.
    - **Curseurs (Scaling) :**
        - **Min :** **5%** (Repos au frais sur le bureau).
        - **Max :** **100%** (Puissance max en jeu).
- [x] **Validation :**
    - Cliquer sur **Apply**.

---

## 2. 🎮 GPU & Latence DPC (RTX 50-Series / Blackwell)
*Cible : Stabilité thermique et priorité interruptions.*

- [x] **Pilote :** NVIDIA Studio Driver **v591.44** (Nettoyé).
- [x] **NVCP (Global/Valorant) :**
    - **Mode de gestion de l'alim :** "Privilégier les performances maximales".
    - **Mode Faible Latence :** **Ultra**.
    - **Max Frame Rate :** **240 FPS** (Cap thermique & G-Sync).
- [x] **HAGS (Hardware Accelerated GPU Scheduling) :**
    - **État :** ⚫ **ACTIVÉ** (ON) - **OBLIGATOIRE**.
    - *Pourquoi :* L'architecture RTX 50 utilise une puce dédiée (AMP) pour gérer le scheduling.
    - *Risque :* Désactiver HAGS sur Blackwell force le CPU à gérer la mémoire vidéo, ce qui augmente la latence et contourne l'optimisation matérielle native.
- [x] **Nvidia Reflex :**
    - **Mode :** **On + Boost**.
    - *Note :* Avec l'efficacité énergétique des RTX 50, le mode "Boost" maintient les fréquences au max sans surchauffe critique.
- [x] **MSI Mode (Message Signaled Interrupts) :**
    - **Statut :** Enabled (via MSI Utility v3).
    - **Priorité :** **High** (Registry `DevicePriority` = 3).

---

## 3. 🧠 RAM & Architecture (64GB @ 8400MT/s)
*Stratégie : Tout en RAM, rien sur le disque.*

- [x] **PageFile (Mémoire Virtuelle) :**
    - **Taille :** Fixée manuellement à **32768 MB** (Min/Max).
- [x] **Optimisations Registre (`Memory Management`) :**
    - `DisablePagingExecutive` = **1** (Force le Kernel en RAM).
- [x] **Compression :** `Disable-MMAgent -mc` (Exécuté une fois).

---

## 4. ⏲️ Latence Système & Cache (ISLC)
*Outil : Intelligent Standby List Cleaner.*

- [x] **Conditions de Purge :**
    - `The list size is at least` : **1024 MB**.
    - `Free memory is lower than` : **16384 MB** (Optimisé pour 64GB RAM).
- [x] **Timer Resolution :**
    - **Wanted timer resolution :** **0.50 ms**.
    - **Case :** "Enable custom timer resolution" **COCHÉE**.
- [x] **Démarrage :** "Start ISLC minimized and auto-Start monitoring" **COCHÉE**.

---

## 5. 🌐 Réseau (Dock Realtek USB)
*Cible : Désactiver l'économie d'énergie agressive du chipset Realtek.*

- [x] **Propriétés Avancées (Gestionnaire de périphériques) :**
    - **Energy-Efficient Ethernet (EEE) :** **Désactivé**.
    - **Green Ethernet :** **Désactivé**.
    - **Idle Power Saving :** **Désactivé**.
    - **Flow Control :** **Désactivé**.
    - **Recv Segment Coalescing (IPv4/IPv6) :** **Désactivé** (Crucial pour le ping).
- [x] **Routing (ExitLag) :**
    - **Région :** Automatic (Virginia/Illinois failover).
    - **Routes UDP :** 2.

---

## 6. 🔌 USB & Périphériques (La Chaîne Complète)
*Règle : Aucun maillon de la chaîne ne doit s'éteindre.*

- [x] **Méthode :** "Affichage > Périphériques par connexion".
- [x] **Cibles traitées :**
    - `Realtek USB GbE` ➡️ `Generic USB Hub` ➡️ `USB Root Hub`.
    - **Action :** Case "Autoriser l'ordinateur à éteindre ce périphérique" **DÉCOCHÉE** partout.
- [x] **Inputs :**
    - Razer Viper V3 Pro @ 1000Hz.
    - Touche Copilot remappée (`Ctrl+Alt+G`).

---

## 7. 🧹 Nettoyage & Sécurité
*Objectif : Silence radio en arrière-plan & Sécurité Pro.*

- [x] **OneDrive :** Délié ➡️ Désinstallé ➡️ Bloqué via GPO.
- [x] **Microsoft Teams :** Démarrage désactivé (Version "Home" et "Work").
- [x] **Core Isolation (VBS) :** ✅ **ACTIVÉ** (Standard).
    - *Raison :* Priorité Sécurité Professionnelle.
    - *Impact :* Négligeable sur Core Ultra 9 (Support matériel MBEC).

---

## 8. 🚀 Priorités MMCSS (Optimisé ExitLag)
*Objectif : Priorité Jeu maximale, tout en protégeant le traitement réseau en arrière-plan.*

- [x] **SystemProfile (Racine) :**
    - `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile`
    - **`NetworkThrottlingIndex`** = **ffffffff** (Hex).
        - *Crucial pour ExitLag :* Supprime totalement le bridage du débit réseau par Windows.
    - **`SystemResponsiveness`** = **10** (Décimal).
        - *Pourquoi 10 et pas 0 ?* Laisse une petite marge de sécurité (10% CPU) aux processus d'arrière-plan critiques comme **ExitLag** pour éviter les pertes de paquets.

- [x] **Tasks \ Games :**
    - `...SystemProfile\Tasks\Games`
    - `GPU Priority` = **8**.
    - `Priority` = **6**.
    - `Scheduling Category` = **High**.
    - `SFIO Priority` = **High**.

---

## 9. 🕵️ Télémétrie & Diagnostics
*Objectif : Supprimer les tâches de fond aléatoires (Scans disque/Réseau).*

- [x] **Services Windows (services.msc) :**
    - `Connected User Experiences and Telemetry` (DiagTrack) : **DÉSACTIVÉ**.
    - `dmwappushservice` : **DÉSACTIVÉ**.
    - *Gain :* Évite l'envoi de paquets de données pendant le jeu.

- [x] **Tâches Planifiées (Task Scheduler) :**
    - `Microsoft \ Windows \ Application Experience` :
        - **Microsoft Compatibility Appraiser** : **DÉSACTIVÉ** (Scan disque CPU-vore).
    - `Microsoft \ Windows \ Customer Experience Improvement Program` :
        - **Tout désactiver** (Consolidator, UsbCeip).
    - *Gain :* Empêche les scans de compatibilité inopinés qui créent des micro-stutters.

---

## 10. 🎥 Mode Jeu & Captures (DVR)
*Objectif : Supprimer l'enregistrement en arrière-plan (Latence) et prioriser le jeu.*

- [x] **Captures (DVR / Xbox Game Bar) :**
    - `Paramètres > Jeux > Captures`
    - **Enregistrer ce qui s'est passé (Record what happened)** : ⚫ **DÉSACTIVÉ** (OFF).
        - *Crucial :* Si activé, Windows enregistre en permanence les 30 dernières secondes sur le SSD. Cela crée des micro-écritures constantes et utilise le CPU pour l'encodage, ce qui ajoute de l'input lag.

- [x] **Mode Jeu (Game Mode) :**
    - `Paramètres > Jeux > Mode Jeu`
    - **Mode Jeu** : ⚪ **ACTIVÉ** (ON).
        - *Pourquoi :* Sur l'architecture hybride Intel (Core Ultra), cela aide Windows à confiner les tâches de fond (Antivirus, Update) sur les cœurs efficients (E-Cores) pour laisser les cœurs puissants (P-Cores) 100% libres pour Valorant.
---

## 11. 📊 Benchmarks de Validation (Reference)
*Scores obtenus le 19/12/2025.*

| Test | Score / Valeur | Signification |
| :--- | :--- | :--- |
| **Cinebench 2024 (1-Core)** | **117 pts** | Turbo Boost actif et sain. |
| **Cinebench 2024 (Multi)** | **1095 pts** | Refroidissement efficace. |
| **Steel Nomad (GPU)** | **2886 pts** | ~30 FPS stables (Excellent pour un Slim). |
| **Latence DPC (Idle)** | **~27 µs** | Pas de pics rouges. Clean. |

![[3d Mark Steel Nomad_2025_12_19.png]]
![[Cinebench 2024_2025-12-19_Score.png]]
---
#tags: #config #lenovo #yoga_pro_9i #rtx5070 #valorant #optimization #islc
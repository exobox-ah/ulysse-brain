
### 1. L'Interface Visuelle et Graphique (L'UI Protecteur)
 * **Composant :** Un habillage graphique (*Graphic Overlay*) circulaire en polycarbonate transparent.
 * **Fabrication :** Impression sérigraphique ou numérique **inversée** (sous la couche de polycarbonate, côté adhésif).
 * **Esthétique (Ton sur Ton) :** L'encre blanche (ou noire) correspond exactement à la teinte de votre boîtier. Elle dessine les repères visuels de la molette tactile (les graduations du "petit o") et les icônes de paiement au Nord de manière subtile et invisible de loin.
 * **Finition Optique :** Le polycarbonate agit comme un vitrage protecteur. Il uniformise la diffusion de la lumière des DEL, élimine complètement les micro-stries de l'impression 3D en surface et scelle hermétiquement le dessus de l'appareil contre les liquides (café renversé, nettoyage).
### 2. Le Boîtier (L'Enveloppe Mécanique et Optique)
 * **Géométrie Extérieure :** Un galet circulaire de 130 mm de diamètre (le "Grand O"), avec un profil en biseau (Sloped Puck) incliné de 3 à 5 degrés (épaisseur de ~10 mm à l'avant, ~15 mm à l'arrière).
 * **Parois Latérales :** Murs de **2,0 mm** d'épaisseur (5 périmètres d'impression avec une buse de 0,4 mm) garantissant une solidité structurelle maximale et bloquant toute fuite de lumière latérale.
 * **Surface Supérieure (L'Opacité Sélective) :**
   * **Zone Générale :** Épaisseur de **1,0 mm**. Offre un rendu rigide, une acoustique mate, et sert de support plat pour coller l'overlay en polycarbonate.
   * **Fenêtre d'Écran :** Amincie chirurgicalement à **0,6 mm** pour permettre l'effet *Dead Front* et laisser percer la lumière des DEL blanches à travers le plastique et le polycarbonate.
 * **Assemblage Interne :** Architecture en "sandwich compressé". Le fond plat utilise des piliers de hauteurs variables pour maintenir le *middle frame* parallèle à la façade inclinée.
### 3. Le Cerveau et l'Énergie (La Logique de Base)
 * **Microcontrôleur :** **Arduino Nano ESP32** (Réf: ABX00092) version *sans broches* (No Headers). Soudé directement à plat (SMT) pour un profil bas.
 * **Certification :** Module pré-certifié u-blox NORA-W106 (blindage FCC/CE/IC et antenne Wi-Fi intégrée), esquivant les dizaines de milliers de dollars de certification RF.
 * **Alimentation Principale :** Module de négociation **USB-C PD** (Power Delivery), monté sur un perfboard faisant office de carte de distribution d'énergie (PDB) pour gérer les ampérages de l'anneau sans brûler le microcontrôleur.
### 4. L'Affichage et l'Interface Marchand (Le Centre)
 * **Écran Matrice :** Deux cartes Adafruit 9x16 DEL blanches juxtaposées (contrôleur IS31FL3731, communication I2C, adresses 0x74 et 0x77) formant un écran 9x32 continu.
 * **Ségrégation Optique :** Un *middle frame* imprimé en PLA noir agissant comme grille de séparation (Light Baffle). Collé sous la fenêtre de 0,6 mm, il empêche l'effet "abat-jour" pour garantir la netteté des chiffres à travers l'épaisseur cumulée (PLA + Polycarbonate).
 * **Le "Petit o" (Tactile Capacitif) :** Molette invisible composée de 4 segments de ruban de cuivre et d'un bouton central carré (0,2 mm). Placés sous le couvercle de 1,0 mm et connectés aux broches de l'ESP32 via des fils monobrins cachés. L'overlay en polycarbonate n'altère en rien la sensibilité capacitive.
### 5. La Zone de Paiement Client (Le Périphérique)
 * **NFC Passif :** Un autocollant Tag NDEF (NTAG213/215) collé à plat sous la façade de 1,0 mm au Nord. Il redirige le téléphone du client vers l'URL de paiement sans nécessiter de lecteur actif certifié EMV.
 * **Anneau Lumineux (Feedback) :** Un anneau de **120 mm** avec 42 DEL RGB WS2812B sur PCB blanc.
 * **Canal de Diffusion Isolé :** Logé sur une marche périphérique avec un **vide d'air de 3 à 4 mm** au-dessus de lui, et séparé du centre par un mur interne. La lumière se mélange dans ce vide et traverse le PLA et le polycarbonate pour créer un halo néon parfait.
### 6. La Topographie Spatiale Finale (La Rose des Vents Ouilo)
| Zone | Composant Hébergé | Fonction & Justification |
|---|---|---|
| **Nord** | Tag NFC Passif & Icône UI | Zone de "Tap" pour le client. Graphique indicatif sur l'overlay. Aucun métal en dessous. |
| **Centre** | Matrice 9x32 & Molette UI | Zone interactive. L'overlay indique subtilement le tracé de la molette. Écran invisible à l'arrêt (*Dead Front*). |
| **Périmètre** | Anneau DEL 120 mm | Halo lumineux traversant la bordure transparente ou semi-opaque de l'overlay pour indiquer le statut. |
| **Est** | Antenne Wi-Fi (u-blox) | Dégagement maximal pour les ondes radio, loin des bruits USB et des masses de cuivre. |
| **Ouest** | Port USB-C PD | Arrivée de puissance pour le marchand, gardant le câble hors de la zone de transaction du client. |
| **Fond** | Arduino ESP32 & Perfboard | Carte logique et puissance fixées au fond plat, protégées thermiquement. |

# Analyse Repêchage 2026-2027

Préparé à partir du kit PoolExpert (`data/draftkit-fr-*.xlsx`), des Listes des listes et des règlements. Les tableaux complets (tous les joueurs, toutes les colonnes) sont dans `scripts/sortie.md`, régénérable avec `node scripts/analyse.js`.

## En bref

- **Format : 16 rondes**, avec 8 attaquants, 2 défenseurs, 1 gardien et l'équipe actifs, plus 4 joueurs de banc. Les choix sont définitifs : ni échange ni ballottage.
  - Une fois 2 gardiens repêchés, il ne reste que 3 places de banc pour les paris de chaque équipe. Voir « Répartition des 16 choix » dans l'objectif 4.
- **Le « rang kit » sert d'ADP.** Le `#` du kit n'est pas un ADP : c'est le classement par points projetés. Comme tout le monde repêchera avec ce kit, c'est la meilleure approximation du prix du marché. Un joueur au rang kit 130 devrait partir vers le choix 130.
- **Le kit, c'est Fantrax.** Les projections du kit sont identiques à celles de Fantrax pour 169 joueurs sur 240, et à 1 point près pour 218. La valeur se trouve donc chez les joueurs que **HLM et ESPN** voient tous deux plus haut que Fantrax.
- **Défenseurs : le rang kit ne suffit pas.** Dans ton pool, le bonus de duo pousse les défenseurs à partir tôt. Une simulation du repêchage (section Objectif 4) donne deux résultats :
  - **En positions 6 à 21, deux défenseurs élites aux rondes 1 et 2 est la meilleure stratégie ou fait jeu égal**, et c'est particulièrement vrai à 19-21, où les deux choix sont dos à dos. Aux positions 1 à 3, c'est une erreur (environ 20 points de moins).
  - Avec cette surenchère, les défenseurs partent environ une ronde plus tôt que leur rang kit. Ta liste pour les rondes 7-8 (Byram, Harley, Luke Hughes, puis Clarke) correspond bien au marché réel.
- **Porter Martone n'est pas un diamant caché.** Le kit le projette à 72 points (rang 49, ronde 3), plus haut que ton plan (68).
- **Meilleure équipe sleeper : Ottawa.** Rang kit 28 sur 32 (85 pts), mais 10e dans ton plan (97,8 pts, 58 % de chances de séries), 95 chez JFresh et 99 pts la saison dernière. Ullmark (rang G29 au kit, rang 9 dans la Liste des listes Gardiens) complète le duo.
- **NHL.com (source ajoutée) :** attention, les projections de ton plan sont celles de NHL.com (même source). Avec HLM, ESPN ou Dobber en appui : Cooley (80), McKenna (63), Stankoven (61), Perreault (57), Theodore (57), et à deux sources Stenberg (61), Frondell (62), Clarke (55). Helenius a fait l'équipe (2e trio, AN2). Sleepers manqués : **Victor Eklund** (NYI ; kit 1 point, NHL 51, HLM 65, ESPN 52, dans l'alignement), **Schaefer** (D, NHL 72), **Seth Jones** (D, NHL 52) et **Ilya Protas** (WSH, 3e centre). Blessés selon NHL.com : Jarvis, Terry, Fiala, Tippett.
- **Nouveau sleeper d'équipe : Edmonton.** JFresh le place 4e (105), contre 92 au kit (14e) ; ton plan dit 96,7. Plus cher qu'Ottawa, mais environ 8 points de plus.
- **Nouvelles de dernière minute intégrées :**
  - **Stuart Skinner** a signé à Winnipeg : il devient le partant tant que Hellebuyck est en grève, pour le prix d'un choix de fin de repêchage.
  - **Stenberg** est projeté à 65 points par Dobber : il passe de pari à diamant confirmé.
  - **Cagnoni** est confirmé dans l'alignement des Sharks.
  - **T.J. Hughes** (COL, AN1) est absent du kit : vérifie qu'on peut le sélectionner sur PoolExpert.
- **Deux équipes dans le même pool :** mets Wallstedt dans l'une et Ullmark dans l'autre, puis ajoute Skinner et Allen (ou Blackwood) comme 2es gardiens. Répartis aussi les sleepers : Ottawa d'un côté, Cagnoni et Nemec un de chaque côté. Les détails sont à la fin de la section gardiens.
- **Projections Dobber (33 joueurs) : les plus gros écarts avec le kit.**
  - **Fantilli** : 79 points (kit 57, ronde 6). Le meilleur attaquant à viser aux rondes 5-6.
  - **McKenna** : 70 (kit 42, ronde 10). Avec HLM à 64, deux sources le voient maintenant bien plus haut.
  - **Michkov** : 68 (kit 51, ronde 7).
  - **Frondell** : 65 en 82 matchs (kit 44 en 71 matchs, ronde 9) ; ton plan dit 62. À prendre en ronde 8 ou 9.
  - **Marner** : 99 (kit 86, rang 19).
  - En défense : **Nemec** (46, contre 24 au kit, rang 384) et **Luke Hughes** (47, sur l'AN1 à la place de Hamilton).
  - **À éviter : Patrick Kane** (Dobber 53 en 65 matchs, contre 64 au kit).
- **Les meilleurs gardiens valent plus que prévu.** Avec 2 points par victoire, 1 par nulle et 3 par blanchissage, Vasilevskiy (96 pts pool) vaut un choix de ronde 2, et Oettinger ou Sorokin un choix de ronde 3. Ta liste de gardiens pour les rondes 7-11 se situe au niveau de remplacement (environ 59 pts) : attendre coûte peu, mais les écarts entre eux sont faibles.

<!-- HV:start -->
## High value picks (liste globale)

Tous les choix jugés de haute valeur dans ce document, regroupés et triés par ronde cible. **Ronde prévue** : rang du kit (`draftkit-fr-p.xlsx`) divisé par 21 poolers, soit là où le marché devrait le prendre. **Ronde cible** : la ronde la plus tardive où le prendre sans risquer de le perdre, selon l'analyse (surenchère sur les défenseurs, visibilité des sources, taxe CH). **Consensus** : moyenne des sources indépendantes (NHL.com corrigé de 5.3 points, HLM, ESPN, Dobber ; ton plan reprend NHL.com). **Ronde méritée** : la ronde où le kit placerait un joueur qui projette le consensus. **Valeur** : ronde cible (début) moins ronde méritée, soit le nombre de rondes gagnées en le prenant à sa ronde cible. Pour les défenseurs, la valeur réelle est plus haute que ce chiffre, parce que le défenseur de remplacement projette 36 points contre 42 pour l'attaquant.

Si la ronde cible est plus tôt que la ronde prévue, c'est voulu : le marché réel de ton pool le prendra avant le kit (surenchère sur les défenseurs, joueurs visibles dans HLM).

| Ronde cible | Joueur | Pos | Éq. | Ronde prévue (rang kit) | Kit | Consensus | Ronde méritée | Valeur (rondes) | Catégorie | Pourquoi |
|---|---|---|---|---|---|---|---|---|---|---|
| **R1** | Mitch Marner | F | VGK | R1 (19) | 86 | 91 | R1 | 0 | Plafond | Dobber 99 ; en positions 19-21, alternative au défenseur élite |
| **R1-2** | Quinn Hughes | D | MIN | R2 (31) | 80 | 84 | R2 | -1 | Duo élite | Cible n° 1 du duo de défenseurs en positions 19-21 (Dobber 87) |
| **R2** | Clayton Keller | F | UTA | R1 (16) | 90 | 89 | R1 | +1 | Marché | Souvent négligé, 82 matchs ; saute dessus s'il glisse en ronde 2 |
| **R4** | Brayden Point | F | TBL | R4 (84) | 61 | 76 | R3 | +1 | Rebond | Saison blessée ; NHL 85, HLM 76, ESPN 73 |
| **R5** | Dylan Holloway | F | STL | R5 (91) | 59 | 67 | R4 | +1 | Confirmé | Rythme de 71 ; HLM 71, NHL 70 |
| **R5** | Will Smith | F | SJS | R5 (92) | 59 | 69 | R3 | +2 | Confirmé | Rythme de 70 ; HLM 78, NHL 75 |
| **R5** | Ivan Demidov (bl.) | F | MTL | R5 (101) | 58 | 67 | R4 | +1 | Confirmé | Taxe CH : peut partir plus tôt |
| **R5-6** | Matthew Schaefer | D | NYI | R5 (86) | 61 | 64 | R4 | +1 | Défenseur 1 | 59 points à 18 ans ; NHL 72. S'il glisse |
| **R6** | John Carlson | D | TBL | R5 (89) | 60 | 62 | R4 | +2 | Défenseur 1 | Dobber 68, AN1 à Tampa ; s'il glisse en ronde 6, avant Michkov |
| **R6** | Adam Fantilli | F | CBJ | R6 (107) | 57 | 67 | R4 | +2 | Plafond | Dobber 79, NHL 68, HLM 65 ; Dobber l'a eu au 149e choix |
| **R6** | Logan Cooley | F | UTA | R7 (130) | 53 | 71 | R3 | +3 | Plafond | Trois sources : NHL 80, HLM 70, ESPN 67 |
| **R6** | Jackson LaCombe | D | ANA | R7 (135) | 53 | 59 | R5 | +1 | Défenseur 1 | Le plus sûr : 58 points en 82 matchs ; NHL 65, HLM 66 |
| **R6** | Shayne Gostisbehere | D | CAR | R7 (140) | 52 | 54 | R7 | -1 | Défenseur 1 | Rythme de 75 ; spécialiste de l'AN |
| **R6-7** | Roope Hintz | F | DAL | R6 (117) | 55 | 69 | R3 | +3 | Plafond | NHL 78, HLM 70 ; risque santé (53 matchs) |
| **R6-7** | Matvei Michkov | F | PHI | R7 (146) | 51 | 59 | R5 | +1 | Plafond | Dobber 68, HLM 60 |
| **R7** | Marco Rossi | F | VAN | R7 (145) | 51 | 54 | R7 | 0 | Confirmé | Diamant du plan confirmé |
| **R7** | Shea Theodore | D | VGK | R9 (174) | 45 | 55 | R6 | +1 | Défenseur 2 | 1er de ta liste : HLM 61, Dobber 61, NHL 57 |
| **R7** | Bowen Byram | D | CHI | R10 (204) | 41 | 50 | R8 | -1 | Défenseur 2 | Quatre sources à 50-55 ; Bedard absent au départ |
| **R7** | Cole Hutson | D | WSH | R10 (206) | 40 | 48 | R8 | -1 | Défenseur 2 | AN1 plus tard dans la saison ; plafond de 60+ |
| **R7-8** | Gavin McKenna | F | TOR | R10 (191) | 42 | 58 | R5 | +2 | Plafond visible | HLM 64, Dobber 70, NHL 63 |
| **R7-8** | Luke Hughes | D | NJD | R10 (209) | 40 | 44 | R9 | -2 | Défenseur 2 | AN1 à la place de Hamilton ; NHL 45 |
| **R8** | Brandt Clarke | D | LAK | R12 (243) | 36 | 49 | R8 | 0 | Défenseur 2 | AN1 à LA, 40 points en 82 matchs ; Dobber 48, NHL 55 |
| **R8-9** | Jackson Blake | F | CAR | R8 (163) | 47 | 59 | R5 | +3 | Plafond visible | HLM 68 ; Jarvis absent |
| **R8-9** | Anton Frondell | F | CHI | R9 (179) | 44 | 56 | R6 | +2 | Plafond | Dobber 65, NHL 62 ; HLM 45 seulement |
| **R8-9** | Matt Coronato | F | CGY | R9 (186) | 43 | 51 | R8 | 0 | Plafond | Dobber 57, HLM 50, ESPN 48 |
| **R9** | Mason McTavish | F | STL | R9 (180) | 44 | 49 | R8 | +1 | Plafond | HLM 52, Dobber 53 |
| **R9** | Logan Stankoven | F | CAR | R10 (192) | 42 | 51 | R8 | +1 | Plafond | NHL 61, Dobber 54, HLM 53 |
| **R9-10** | Josh Doan | F | BUF | R9 (175) | 45 | 53 | R7 | +2 | Plancher | 52 points en 82 matchs ; HLM 61 (ne pas surpayer) |
| **R9-10** | Zach Benson | F | BUF | R10 (190) | 42 | 53 | R7 | +2 | Plafond | HLM 62, NHL 61 ; AN1 à Buffalo |
| **R10-11** | Frank Nazar | F | CHI | R11 (211) | 40 | 51 | R8 | +2 | Plafond | HLM 58, NHL 54 ; Bedard absent au départ |
| **R10-11** | Gabe Perreault | F | NYR | R12 (251) | 35 | 51 | R8 | +2 | Plafond | Trois sources : NHL 57, Dobber 52, HLM 50 |
| **R10-12** | Seth Jones | D | FLA | R13 (264) | 33 | 44 | R9 | +1 | Plan B défense | NHL 52, HLM 47, rythme de 50 |
| **R11** | Collin Graf | F | SJS | R11 (225) | 37 | 46 | R9 | +2 | Plancher | 46 points en 81 matchs ; HLM 50, NHL 54 |
| **R11-13** | Simon Nemec | D | CGY | non repêché (384) | 24 | 40 | R11 | 0 | Pari établi | 19:40 de temps de glace ; Dobber 46, NHL 40. Jamais avec Parekh |
| **R12** | Mavrik Bourque | F | NSH | R13 (253) | 35 | 47 | R8 | +4 | Plancher | 82 matchs ; HLM 52, NHL 55 |
| **R12-14** | Brandon Montour | D | SEA | R12 (250) | 35 | 41 | R10 | +2 | Défenseur 3 | Établi : NHL 48, HLM 46 |
| **R12-14** | Ivar Stenberg | F | SJS | non repêché (375) | 24 | 60 | R5 | +7 | Caché | Dobber 65, NHL 61 ; absent de la LdL |
| **R12-14** | Luca Cagnoni | D | SJS | non repêché (610) | 10 | 31 | R14 | -2 | Pari établi | AN1 à San José ; NHL 36 |
| **R12-14** | Victor Eklund | F | NYI | non repêché (822) | 1 | 54 | R7 | +5 | Caché | Kit : 1 match ; NHL 51, HLM 65, ESPN 52. A fait l'équipe |
| **R13-14** | Matvei Gridin | F | CGY | R13 (263) | 33 | 41 | R10 | +3 | Confirmé | Diamant du plan confirmé |
| **R13-14** | Noah Hanifin | D | VGK | R14 (277) | 32 | 37 | R12 | +1 | Défenseur 3 | Dobber 40 ; vétéran stable, va avec Vegas |
| **R13-14** | Matt Savoie (bl.) | F | EDM | R14 (278) | 32 | 43 | R10 | +3 | Confirmé | Blessé : vérifier le retour |
| **R13-15** | Roman Kantserov | F | CHI | R16 (320) | 28 | 47 | R8 | +5 | Caché | Dobber 55, NHL 45 ; pas avec Frondell |
| **R15-16** | Konsta Helenius | F | BUF | non repêché (376) | 24 | 44 | R9 | +6 | Caché | 2e trio et AN2 à Buffalo ; NHL 49 |
| **R15-16** | Ryan Ufko | D | NSH | non repêché (585) | 11 | 30 | R15 | 0 | Pari établi | Fait l'équipe ; rythme de 50 en 18 matchs ; NHL 35 |
| **R16** | Ilya Protas | F | WSH | non repêché (621) | 9 | 42 | R10 | +6 | Caché | 3e centre à Washington ; recrue de l'année AHL |
| **R16** | T.J. Hughes | D | — | - | — | — | — | — | Caché | AN1 au Colorado ; absent du kit, vérifier dans PoolExpert |

**Gardiens** (absents de `draftkit-fr-p.xlsx`, donc ronde prévue « - ») :

| Ronde cible | Gardien | Ronde prévue | Pourquoi |
|---|---|---|---|
| **R9-10** | Linus Ullmark | - | G29 ; LdL 9e ; environ le 19e gardien du marché |
| **R10-11** | Jesper Wallstedt | - | G34 ; 72 à 80 pts pool en 1A (Gustavsson blessé) |
| **R12-13** | Stuart Skinner | - | G49 ; partant à Winnipeg pendant la grève de Hellebuyck |

**Équipes :** Ottawa (rondes 14-16, kit 28e) et Edmonton (JFresh 4e, kit 14e) ; Vegas en repli. Montréal subit la taxe CH.
<!-- HV:end -->

## Règles qui touchent la stratégie

- **16 rondes en serpent** (15 joueurs et 1 équipe) : ordre croissant aux rondes impaires, décroissant aux rondes paires. Tirage de l'ordre aujourd'hui à 15h00. Tu as 45 secondes par choix et un seul temps mort de 60 secondes : garde la feuille de référence ouverte.
- **Alignement actif :** au plus 8 attaquants, au moins 2 défenseurs, exactement 1 gardien et l'équipe. Les 4 autres joueurs sont au banc, et on peut faire 2 changements par semaine.
  - Avec 2 gardiens, il reste 3 places de banc pour les patineurs.
  - Un **3e défenseur** à 50 points ou plus joue à la place d'un attaquant, car l'attaquant de remplacement projette 42 points. Même au banc, il compte pour le boni de duo, puisque le règlement parle des défenseurs « sélectionnés », sur la glace ou non.
  - Un blessé de longue durée (Bedard, Terry, Fiala…) peut attendre au banc, puis entrer dans l'alignement à son retour.
- **Choix définitifs :** ni échange ni ballottage, seules les permutations entre l'alignement et le banc sont permises. Les 4 places du banc sont donc ta seule assurance pour toute la saison.
  - Il faut 2 gardiens qui jouent vraiment : il faut toujours un gardien actif, et on ne pourra pas en ajouter un en cours de saison.
  - Un joueur qui ne jouera jamais (un blessé pour la saison, un gardien en grève qui ne revient pas) bloque une place du banc pour de bon.
- **Pointage :** patineurs et équipe comme dans la LNH. Gardiens : points + 2 par victoire + 1 par nulle + 3 par blanchissage.
- **Bonus par duo de défenseurs :** 25, 15 et 10 points pour les trois meilleurs duos de défenseurs de la ligue.
  - Selon la simulation, il faut un duo projeté autour de 150 points ou plus pour avoir de vraies chances de le gagner : deux défenseurs pris aux rondes 1 et 2.
  - Un duo pris aux rondes 7-8 (environ 85 points) n'a pratiquement aucune chance.
- **Niveau de remplacement :** c'est la production du dernier joueur actif requis dans une ligue de 21 équipes.
  - Attaquant n° 168 : 42 pts (8 attaquants actifs × 21 équipes).
  - Défenseur n° 42 : 36 pts.
  - Gardien n° 21 : 59 pts pool.

## Feuille de référence : numéros de choix par position

| Pos. | R1 | R2 | R3 | R4 | R5 | R6 | R7 | R8 | R9 | R10 | R11 | R12 | R13 | R14 | R15 | R16 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | 1 | 42 | 43 | 84 | 85 | 126 | 127 | 168 | 169 | 210 | 211 | 252 | 253 | 294 | 295 | 336 |
| 2 | 2 | 41 | 44 | 83 | 86 | 125 | 128 | 167 | 170 | 209 | 212 | 251 | 254 | 293 | 296 | 335 |
| 3 | 3 | 40 | 45 | 82 | 87 | 124 | 129 | 166 | 171 | 208 | 213 | 250 | 255 | 292 | 297 | 334 |
| 4 | 4 | 39 | 46 | 81 | 88 | 123 | 130 | 165 | 172 | 207 | 214 | 249 | 256 | 291 | 298 | 333 |
| 5 | 5 | 38 | 47 | 80 | 89 | 122 | 131 | 164 | 173 | 206 | 215 | 248 | 257 | 290 | 299 | 332 |
| 6 | 6 | 37 | 48 | 79 | 90 | 121 | 132 | 163 | 174 | 205 | 216 | 247 | 258 | 289 | 300 | 331 |
| 7 | 7 | 36 | 49 | 78 | 91 | 120 | 133 | 162 | 175 | 204 | 217 | 246 | 259 | 288 | 301 | 330 |
| 8 | 8 | 35 | 50 | 77 | 92 | 119 | 134 | 161 | 176 | 203 | 218 | 245 | 260 | 287 | 302 | 329 |
| 9 | 9 | 34 | 51 | 76 | 93 | 118 | 135 | 160 | 177 | 202 | 219 | 244 | 261 | 286 | 303 | 328 |
| 10 | 10 | 33 | 52 | 75 | 94 | 117 | 136 | 159 | 178 | 201 | 220 | 243 | 262 | 285 | 304 | 327 |
| 11 | 11 | 32 | 53 | 74 | 95 | 116 | 137 | 158 | 179 | 200 | 221 | 242 | 263 | 284 | 305 | 326 |
| 12 | 12 | 31 | 54 | 73 | 96 | 115 | 138 | 157 | 180 | 199 | 222 | 241 | 264 | 283 | 306 | 325 |
| 13 | 13 | 30 | 55 | 72 | 97 | 114 | 139 | 156 | 181 | 198 | 223 | 240 | 265 | 282 | 307 | 324 |
| 14 | 14 | 29 | 56 | 71 | 98 | 113 | 140 | 155 | 182 | 197 | 224 | 239 | 266 | 281 | 308 | 323 |
| 15 | 15 | 28 | 57 | 70 | 99 | 112 | 141 | 154 | 183 | 196 | 225 | 238 | 267 | 280 | 309 | 322 |
| 16 | 16 | 27 | 58 | 69 | 100 | 111 | 142 | 153 | 184 | 195 | 226 | 237 | 268 | 279 | 310 | 321 |
| 17 | 17 | 26 | 59 | 68 | 101 | 110 | 143 | 152 | 185 | 194 | 227 | 236 | 269 | 278 | 311 | 320 |
| 18 | 18 | 25 | 60 | 67 | 102 | 109 | 144 | 151 | 186 | 193 | 228 | 235 | 270 | 277 | 312 | 319 |
| 19 | 19 | 24 | 61 | 66 | 103 | 108 | 145 | 150 | 187 | 192 | 229 | 234 | 271 | 276 | 313 | 318 |
| 20 | 20 | 23 | 62 | 65 | 104 | 107 | 146 | 149 | 188 | 191 | 230 | 233 | 272 | 275 | 314 | 317 |
| 21 | 21 | 22 | 63 | 64 | 105 | 106 | 147 | 148 | 189 | 190 | 231 | 232 | 273 | 274 | 315 | 316 |

Pour savoir si un joueur sera encore là à ton prochain choix, compare son rang kit à ton numéro de choix. Aux extrémités (positions 1-3 et 19-21), tu repêches deux fois presque de suite, puis tu attends environ 40 choix : prends ton joueur prioritaire au premier des deux choix.

## Précision des sources (saison 2025-26)

On a comparé 214 joueurs, en projections brutes et en rythme sur 82 matchs pour les 186 joueurs ayant disputé au moins 60 matchs.

| Source | Erreur moyenne (points bruts) | Biais (points bruts) | Erreur moyenne (rythme 82 PJ) | Corrélation (rythme) | Erreur de 10 pts ou moins |
|---|---|---|---|---|---|
| Fantrax | 12,8 | +5,6 | 10,9 | 0,80 | 52 % |
| Pool Pro | 12,9 | +6,2 | 10,7 | 0,81 | 55 % |
| ESPN | 13,6 | +6,6 | 11,5 | 0,77 | 51 % |
| **Moyenne des 3** | **12,6** | +6,2 | **10,5** | **0,82** | **56 %** |

Ce qu'on en retient :

- **La moyenne bat chaque source.** On utilise donc un consensus pondéré par la précision 2025-26. Les écarts entre sources étant faibles, les poids restent proches de l'égalité : Fantrax 35 %, HLM 33 % (poids neutre, faute d'historique), ESPN 32 %.
- **Toutes les sources surestiment d'environ 6 points par joueur**, à cause des matchs manqués. En rythme, l'erreur tombe à environ 1 point. Retire donc environ 6 points à toute projection pour obtenir une attente réaliste.
- **Seulement une projection sur deux tombe à 10 points près.** Les grosses surprises viennent des percées (Celebrini +37, Bouchard +25, Scheifele +25, Slafkovsky +19, Gauthier +17). Les grosses déceptions viennent des blessures (Hedman, Matthews, Dubois, Point, Huberdeau).
- **HLM, nouvelle source cette année, est la plus optimiste.** Elle se situe à +3,7 points au-dessus de Fantrax et d'ESPN en moyenne. C'est la source la plus haute dans 145 cas sur 232, et elle est deux fois plus dispersée (écart moyen de 6,9 points, contre 3,1 entre Fantrax et ESPN). Un plafond qui ne vient que de HLM est un scénario optimiste, pas une attente.
- Les vétérans de 32 ans et plus ont légèrement dépassé leur rythme projeté (+2,3 points) ; les jeunes étaient bien calibrés.

Dans les tableaux qui suivent, les « LdL F/HLM/ESPN » sont les trois projections 2026-27 de la Liste des listes. Le « consensus » en est la moyenne pondérée. Les « rondes gagnées » mesurent de combien de rondes le joueur devrait être repêché plus tôt si le marché croyait ta projection ou le consensus.

## Projections Dobber (source ajoutée)

Dobber n'a pas d'historique mesuré, et on n'a ses projections que pour 33 joueurs. Je l'utilise donc comme source de confirmation : un plafond est crédible quand Dobber et une autre source (HLM ou ESPN) le voient tous deux au-dessus du kit. Les « rondes gagnées » indiquent combien de rondes plus tôt le joueur partirait si le kit avait la projection de Dobber.

| Joueur | Éq. | Pos | Rang kit (ronde) | Kit (PJ) | Dobber (PJ) | Dobber − kit | LdL F/HLM/ESPN | Rondes gagnées | Lecture |
|---|---|---|---|---|---|---|---|---|---|
| Ivar Stenberg | SJS | LW | 375 (non repêché) | 24 (52) | 65 (79) | +41 | absent | 14,4 | Plan 61 et Dobber 65 : **rondes 10 à 12** |
| Gavin McKenna | TOR | LW | 191 (R10) | 42 (72) | 70 (82) | +28 | 42/64/42 | 6,6 | **HLM et Dobber** : à prendre **aux rondes 7 et 8** |
| Roman Kantserov | CHI | RW | 320 (R16) | 28 (49) | 55 (82) | +27 | absent | 9,8 | Plan 45 et Dobber 55 : **rondes 12 à 14** |
| **Anton Frondell** | CHI | C | 179 (R9) | 44 (71) | 65 (82) | +21 | 44/45/— | 5,0 | **Plan 62 et Dobber 65** ; 9 points en 12 matchs à 17:45 l'an dernier (rythme 62). **Ronde 8 ou 9** : HLM (45) ne le voit pas, donc il est moins visible que McKenna |
| Adam Fantilli | CBJ | C | 107 (R6) | 57 (81) | 79 (83) | +22 | 57/65/60 | 3,4 | **Priorité aux rondes 5 et 6** : HLM, ESPN et Dobber au-dessus |
| Simon Nemec | CGY | D | 384 (non repêché) | 24 (73) | 46 (78) | +22 | absent | 10,4 | **Défenseur sleeper** ; 26 points en 68 matchs, 19:40 de temps de glace |
| Matvei Michkov | PHI | RW | 146 (R7) | 51 (77) | 68 (83) | +17 | 51/60/55 | 4,2 | Diamant du plan confirmé : **prends-le en ronde 6** |
| Matt Coronato | CGY | LW | 186 (R9) | 43 (77) | 57 (82) | +14 | 43/50/48 | 3,9 | Confirmé : **ronde 8** |
| Mitch Marner | VGK | RW | 19 (R1) | 86 (82) | 99 (83) | +13 | 87/93/87 | 0,5 | En positions 19-21, rivalise avec un défenseur élite en ronde 1 |
| Logan Stankoven | CAR | C | 192 (R10) | 42 (77) | 54 (82) | +12 | 42/53/41 | 3,3 | HLM et Dobber : **ronde 9** |
| **Gabe Perreault** | NYR | RW | 251 (R12) | 35 (71) | 52 (79) | +17 | 37/50/— | 5,1 | **Trois sources** (HLM 50, Dobber 52, plan 57). Le moins cher des attaquants à plafond : **rondes 10-11** |
| Mikael Granlund | ANA | C | 129 (R7) | 53 (71) | 52 (72) | −1 | 55/55/57 | — | Aligné sur le kit : plancher (top 6, AN, capitaine), aucun avantage. 34 ans, 58 matchs l'an dernier |
| Gage Goncalves | TBL | C | 326 (R16) | 28 (67) | 39 (76) | +11 | absent | 5,3 | Pari de fin de repêchage (top 6 à Tampa) |
| JJ Peterka | BOS | RW | 137 (R7) | 53 (84) | 63 (82) | +10 | 53/58/54 | 2,8 | Valeur en ronde 7 |
| Mason McTavish | STL | C | 180 (R9) | 44 (75) | 53 (77) | +9 | 44/52/44 | 2,5 | HLM et Dobber : ronde 8 ou 9 |
| Luke Evangelista | NJD | RW | 134 (R7) | 53 (81) | 61 (81) | +8 | 53/62/51 | 2,4 | HLM et Dobber : ronde 7 |
| Noah Hanifin | VGK | D | 277 (R14) | 32 (75) | 40 (80) | +8 | absent | 3,4 | 3e défenseur tardif ; va avec Vegas |
| Quinn Hughes | MIN | D | 31 (R2) | 80 (76) | 87 (77) | +7 | 80/88/81 | 0,6 | Rythme de 93 : cible n° 1 du duo élite |
| Clayton Keller | UTA | RW | 16 (R1) | 90 (84) | 89 (82) | −1 | 91/92/93 | — | Toutes les sources autour de 90 : aucun écart de projection. L'avantage vient du marché (« souvent négligé », selon Dobber) et de sa santé (82 matchs l'an dernier, 88 points). **S'il glisse en ronde 2, saute dessus** |
| Juraj Slafkovsky | MTL | LW | 55 (R3) | 70 (84) | 80 (83) | +10 | 70/80/71 | 1,0 | HLM et Dobber à 80 ; 73 points en 82 matchs l'an dernier. **Taxe CH** : il partira en ronde 2 ou au début de la ronde 3, soit à sa vraie valeur. À prendre seulement s'il est encore là à ton choix de ronde 3 |
| John Carlson | TBL | D | 89 (R5) | 60 (75) | 68 (79) | +8 | 61/62/60 | 1,2 | 36 ans ; 60 points en 71 matchs (rythme 69). AN1 à Tampa devant Hedman. Visible (D11) : pas un sleeper, mais une bonne valeur en ronde 5-6 |
| Luke Hughes | NJD | D | 209 (R10) | 40 (72) | 47 (76) | +7 | 40/51/38 | 2,2 | **AN1 à la place de Hamilton** : monte en ronde 7 |
| **Shea Theodore** | VGK | D | 174 (R9) | 45 (70) | 61 (69) | +16 | 45/61/45 | 4,1 | **HLM et Dobber à 61** ; Dobber : « énorme valeur possible ». 1er défenseur de ta liste en ronde 7 |
| **Brandt Clarke** | LAK | D | 243 (R12) | 36 (78) | 48 (83) | +12 | absent | — | Plan 55 (AN1) ; 40 points en 82 matchs l'an dernier. **Le défenseur de ta liste le moins cher** : ronde 8 |
| Jamie Drysdale | PHI | D | 313 (R15) | 29 (75) | 36 (74) | +7 | absent | 3,8 | 180 minutes d'AN l'an dernier, percée possible |
| Zeev Buium | VAN | D | 355 (non repêché) | 26 (78) | 32 (78) | +6 | absent | 4,0 | Plancher ; plus s'il obtient l'AN1 |
| Jack Roslovic | TOR | RW | 237 (R12) | 36 (72) | 41 (77) | +5 | absent | 1,9 | Pari s'il reste avec Matthews et sur l'AN1 |
| Matthew Wood | NSH | RW | 295 (R15) | 30 (74) | 35 (74) | +5 | absent | 2,2 | Déjà essayé sur l'AN1 : pari de fin de repêchage |
| Brock Boeser | VAN | RW | 126 (R6) | 54 (77) | 58 (79) | +4 | 55/53/57 | 1,3 | Juste prix |
| Artemi Panarin | LAK | LW | 13 (R1) | 91 (81) | 94 (82) | +3 | 91/76/95 | 0,1 | Juste prix (HLM à 76 le freine) |
| Tim Stützle | OTT | C | 24 (R2) | 84 (82) | 87 (80) | +3 | 84/86/78 | 0,2 | Juste prix |
| Mikhail Sergachev | UTA | D | 109 (R6) | 56 (76) | 59 (79) | +3 | 56/66/56 | 0,9 | Juste prix |
| Mats Zuccarello (bl.) | LAK | RW | 114 (R6) | 55 (62) | 57 (68) | +2 | 55/50/55 | 0,4 | Pari santé |
| Celebrini, Pastrnak, Crosby, Kempe, Trocheck | | | 4 à 98 | | | 0 à +1 | | 0 | Dobber est d'accord avec le kit |
| Philip Broberg | STL | D | 286 (R14) | 31 (74) | 31 (74) | 0 | absent | 0 | **Aucun avantage** ; Dobber suggère plutôt Logan Mailloux (STL, rang 533) |
| Valeri Nichushkin | CBJ | LW | 123 (R6) | 54 (73) | 53 (69) | -1 | 55/54/59 | 0 | Pari santé |
| **Patrick Kane** | CHI | RW | 73 (R4) | 64 (74) | 53 (65) | **-11** | 64/48/58 | -2,6 | **À éviter** : HLM et Dobber sous le kit |

**Gardien :** Dobber donne 29 victoires en 56 matchs à Lukas Dostal (ANA), comme la Liste des listes (29), contre 27 au kit. Ça représente environ 63 pts pool au lieu de 59, un peu au-dessus du niveau de remplacement.

## Projections NHL.com (source ajoutée)

NHL.com projette 263 attaquants et 97 défenseurs (`data/NHL.com Projections 2026-2027.md`). Ses totaux sont en moyenne **5,3 points plus hauts que le kit** sur le top 250 (projection de saison complète, sans matchs manqués) : les écarts ci-dessous sont corrigés de ce biais. Le croisement complet est dans `scripts/sortie-nhl.md`.

La « visibilité » compte pour ton pool : le kit et la Liste des listes (HLM, ESPN) sont lus par tes adversaires, Dobber presque pas. NHL.com est gratuit, mais peu consulté par les poolers québécois.

**Attention : les projections de ton plan sont celles de NHL.com.** Sur les 38 joueurs communs, 30 ont exactement le même total ; seuls 8 défenseurs diffèrent (Ufko, Cagnoni, Buium, Drysdale, Parekh, Broberg, Andersson, Gritsyuk). NHL.com ne confirme donc pas ton plan : c'est la même source. Les confirmations ci-dessous ne comptent que HLM, ESPN et Dobber comme sources indépendantes.

### Paris du rapport : ce que NHL.com ajoute

| Joueur | Éq. | Rang kit (R) | Kit | NHL (= plan) | Sources indépendantes au-dessus du kit | Verdict |
|---|---|---|---|---|---|---|
| Ivar Stenberg | SJS | 375 (—) | 24 (52 PJ) | **61** | Dobber 65 | **Deux sources** (NHL et Dobber). Toujours absent de la LdL : caché pour tes adversaires. Rondes 12 à 14 |
| Logan Cooley | UTA | 130 (R7) | 53 | **80** | HLM 70, ESPN 67 | **Trois sources, le plus gros consensus des rondes 6-7 (environ 71).** Passe devant Michkov : prends-le en ronde 6 |
| Anton Frondell | CHI | 179 (R9) | 44 | 62 | Dobber 65 (HLM 45 non) | Deux sources : ronde 8 ou 9 |
| Gavin McKenna | TOR | 191 (R10) | 42 | 63 | HLM 64, Dobber 70 | Trois sources : rondes 7-8 |
| Logan Stankoven | CAR | 192 (R10) | 42 | 61 | Dobber 54, HLM 53 | Trois sources : monte en ronde 9 |
| Zach Benson | BUF | 190 (R10) | 42 | 61 | HLM 62 | Deux sources. **Sur l'AN1 à Buffalo** (Doan, Thompson, Benson, Quinn, Dahlin) : rondes 9-10 |
| Jackson Blake | CAR | 163 (R8) | 47 | 61 | HLM 68 | **Monte :** NHL.com liste Jarvis parmi les absents, donc plus de temps de glace pour Blake. Ronde 8 ou 9 |
| Gabe Perreault | NYR | 251 (R12) | 35 | 57 | Dobber 52, HLM 50 | Trois sources : rondes 10-11 |
| Brandt Clarke | LAK | 243 (R12) | 36 | 55 | Dobber 48 | Deux sources, plancher de 40 sur 82 matchs : ronde 8 |
| Shea Theodore | VGK | 174 (R9) | 45 | 57 | HLM 61, Dobber 61 | Trois sources : 1er défenseur de ta liste en ronde 7 |
| Adam Fantilli | CBJ | 107 (R6) | 57 | 68 | Dobber 79, HLM 65 | Confirmé, moins haut que Dobber |
| Bourque, Graf, Nazar, Doan | | 175-253 | 35-45 | 54-60 | HLM 50-61 | Deux sources chacun : attaquants de plafond des rondes 9 à 12 |
| Nemec, Cagnoni, Ufko | | 384-610 | 10-24 | 40 / 36 / 35 | Dobber (Nemec 46) | NHL.com a **baissé** Ufko (35 contre 50 dans ton plan) et Cagnoni (36 contre 40). Cohérent avec l'estimation réaliste de 30 à 40 |
| Kantserov | CHI | 320 (R16) | 28 | 45 | Dobber 55 | Deux sources, entre 45 et 55 |
| Konsta Helenius | BUF | 376 (—) | 24 (54 PJ) | 49 | aucune (absent de la LdL) | **Une seule source**, mais la nouvelle compte : il a fait l'équipe, au 2e trio avec McLeod et Norris, et sur l'AN2 ([The Hockey News](https://thehockeynews.com/nhl/buffalo-sabres/game-day/buffalo-sabres-lineup-vs-pittsburgh-penguins-in-preseason-finale)). Zucker (hernie) et Kulich sont blessés. Environ 40 à 45 points. Caché : **rondes 15-16**, pour ta signature |

### Sleepers que le rapport avait manqués

| Joueur | Éq. | Âge | Rang kit | Kit | NHL | HLM | ESPN | 2025-26 | Recommandation |
|---|---|---|---|---|---|---|---|---|---|
| **Victor Eklund** | NYI | 19 | 822 | **1 (1 PJ)** | 51 | **65** | 52 | 1 point en 1 match (LNH), 10 en 9 (AHL) | **Le plus gros trou du kit.** Il a gagné sa place : 3e trio avec Pageau et Heineman, et Barzal est blessé ([SI](https://www.si.com/nhl/islanders/onsi/news/victor-eklund-appears-to-have-secured-ny-islanders-roster-spot), [NY Post](https://nypost.com/2026/09/26/sports/victor-eklund-makes-roster-case-with-islanders-cuts-looming/)). Trois sources publiques à 51-65 alors que le kit l'ignore. Les lecteurs de HLM le verront : **rondes 12 à 14**, pas en 16 |
| **Matthew Schaefer** (D) | NYI | 19 | 86 (R5) | 61 | **72** | 65 | 61 | **59 en 82 PJ** à 18 ans | Défenseur 1 de rechange, comme Carlson : s'il est là en ronde 5 ou 6, prends-le. Probablement parti en ronde 4 avec la surenchère |
| **Ilya Protas** | WSH | 20 | 621 | 9 (33 PJ) | 44 | 33 | 53 | 4 en 4 (LNH) ; recrue de l'année de l'AHL (66 en 69) | Dans l'alignement de 23 comme 3e centre ([RMNB](https://russianmachineneverbreaks.com/2026/09/27/capitals-cut-19-players-opening-night-roster/)). Environ 40 points. Pari de ronde 16 seulement |
| Seth Jones (D) | FLA | 31 | 264 (R13) | 33 | 52 | 47 | 37 | 32 en 52 PJ (rythme 50) | **Monte :** NHL.com à 52 (ton plan reprend ce chiffre) et HLM à 47. Meilleur 2e défenseur de plan B que Nemec : rondes 10 à 12 |
| Brandon Montour (D) | SEA | 32 | 250 (R12) | 35 | 48 | 46 | 34 | 32 en 64 PJ (rythme 41) | 3e défenseur établi (le contraire d'un pari) : rondes 12 à 14 |
| Bobby McMann | SEA | 30 | 183 (R9) | 44 | 63 | 43 | 46 | 46 en 78 PJ | NHL.com seul : ne pas surpayer |
| Mackie Samoskevich | SEA | 23 | 312 (R15) | 29 | 51 | — | — | 32 en 77 PJ | NHL.com seul : dernier choix au mieux |

### Drapeaux rouges de NHL.com

- **Blessés ou absents selon NHL.com :** Seth Jarvis (rang 59, ronde 3), Troy Terry (85), Kevin Fiala (144), Owen Tippett (159). Ne les paie pas au prix du kit. Aussi marqués blessés : Bedard, Larkin, Barzal, Marchand, Rust et Faber (D).
- **Vétérans en déclin dans la « zone de flottement » des rondes 7-8 :** Toffoli (kit 53, NHL 44), Giroux (38 ans, kit 50, NHL 42), Wennberg (52 contre 45), Mantha (53 contre 48). Ce sont des attaquants à plancher… dont le plancher baisse. Évite-les.
- **Patrick Kane** (ronde 4) : NHL.com à 55, après HLM (48) et Dobber (53). Trois sources contre le kit (64).

### Ordre de ta liste de défenseurs en ronde 7, avec NHL.com

Consensus (moyenne de NHL corrigé, HLM, ESPN et Dobber, sans ton plan qui reprend NHL.com) : Theodore 55, Byram 50, Hutson 48, Luke Hughes 44 ; Clarke 51 mais deux rondes moins cher. NHL.com ne voit Luke Hughes qu'à 45, sous Hutson (51) et Byram (50). Nouvel ordre : **Theodore, Byram, Hutson, Luke Hughes**, puis Clarke en ronde 8.

## Objectif 1 : tes diamants cachés

### Attaquants (liste « breakout »)

| Joueur | Éq. | Rang kit (ronde) | Kit | Plan | LdL F/HLM/ESPN | Consensus | 2025-26 (rythme 82) | Rondes gagnées (plan / consensus) | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Porter Martone | PHI | 49 (R3) | 72 | 68 | 73/57/— | 65 | recrue | -0,4 / -1,1 | **Au prix du marché, pas un sleeper** |
| Trevor Zegras | PHI | 88 (R5) | 60 | 64 | 60/64/59 | 61 | 67 (68) | 0,7 / 0,2 | Plafond crédible, prix juste |
| Will Smith | SJS | 92 (R5) | 59 | 75 | 59/78/59 | 65 | 59 en 69 PJ (70) | 2,3 / 0,9 | **Confirmé** |
| Ivan Demidov (bl.) | MTL | 101 (R5) | 58 | 70 | 58/77/59 | 65 | 62 (62) | 2,3 / 1,3 | **Confirmé** (vérifier la blessure) |
| Marco Rossi | VAN | 145 (R7) | 51 | 54 | 51/56/57 | 55 | 35 en 50 PJ (57) | 1,0 / 1,0 | **Confirmé** |
| Matvei Michkov | PHI | 146 (R7) | 51 | 57 | 51/60/55 ; Dobber 68 | 55 | 51 (52) | 2,0 / 1,5 | **Confirmé (Dobber 68) : ronde 6** |
| Igor Chernyshov | SJS | 155 (R8) | 49 | 54 | 49/46/19 | 39 | 19 en 28 PJ (56) | 1,5 / -2,9 | Plafond crédible ; ESPN à 19 fait peur |
| Jack Quinn | BUF | 165 (R8) | 47 | 53 | 48/55/43 | 49 | 51 (51) | 1,8 / 0,3 | Plafond crédible, prix juste |
| Anton Frondell | CHI | 179 (R9) | 44 | 62 | 44/45/— | 44 | 9 en 12 PJ | 4,7 / 0 | Pari : ton plan seul |
| Matt Coronato | CGY | 186 (R9) | 43 | 53 | 43/50/48 ; Dobber 57 | 47 | 45 (46) | 2,8 / 1,0 | **Confirmé (Dobber 57) : ronde 8** |
| Zach Benson | BUF | 190 (R10) | 42 | 61 | 43/62/40 | 48 | 43 en 65 PJ (54) | 5,1 / 1,5 | **Confirmé** (plafond venant de HLM) |
| Yegor Chinakhov | PIT | 200 (R10) | 41 | 62 | 41/45/37 | 41 | 42 (48) | 5,7 / 0,1 | Pari : ton plan seul |
| Collin Graf | SJS | 225 (R11) | 37 | 54 | 37/50/38 | 42 | 46 (47) | 4,9 / 1,3 | **Confirmé** |
| Ilya Mikheyev | TBL | 244 (R12) | 36 | 55 | absent | — | 36 (38) | 6,2 / — | Pari : ton plan seul |
| Gabe Perreault | NYR | 251 (R12) | 35 | 57 | 37/50/— | 43 | 27 en 49 PJ (45) | 7,0 / 3,1 | Pari (seul HLM suit) |
| Mavrik Bourque | NSH | 253 (R13) | 35 | 55 | 30/52/39 | 40 | 41 (41) | 6,6 / 2,2 | **Confirmé** (valeur tardive) |
| Benjamin Kindel (bl.) | PIT | 256 (R13) | 35 | 45 | absent | — | 35 (37) | 4,0 / — | Pari |
| Matvei Gridin | CGY | 263 (R13) | 33 | 46 | absent | — | 20 en 37 PJ (44) | 4,6 / — | **Confirmé par le rythme** |
| Matt Savoie (bl.) | EDM | 278 (R14) | 32 | 49 | 33/45/39 | 39 | 37 (37) | 6,1 / 3,0 | **Confirmé** (valeur tardive) |
| Matthew Wood | NSH | 295 (R15) | 30 | 44 | absent ; Dobber 35 | — | 30 (35) | 5,5 / — | Pari ; essayé sur l'AN1 selon Dobber |
| Andrei Kuzmenko (bl.) | PIT | 304 (R15) | 29 | 44 | absent | — | 25 en 52 PJ (39) | 6,0 / — | Confirmé par le rythme, mais blessé |
| Roman Kantserov | CHI | 320 (R16) | 28 | 45 | absent ; **Dobber 55** | — | recrue | 7,0 / — | **Confirmé par Dobber : rondes 12 à 14** |
| Arseny Gritsyuk | NJD | 322 (R16) | 28 | 50 | absent | — | 31 en 66 PJ (39) | 8,3 / — | Pari |
| Ivar Stenberg | SJS | 375 (non repêché) | 24 (52 PJ) | 61 | absent ; **Dobber 65** | — | recrue | 13,9 / — | **Confirmé par Dobber** |
| Konsta Helenius | BUF | 376 (non repêché) | 24 | 49 | absent | — | recrue | 10,8 / — | **A fait l'équipe** : 2e trio et AN2 à Buffalo. Pari de rondes 15-16 (voir la section NHL.com) |
| Dalibor Dvorsky | STL | 409 (non repêché) | 22 | 42 | absent | — | 21 (24) | 10,4 / — | Pari, dernier choix |

À retenir :

- **Diamants confirmés par au moins une autre source et au rythme 2025-26 :** Will Smith et Demidov (ronde 5), Rossi et Michkov (ronde 7), Coronato et Benson (rondes 9-10), Graf (ronde 11), Bourque, Gridin et Savoie (rondes 13-14). Pour ceux-là, ton plan tient.
- **Dobber confirme aussi Stenberg (65), Kantserov (55), Michkov (68) et Coronato (57).** Avance Michkov en ronde 6 et Coronato en ronde 8 : les lecteurs de Dobber vont les voir.
- **Tes projections du plan (NHL.com) sont en moyenne bien au-dessus de toutes les autres sources.** Pour Frondell, Chinakhov, Mikheyev et Gritsyuk, aucune source ne va plus haut que 45 à 50 points. Ce sont des paris, pas des diamants : ne les prends pas avant leur rang kit.
  - Frondell et Chinakhov : pas avant les rondes 9-10.
  - Helenius et Dvorsky : ils ne seront probablement pas repêchés, donc garde-les pour tes 2-3 derniers choix. Helenius passe devant Dvorsky : il a fait l'équipe au 2e trio, avec l'AN2.
- **Stenberg (nouveau) :** avec Dobber à 65 et ton plan à 61, deux sources voient un joueur de niveau ronde 5. Seul le kit (24 points en 52 matchs) le voit bas, probablement par peur d'un retour en Europe ou d'un essai de 9 matchs.
  - Ceux qui suivent le kit ne le prendront pas, mais les lecteurs de Dobber, oui.
  - Prends-le **vers les rondes 10 à 12**, avant tes autres paris : c'est le plus gros potentiel de ta liste.
- **T.J. Hughes (COL, AN1) :** absent du kit et de toutes les listes, donc personne ne le prendra avant toi. Vérifie d'abord qu'il est sélectionnable dans PoolExpert. Si oui, c'est un choix de dernière ronde avec un vrai rôle sur un des meilleurs avantages numériques de la ligue.
- **Chernyshov :** ESPN le projette à 19 points (rôle incertain). Le consensus (39) est sous le kit (49). Évite-le avant la ronde 10.

### Défenseurs de ton plan

| Joueur | Éq. | Rang kit (ronde) | Kit (PJ) | Plan (AN) | LdL F/HLM/ESPN | Consensus | 2025-26 (rythme 82) | TG 2025-26 | Verdict |
|---|---|---|---|---|---|---|---|---|---|
| Rasmus Andersson | VGK | 171 (R9) | 46 (83) | 48 (Non) | 46/49/45 | 47 | 47 (48) | 23:12 | Au prix du marché |
| Thomas Harley | DAL | 197 (R10) | 41 (75) | 49 (PP2) | 41/48/42 | 44 | 36 en 70 PJ (42) | 23:03 | Plafond crédible |
| Bowen Byram | CHI | 204 (R10) | 41 (83) | 50 (Oui) | 41/55/51 | 49 | 42 (42) | 22:22 | **Confirmé (HLM et ESPN)** |
| Luke Hughes | NJD | 209 (R10) | 40 (72) | 45 (Oui) | 40/51/38 ; Dobber 47 | 43 | 35 en 68 PJ (42) | 23:01 | **Confirmé** : AN1 à la place de Hamilton (Dobber) |
| Brandt Clarke | LAK | 243 (R12) | 36 (78) | 55 (Oui) | absent | — | 40 (40) | 19:46 | Pari |
| Sam Malinski | COL | 255 (R13) | 35 (77) | 43 (Non) | absent | — | 40 (40) | 17:36 | Confirmé par le rythme |
| Seth Jones | FLA | 264 (R13) | 33 (71) | 52 (Oui) | 33/47/37 | 39 | 32 en 52 PJ (50) | 23:38 | **Confirmé** (rythme 50 avec les Panthers) |
| Philip Broberg | STL | 286 (R14) | 31 (74) | 48 (Oui) | absent ; Dobber 31 | — | 34 (34) | 23:22 | **Rejeté** : Dobber = kit ; Mailloux est le pari moins cher |
| Jamie Drysdale | PHI | 313 (R15) | 29 (75) | 45 (Oui) | absent ; Dobber 36 | — | 32 (34) | 21:36 | Pari appuyé : percée possible selon Dobber |
| Zeev Buium | VAN | 355 (non repêché) | 26 (78) | 40 (Oui) | absent ; Dobber 32 (plancher) | — | 26 (28) | 19:33 | Pari : plus s'il obtient l'AN1 |
| Zayne Parekh | CGY | 405 (non repêché) | 22 (61) | 40 (Oui) | absent | — | 9 en 37 PJ (20) | 17:06 | **Retiré :** Dobber préfère Nemec pour cette saison (Parekh pour le long terme). Les deux se disputent l'AN à Calgary |
| Ryan Ufko | NSH | 585 (non repêché) | 11 (34) | 50 (PP2) | absent | — | 11 en 18 PJ (50) | 13:46 | **Pari appuyé** : il fait l'équipe (Perbix et Lyubushkin au ballottage le 27 septembre). Environ 30 à 40 points sur une saison complète, plus si Josi (36 ans) manque des matchs |
| Luca Cagnoni | SJS | 610 (non repêché) | 10 (48) | 40 (Oui) | absent | — | 0 en 3 PJ | 18:00 | **Confirmé dans l'alignement (nouvelle du jour)** ; le kit est dépassé |

## Objectif 2 : anomalies statistiques (plancher solide, plafond bien au-delà du prix)

Critère : la projection la plus basse de la Liste des listes (le plancher) est au moins égale au kit, à 3 points près. La plus haute (le plafond) le dépasse d'au moins 8 points. Comme le kit reproduit Fantrax, le plancher correspond presque toujours au prix payé. Le risque est donc faible, et tout le potentiel au-dessus du kit est gratuit. Le signal est plus fort quand **HLM et ESPN** dépassent tous deux le kit de 5 points ou plus, ou quand le **rythme 2025-26** appuie le plafond.

### Plafond confirmé par deux sources (les plus fiables)

| Joueur | Éq. | Pos | Âge | Rang kit (ronde) | Kit (PJ) | LdL F/HLM/ESPN | Consensus | 2025-26 (rythme 82) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| J.T. Miller | NYR | C | 33 | 81 (R4) | 62 (72) | 62/70/69 | 67 | 53 en 68 PJ (64) | Le kit prévoit 10 matchs manqués |
| Evgeni Malkin | PIT | C | 40 | 83 (R4) | 61 (61) | 62/69/69 | 67 | 61 en 56 PJ (**89**) | Rythme élite ; seul le nombre de matchs limite |
| Brayden Point | TBL | C | 30 | 84 (R4) | 61 (69) | 61/76/73 | 70 | 50 en 63 PJ (65) | Rebond après une saison blessée |
| Dylan Holloway | STL | C | 25 | 91 (R5) | 59 (69) | 60/71/65 | 65 | 51 en 59 PJ (71) | Rythme appuie 70 points |
| Zach Hyman | EDM | RW | 34 | 115 (R6) | 55 (65) | 56/74/74 | 68 | 52 en 58 PJ (74) | **Meilleur rapport** : 2 sources à 74 |
| Matt Duchene (bl.) | DAL | C | 35 | 116 (R6) | 55 (65) | 55/62/77 | 64 | 45 en 57 PJ (65) | Blessé au départ, à mettre au banc |
| Roope Hintz | DAL | C | 29 | 117 (R6) | 55 (69) | 55/70/65 | 63 | 44 en 53 PJ (68) | Rythme 68 |
| Elias Pettersson | VAN | C | 27 | 121 (R6) | 55 (76) | 55/62/64 | 60 | 51 en 74 PJ (57) | Plafond modeste |
| Logan Cooley | UTA | C | 22 | 130 (R7) | 53 (73) | 55/70/67 | 64 | 43 en 54 PJ (65) | **Meilleur rapport aux rondes 7-8** |
| Kevin Fiala (bl.) | LAK | LW | 30 | 144 (R7) | 51 (68) | 51/60/69 | 60 | 40 en 56 PJ (59) | Retour fin octobre |
| Jackson Blake | CAR | RW | 23 | 163 (R8) | 47 (75) | 47/68/53 | 56 | 53 en 81 PJ (54) | A déjà produit 53 points |
| Bowen Byram | CHI | D | 25 | 204 (R10) | 41 (83) | 41/55/51 | 49 | 42 (42) | Défenseur, sur l'AN1 selon ton plan |
| Frank Nazar | CHI | C | 22 | 211 (R11) | 40 (79) | 40/58/46 | 48 | 41 en 66 PJ (51) | Bon profil pour la fin |
| Jonathan Huberdeau (bl.) | CGY | LW | 33 | 214 (R11) | 39 (70) | 39/54/46 | 46 | 25 en 50 PJ (41) | Risqué |
| Thomas Chabot | OTT | D | 29 | 235 (R12) | 36 (66) | 36/42/45 | 41 | 31 en 57 PJ (45) | Défenseur 3 tardif |
| Matt Savoie (bl.) | EDM | C | 22 | 278 (R14) | 32 (76) | 33/45/39 | 39 | 37 (37) | Valeur tardive |

### Plafond confirmé par HLM et Dobber (nouveau)

| Joueur | Éq. | Pos | Rang kit (ronde) | Kit | LdL F/HLM/ESPN | Dobber | Commentaire |
|---|---|---|---|---|---|---|---|
| Adam Fantilli | CBJ | C | 107 (R6) | 57 | 57/65/60 | **79** | Trois sources au-dessus du kit : **meilleur choix des rondes 5 et 6** |
| Matvei Michkov | PHI | RW | 146 (R7) | 51 | 51/60/55 | 68 | Diamant du plan : ronde 6 |
| Luke Evangelista | NJD | RW | 134 (R7) | 53 | 53/62/51 | 61 | Ronde 7 |
| JJ Peterka | BOS | RW | 137 (R7) | 53 | 53/58/54 | 63 | Ronde 7 |
| Matt Coronato | CGY | LW | 186 (R9) | 43 | 43/50/48 | 57 | Ronde 8 |
| Mason McTavish | STL | C | 180 (R9) | 44 | 44/52/44 | 53 | Ronde 8 ou 9 |
| Gavin McKenna | TOR | LW | 191 (R10) | 42 | 42/64/42 | **70** | Plus gros écart du groupe : **rondes 7 et 8** |
| Logan Stankoven | CAR | C | 192 (R10) | 42 | 42/53/41 | 54 | Ronde 9 |

### Plafond venant de HLM seulement, mais appuyé par le rythme 2025-26

| Joueur | Éq. | Pos | Rang kit (ronde) | Kit | LdL F/HLM/ESPN | 2025-26 (rythme 82) | Commentaire |
|---|---|---|---|---|---|---|---|
| Mark Stone | VGK | RW | 43 (R3) | 73 (62 PJ) | 71/81/80 | 73 en 60 PJ (**100**) | Rythme d'élite, seul le nombre de matchs inquiète |
| Leo Carlsson | ANA | C | 78 (R4) | 63 | 63/90/65 | 67 en 70 PJ (78) | Plus grand plafond de la liste (HLM à 90) |
| Charlie McAvoy (bl.) | BOS | D | 118 (R6) | 55 | 55/64/55 | 61 en 69 PJ (72) | Défenseur |
| Jake Sanderson (bl.) | OTT | D | 119 (R6) | 55 | 55/74/56 | 54 en 67 PJ (66) | Défenseur |
| Shayne Gostisbehere | CAR | D | 140 (R7) | 52 | 52/59/57 | 50 en 55 PJ (**75**) | Défenseur, rythme élevé |
| Zach Benson | BUF | LW | 190 (R10) | 42 | 43/62/40 | 43 en 65 PJ (54) | Diamant de ton plan |

### À ne pas surpayer (plafond venant uniquement de HLM, aucun autre appui)

- Newhook (rang 332, 27/52/—), Landeskog, Cowan, Doan, Eklund, Pinto. McKenna (Dobber 70), Theodore (Dobber 61) et Perreault (Dobber 52) sont sortis de cette liste.
- Ce sont des billets de loterie à prendre à leur rang kit ou plus tard.

### Sources en désaccord (plancher sous le kit)

- **Seth Jarvis** (69/**32**/68) : HLM intègre sa blessure. Le kit le place au rang 59 ; retour prévu entre fin octobre et début décembre.
- **Ovechkin** (69/48/68) : HLM croit au déclin.
- **Patrick Kane** (64/48/58) : HLM et maintenant **Dobber (53 en 65 matchs)** le voient sous le kit (64). Ne le prends pas au rang 73.
- **Protas** (49/33/53) et **Chernyshov** (49/46/19) : rôle incertain.
- **Porter Martone** (73/57/—) : le kit (72) est déjà au sommet de la fourchette.

## Objectif 3 : équipes sleepers et duos de gardiens

Une équipe rapporte des points au classement LNH (2 par victoire, 1 par défaite en prolongation). L'écart entre la 1re équipe (Caroline, 113 pts) et la 21e (environ 93 pts) est d'environ 20 points. **Les équipes que le kit sous-estime seront disponibles tard**, puisque tout le monde voit le même classement. Et comme seulement 21 des 32 équipes seront repêchées, il en restera toujours au moins 11 à la fin.

### Équipes sous-estimées par le kit (sleepers)

| Équipe | Rang kit | Pts kit | Rang plan | Pts plan | Séries plan | **JFresh** | Pts 2025-26 | Duo de gardiens (V kit / V LdL) |
|---|---|---|---|---|---|---|---|---|
| **Oilers** | 14 | 92 | 9 | 96,7 | 67 % | **105 (4e)** | 93 | Andersen 17 ; Jarry 13 / 19 (duo faible) |
| **Sénateurs** | 28 | 85 | 10 | 97,8 | 58 % | **95 (18e)** | 99 | Ullmark 21 / **29** ; Ersson 13 |
| **Golden Knights** | 13 | 98 | 4 | 101,1 | 79 % | **104 (5e)** | 95 | Hart 25 / 27 ; Hill 17 / 19 |
| **Canadiens** | 16 | 94 | 8 | 99,3 | 63 % | **99 (10e)** | 106 | Dobes 26 / 27 ; Fowler 10 / 15 |
| Kings | 26 | 89 | 21 | 90,6 | 47 % | 96 (14e) | 90 | Kuemper 22 ; Forsberg 16 / 17 |
| Blue Jackets | 20 | 91 | 16 | 93,8 | 46 % | 92 (20e) | 92 | Greaves 23 / 24 ; Talbot 8 |
| ~~Blues~~ | 24 | 89 | 13 | 94,9 | 56 % | 85 (28e) | 86 | Hofer 23 / 24 ; Binnington 16 |

### Projections de JFresh (classement 2026-27)

JFresh (hockeystats.com) donne une 3e source indépendante pour les équipes. Sa moyenne (94,1) est presque celle du kit (93,6), donc les écarts se comparent directement.

- **Edmonton, nouveau sleeper :** JFresh le place 4e (105), 13 points au-dessus du kit (92, 14e). C'est le plus gros écart de la ligue, et ton plan (96,7) va dans le même sens. L'équipe coûte plus cher qu'Ottawa (rang 14 au kit), mais projette environ 8 points de plus en moyenne entre JFresh et ton plan. Le duo de gardiens reste faible : prends l'équipe, pas le gardien.
- **Ottawa confirmé :** 95 chez JFresh, 97,8 dans ton plan, contre 85 au kit. Ça reste le meilleur rapport qualité-prix, puisque le kit le classe 28e.
- **Vegas (104) et Montréal (99) confirmés :** deux sources sur trois au-dessus du kit.
- **St. Louis retiré :** JFresh le voit 28e (85). Seul ton plan y croit ; ce n'est plus un repli.
- **Surestimées par le kit, confirmé par JFresh :** Islanders (89 contre 103 au kit), Dallas (101 contre 111), Buffalo (97 contre 106). Laisse-les aux autres.
- **Sources en désaccord :** Floride (JFresh 108, plan 94) et Toronto (JFresh 96, plan 87). Pas de pari.
- **Effet sur les gardiens :** JFresh confirme les équipes des gardiens visés, Minnesota (102) pour Wallstedt, New Jersey (96, contre 90 au kit) pour Allen et Ottawa (95) pour Ullmark. Il voit Winnipeg bas (89), ce qui confirme d'éviter l'équipe des Jets.

Recommandations :

1. **Ottawa est le meilleur sleeper.** Le kit les place 28e sur 32, alors qu'ils ont fait 99 pts la saison dernière et que ton plan les met 10e. Tu devrais pouvoir les prendre à l'un de tes 3 derniers tours. **Ullmark** suit la même logique : rang G29 au kit, mais 9e selon la Liste des listes Gardiens (28/30/29 victoires). Avec 29 victoires, il vaudrait environ 75 pts pool, soit le niveau d'un gardien top 7, au prix d'un substitut.
2. **Vegas et Montréal** sont des choix de milieu de repêchage à bon prix. Attention à la **taxe CH** : dans ton pool, Montréal (et Dobes) partiront probablement plus tôt que le kit ne le prévoit. Vegas est le meilleur prix des deux.
   - Vegas : rang kit 13, 4e dans ton plan. Duo Hart-Hill ; Hart projette 71 pts pool (8 nulles, 4 blanchissages au kit).
   - Montréal : rang kit 16, 106 pts la saison dernière. Duo Dobes-Fowler ; Dobes est 13e selon la Liste des listes Gardiens.
3. ~~**St. Louis** comme plan de repli tardif~~ : retiré, JFresh le voit 28e (85).
4. **Edmonton :** l'équipe est sous-estimée (JFresh 105, 4e), mais le duo Andersen-Jarry est faible. Prends l'équipe, pas le gardien.
5. **Prendre l'équipe et son gardien** (Ottawa avec Ullmark, Vegas avec Hart) double les points de chaque victoire. C'est un pari corrélé : plus de potentiel, mais plus de risque.

### Équipes surestimées par le kit (à laisser aux autres)

- Islanders : rang kit 6, mais 26e dans ton plan et 34 % de chances de séries.
- Sharks : 17e au kit contre 30e dans ton plan.
- Maple Leafs : 18e contre 29e.
- Ducks : 11e contre 20e.
- Panthers : 7e contre 15e.

### Gardiens : écarts à connaître

| Gardien | Éq. | Rang kit | V kit | V LdL (moy.) | Rang LdL | Pts pool proj. | Lecture |
|---|---|---|---|---|---|---|---|
| Linus Ullmark | OTT | G29 | 21 | 29 | 9 | 59 | **Sleeper** (voir Ottawa) |
| Igor Shesterkin | NYR | G21 | 24 | 28 | 11 | 60 | **Sleeper** ; HLM à 32 |
| Jesper Wallstedt | MIN | G34 | 18 | 26 (22/38/18) | 19 | 54 ; **environ 72 à 80 en 1A** (84 matchs) | **Sleeper confirmé** : Gustavsson est opéré à la hanche (retour vers novembre) |
| Filip Gustavsson (bl.) | MIN | G27 | 22 (35 PJ) | absent du top 40 | — | 53 | **À éviter** : blessé, et le kit lui donne encore les victoires d'un partant |
| Connor Hellebuyck (suspendu) | WPG | G9 | 27 | 25 | 21 | 76 (kit) ; 0 à 75 selon la date d'un échange | **Pari tardif seulement** : bon 2e gardien s'il est échangé avant la mi-décembre (voir plus bas) |
| Stuart Skinner | WPG (signé le 1er juillet) | G49 | 13 (25 PJ) | 25 (projeté comme partant à PIT) | 22 | 34 (réserviste) ; environ 60 comme partant | **Sleeper :** partant à Winnipeg pendant la grève de Hellebuyck |
| Sergei Murashov | PIT | G17 | 25 | absent | — | 64 | Le kit en fait le partant à Pittsburgh, devant Silovs |
| Arturs Silovs | PIT | G40 | 16 | 19 | 35 | 46 | **Retirer de ta liste** : réserviste selon le kit |
| Jake Allen | NJD | G18 | 25 | 23 | 27 | 61 ; **environ 66 à 68** sans Rittich | Rittich rétrogradé le 28 septembre : environ 53 matchs et 27-28 victoires. Ton plan (28) devient réaliste |
| Nico Daws | NJD | G75 | 4 (16 PJ) | absent | — | 12 ; environ 20 à 25 comme réserviste | Réserviste d'Allen : utile seulement si Allen se blesse |
| Yaroslav Askarov | SJS | G22 | 24 | 22 | 29 | 53 | Ton plan (25) est optimiste ; ESPN à 17 |

**Skinner, le vrai sleeper des gardiens :** il a signé à Winnipeg le 1er juillet. Le kit le traite en réserviste (25 matchs, 13 victoires), alors qu'il sera le partant tant que Hellebuyck est en grève.
- En 2025-26, il a obtenu 23 victoires, 9 nulles et 2 blanchissages en 50 matchs, soit 62 pts pool. C'est le niveau de Vladar ou d'Allen, pour un gardien classé 49e au kit.
- Comme personne ne le prendra avant la fin, choisis-le comme **gardien substitut entre les rondes 12 et 14**. Il peut même servir de gardien partant si la grève se prolonge.
- **Ne paie pas Hellebuyck au prix du kit** (9e gardien), mais c'est un bon pari tardif (voir ci-dessous).
- **Évite aussi l'équipe des Jets** : le kit compte 27 victoires de Hellebuyck dans leur projection.

**Hellebuyck, un pari de 2e gardien en fin de repêchage :**
- **Situation au 28 septembre :** il est suspendu depuis le 16 septembre pour ne pas s'être présenté au camp, et il n'est pas payé pendant sa suspension. Il lui reste 5 ans de contrat.
  - Le directeur général Kevin Cheveldayoff dit n'avoir « aucun échéancier » et n'avoir reçu aucune offre valable.
  - Destinations nommées : Buffalo, la Caroline et l'Utah selon Pierre LeBrun, puis San José, où les discussions bloquent sur Misa. Montréal dément tout intérêt ([TSN](https://www.tsn.ca/nhl/article/cheveldayoff-says-jets-will-continue-to-explore-trade-options-for-suspended-g-hellebuyck/), [CBC](https://www.cbc.ca/news/canada/manitoba/winnipeg-jets-hellebuyck-trade-9.7348026)).
  - Il ne produit rien tant qu'il n'est pas échangé ou revenu au jeu.
- **Valeur selon la date d'un échange** (équipe type : Buffalo, 65 % des départs, 1,50 pt pool par départ, scénario réaliste de 2 changements aux 2 semaines) :

| Échange le | Hellebuyck seul | Wallstedt + Hellebuyck | Ullmark + Hellebuyck | Skinner + Hellebuyck |
|---|---|---|---|---|
| 15 octobre | 75 | 103 | 94 | 94 |
| 1er novembre | 68 | 103 | 94 | 93 |
| 15 décembre | 50 | 98 | 89 | 87 |
| 1er février | 28 | 89 | 82 | 78 |
| Date limite des échanges (début mars) | 18 | 84 | 78 | 74 |
| Jamais | 0 | 80 | 72 | 68 |
| *Référence : Wallstedt + Allen = 93 ; Ullmark + Skinner = 88* | | | | |

- **Point d'équilibre vers la mi-décembre :**
  - Échangé avant, Hellebuyck bat Allen comme 2e gardien derrière Wallstedt, et Skinner derrière Ullmark.
  - Échangé après, il fait moins bien.
  - Mon estimation des chances, subjective : environ 50 % avant la mi-décembre, sa suspension sans salaire poussant à un règlement. L'espérance est donc à peu près la même qu'avec Allen (environ 93), avec beaucoup plus de variance.
- **Pourquoi il reste intéressant :**
  - **Il couvre le risque de Skinner.** S'il revient à Winnipeg, Skinner redevient réserviste, mais tu as récupéré le partant. S'il est échangé, les deux sont partants. S'il reste à la maison, Skinner joue.
  - **Mais le choix est définitif** : ni échange ni ballottage. S'il ne rejoue jamais, il bloque une des 4 places du banc toute la saison.
  - **Pire : si Wallstedt se blesse** et que Hellebuyck ne joue toujours pas, l'équipe n'a plus de gardien actif, alors qu'il en faut un au minimum. Avec Hellebuyck comme seul 2e gardien, ce risque est réel.
  - La version sûre est donc **Wallstedt + un vrai 2e partant (Allen, Blackwood) + Hellebuyck en 3e gardien**. Ça coûte 2 places de banc sur 4 aux gardiens. Ce n'est raisonnable que si Hellebuyck tombe en toute dernière ronde et que le reste du banc est déjà solide.
  - **Il coûte peu à Wallstedt.** En octobre et en novembre, Wallstedt joue 85 % des matchs (Gustavsson est blessé), donc le 2e gardien sert peu de toute façon.
- **Où le prendre :**
  - Seulement en fin de repêchage (rondes 14 à 16), jamais au rang G9 du kit. Des poolers qui suivent le kit pourraient le prendre bien avant, par réflexe.
  - Le meilleur endroit : **en 3e gardien, en toute dernière ronde**, dans l'équipe de Wallstedt ou dans celle de Skinner. Ne le prends pas comme seul gardien de réserve.

**Wallstedt, le deuxième sleeper des gardiens :**
- **La blessure est confirmée.** Gustavsson a été opéré à la hanche au début de l'été et ne sera pas prêt pour le camp. Selon The Athletic, son retour est prévu vers début novembre (rapporté par [RotoWire, 18 septembre](https://www.rotowire.com/hockey/headlines/filip-gustavsson-injury-expected-back-in-november-593284)). Bill Guerin précise que la hanche le gênait depuis bien avant les Jeux olympiques ([The Hockey News](https://thehockeynews.com/nhl/minnesota-wild/latest-news/filip-gustavsson-still-undergoing-physical-therapy-expected-to-miss-start-of-wilds-2026-27-nhl-season)).
- **Le kit est incohérent.**
  - Il réduit Gustavsson à 35 matchs, mais lui garde un taux de victoires de partant (22 en 35, soit 63 %).
  - Il donne à Wallstedt 18 victoires en 36 matchs (50 %), alors que Wallstedt a un meilleur taux d'arrêts (.915 contre .903 en 2025-26) et qu'il avait déjà pris des départs à Gustavsson en fin de saison.
  - Les deux jouent derrière la même équipe, projetée à 46 victoires.
- **Les sources divergent énormément** : Fantrax 22, HLM 38, ESPN 18. Gustavsson n'apparaît même pas dans le top 40 de la Liste des listes Gardiens, donc au moins une partie des sources a tenu compte de la blessure.
- **Estimation** (46 victoires pour Minnesota ; Pickard, à .871 l'an dernier, comme simple réserviste en octobre) :
  - Environ 10 départs en octobre, puis un partage 50/50 : **environ 43 matchs, 23 victoires, 65 pts pool**. Environ 14e gardien.
  - Environ 10 départs en octobre, puis 60 % des départs comme 1A : **environ 50 matchs, 27 victoires, 72 à 78 pts pool**. Entre le 5e et le 9e gardien, au niveau de Thompson, Swayman ou Hart.
  - Dans les deux cas, il dépasse le niveau de remplacement (59 pts pool), et le kit le classe 34e.
- **Où le prendre :**
  - Les poolers qui suivent le kit ne le verront pas.
  - Ceux qui suivent la Liste des listes le voient 19e.
  - Vise-le **quand les gardiens 15 à 20 de la Liste des listes commencent à partir**, et avant Skinner. Ensemble, ils feraient ton meilleur duo de gardiens à bas prix.
  - L'équipe du Wild (8e au kit, 7e dans ton plan) est payée au juste prix : ce n'est pas un sleeper.

**Colten Ellis (BUF) : utile quelques jours seulement.**
- Lyon (haut du corps, 24 septembre, « quelques jours ») et Luukkonen (bas du corps, 26 septembre, un « étirement ») sont blessés, sans échéancier ([Buffalo Hockey Beat](https://www.buffalohockeybeat.com/ukko-pekka-luukkonen-leaves-game-injured-as-sabres-end-preseason/)). Ellis devrait donc amorcer la saison le 1er octobre à Columbus.
- L'an dernier, il a gagné 8 matchs avec un taux d'arrêts de .903 en 16 matchs. Buffalo est une équipe forte (106 pts au kit), donc environ 1,5 pt pool par départ.
- Mais les deux blessures semblent mineures. Ellis ne devrait obtenir que 3 à 5 départs de plus que son rôle de 3e gardien : **environ 25 à 30 pts pool sur la saison**, loin derrière Skinner ou Allen.
- Un podcast local lie aussi les Sabres à Hellebuyck. Si Buffalo le prend, Ellis perd toute valeur, mais Skinner reste le partant à Winnipeg pour toute la saison.
- **Verdict :** à prendre en toute dernière ronde seulement, et seulement si une équipe a une place de banc libre. Comme il n'y a ni échange ni ballottage, un choix d'Ellis bloque une place de banc toute la saison pour environ 25 à 30 pts : mieux vaut un attaquant ou un défenseur de réserve. Vérifie aussi à partir de quelle date les points comptent : l'an dernier, l'alignement devait être déposé le 8 octobre. Si c'est encore le cas, la courte fenêtre d'Ellis pourrait être passée avant que ton alignement compte.

**Deuxième gardien et changements : deux régimes possibles.**

Selon le point 2.3, les changements prennent effet le lundi et comptent du lundi au dimanche, à raison de 2 par semaine. En pratique, l'an dernier, PoolExpert a permis des changements en libre-service **n'importe quel jour**, pris en compte le lendemain s'ils étaient faits avant la réinitialisation quotidienne (vers 3 h, à confirmer). La limite restait de 2 par semaine. Ça change la valeur d'un 2e gardien.

- **Si le règlement est appliqué à la lettre (changements le lundi seulement) :** le gardien actif l'est pour toute la semaine. Un réserviste de la même équipe (Daws derrière Allen) ne sert qu'en cas de blessure. Un 2e partant d'une autre équipe permet au moins de choisir chaque lundi le gardien qui a le plus de départs probables.
- **Si le libre-service quotidien est encore toléré :** un aller-retour se fait en 2 changements. Tu actives le 2e gardien pour une fenêtre de jours où ton partant ne joue pas, puis tu reviens au partant. Ça utilise toute la limite de la semaine.
  - **Réserviste de la même équipe (Allen, puis Daws au 2e match d'un aller-retour) :**
    - Le réserviste joue presque toujours le 2e match d'un aller-retour, c'est prévisible.
    - Mais ça ne se produit que 12 à 15 fois par saison.
    - Daws est faible : environ 1 pt pool par départ.
    - **Gain : environ 12 à 15 pts pool par saison.** Sa valeur autonome est nulle.
  - **Deux partants de deux équipes différentes (Wallstedt et Allen, ou Wallstedt et Skinner) :**
    - Presque chaque semaine, il y a une ou deux soirées où l'équipe de ton gardien actif ne joue pas et où l'autre équipe joue, y compris les soirs où ton partant se repose au 2e match d'un aller-retour.
    - Le 2e partant rapporte environ 1,3 à 1,4 pt pool par départ, mais il faut qu'il soit le partant ce soir-là (environ 65 % des cas).
    - Si tu en profites une semaine sur deux ou trois, **le gain est d'environ 20 à 30 pts pool par saison**.
    - En plus, tu as un vrai gardien de remplacement en cas de blessure.
  - **Attention :** les attaquants blessés ou en panne utilisent aussi ces 2 changements. Le jeu des gardiens se fait seulement les semaines où tu n'en as pas besoin ailleurs.
- **Conclusion : mieux vaut un 2e partant d'une autre équipe** que le réserviste de ton propre gardien, peu importe le régime. Daws ne vaut une place sur le banc qu'à la toute fin, si ton banc n'a rien de mieux.

**Simulation des duos avec le vrai calendrier 2026-27** (84 matchs, calendrier de la LNH ; script `scripts/gardiens.js`)

La simulation cherche la meilleure séquence de changements pour toute la saison, en points pool attendus. Chaque changement prend effet le lendemain.

Elle couvre 31 gardiens et 489 duos. Les gardiens élites (Vasilevskiy, Oettinger, Sorokin, Bussi, Vejmelka, Thompson, Swayman, Saros, Hellebuyck) sont exclus, parce qu'ils partent trop tôt. Le classement complet est dans `scripts/sortie-gardiens.md`.

Hypothèses :
- **Pts pool par départ :** ceux du kit.
- **Part des départs :** celle du kit, ajustée à mi-chemin vers les victoires de la Liste des listes Gardiens, avec un maximum de 75 %.
- **Au 2e match d'un aller-retour**, le partant joue 20 % du temps.
- **Ajustements selon les nouvelles :**
  - Wallstedt : 85 % des départs jusqu'au 5 novembre, puis 58 %.
  - Gustavsson : absent jusqu'en novembre.
  - Allen 63 % et Daws 37 %, avec Rittich rétrogradé.
  - Skinner 65 %, partant pendant la grève de Hellebuyck.
  - Kuemper 50 %, en alternance possible avec Forsberg.
  - Jarry : il partage les départs avec Levi, puis Andersen revient fin octobre.
  - Dostal : pts par départ = moyenne du kit et de Dobber.

Colonnes :
- **Soirs décalés** : nombre de soirs où une seule des deux équipes joue.
- **Lundi seulement** : le règlement à la lettre.
- **Quotidien réaliste** : 2 changements aux 2 semaines, en laissant l'autre moitié aux attaquants.
- **Quotidien max** : 2 changements chaque semaine, tous pour les gardiens.

Gardiens seuls, en pts pool sur 84 matchs :
- **Wallstedt : 80**
- **Hart : 76**
- **Ullmark et Wedgewood : 72**
- **Bobrovsky : 71**
- **Dostal : 69**
- **Gibson et Skinner : 68**
- **Allen et Shesterkin : 67**
- Murashov et Markstrom : 66
- Vladar, Luukkonen et Hofer : 63 à 64
- Greaves : 59
- **Kuemper : 53**
- **Askarov : 52**
- **Jarry : 34**
- Daws : 30

**Duos avec Wallstedt (le meilleur rapport qualité-prix)**

| Duo | Rangs kit | Rangs LdL | Soirs décalés | Meilleur seul | Lundi seulement | Quotidien réaliste | Quotidien max |
|---|---|---|---|---|---|---|---|
| Wallstedt + Hart | G34 / G16 | 19 / 18 | 68 | 80 | 87 | **98** | 101 |
| Wallstedt + Wedgewood | G34 / G10 | 19 / 16 | 76 | 80 | 87 | 97 | 105 |
| Wallstedt + Ullmark | G34 / G29 | 19 / 9 | 66 | 80 | 85 | 96 | 103 |
| Wallstedt + Bobrovsky | G34 / G19 | 19 / 14 | 74 | 80 | 84 | 96 | 104 |
| Wallstedt + Dostal | G34 / G13 | 19 / 10 | 76 | 80 | 84 | 95 | 101 |
| Wallstedt + Shesterkin | G34 / G21 | 19 / 11 | 80 | 80 | 83 | 94 | 101 |
| Wallstedt + Skinner | G34 / G49 | 19 / 22 | 70 | 80 | 83 | 94 | 98 |
| Wallstedt + Allen | G34 / G18 | 19 / 27 | 56 | 80 | 83 | 93 | 97 |
| Wallstedt + Greaves | G34 / G25 | 19 / 25 | 66 | 80 | 82 | 92 | 97 |

**Duos sans Wallstedt (pour le 2e pool, ou si Wallstedt part avant ton tour)**

| Duo | Rangs kit | Rangs LdL | Soirs décalés | Meilleur seul | Lundi seulement | Quotidien réaliste | Quotidien max |
|---|---|---|---|---|---|---|---|
| Ullmark + Shesterkin | G29 / G21 | 9 / 11 | 86 | 72 | 79 | **90** | 99 |
| Wedgewood + Bobrovsky | G10 / G19 | 16 / 14 | 84 | 72 | 78 | 89 | 99 |
| Ullmark + Allen | G29 / G18 | 9 / 27 | 74 | 72 | 79 | 87 | 95 |
| Dostal + Markstrom | G13 / G11 | 10 / 23 | 84 | 69 | 74 | 85 | 93 |
| **Skinner + Blackwood** | G49 / G23 | 22 / 20 | 88 | 68 | 74 | 84 | 92 |
| Gibson + Dobes | G14 / G15 | 17 / 13 | 68 | 68 | 73 | 83 | 90 |
| Allen + Murashov | G18 / G17 | 27 / — | 68 | 67 | 72 | 83 | 89 |
| Shesterkin + Kuemper | G21 / G26 | 11 / — | 86 | 67 | 69 | 81 | 87 |
| Dostal + Jarry | G13 / G50 | 10 / 34 | 86 | 69 | 69 | 77 | 80 |
| Hofer + Askarov | G24 / G22 | 24 / 29 | 68 | 63 | 65 | 75 | 77 |
| Allen + Daws | G18 / G75 | 27 / — | 0 | 67 | 67 | 72 | 74 |

Ce qu'on en retient :
- **Wallstedt est la pièce maîtresse** : environ 80 pts pool seul sur 84 matchs, et 92 à 98 avec n'importe quel 2e partant.
- **Ce que vaut un 2e gardien :**
  - Il rapporte surtout grâce aux soirs décalés et à sa valeur autonome.
  - Deux gardiens de valeur semblable (Ullmark + Shesterkin, Ullmark + Allen) rapportent le plus, parce que le meilleur choix de la semaine change souvent.
  - Un gardien de l'Est avec un gardien de l'Ouest donne en général plus de soirs décalés (84 à 88).
- **Couvrir le risque Daws :**
  - Si Daws prend le poste en janvier, Allen seul chute à environ 55.
  - Posséder Daws n'en récupère que 6 à 8.
  - Un 2e partant d'une autre équipe en récupère environ 25.
- **Ajouter Daws comme 3e gardien** ne rapporte que 1 à 3 pts, pour une 2e place de banc bloquée. Ça ne vaut le coup qu'en dernière ronde.
- **Duos à éviter :**
  - **Jarry** : il partage avec Levi en octobre, puis il est menacé d'être envoyé dans la Ligue américaine quand Andersen revient.
  - **Askarov** : San José est faible, et le kit ne lui donne aucun blanchissage.
  - **Kuemper** : il a 36 ans et a perdu son poste au profit de Forsberg en fin de saison. Vérifie qui sera partant le soir du repêchage.
- **Attention aux noms connus :** Shesterkin, Bobrovsky et Markstrom partent souvent plus tôt que leur projection, simplement à cause de leur réputation.

### Deux équipes dans le même pool (la tienne et celle de ta blonde) : répartir 4 gardiens

Les deux équipes ne peuvent pas avoir les mêmes gardiens. La simulation compare toutes les façons de former deux duos sans gardien en commun, parmi les gardiens abordables. Le prix approximatif est la moyenne du rang au kit et du rang dans la Liste des listes : plus il est élevé, moins le gardien coûte cher.

| Ensemble | Équipe 1 | Équipe 2 | Total des deux duos |
|---|---|---|---|
| Idéal (Hart coûte un peu plus cher) | Wallstedt + Murashov ou Markstrom (94-95) | Hart + Ullmark (92) | 186-187 |
| **Recommandé** | **Wallstedt + Allen, Murashov ou Markstrom (93-95)** | **Ullmark + Skinner (88)** | **181-183** |
| Autre option | Wallstedt + Skinner (94) | Ullmark + Allen (87) | 181 |
| Tout à bas prix (sans Ullmark ni Hart) | Wallstedt + Blackwood (94) | Skinner + Allen (83) | 177 |

- **L'essentiel : Wallstedt et Ullmark doivent être dans deux équipes différentes.**
  - Le choix du 2e gardien de chaque équipe ne fait varier le total que de 2 à 5 pts.
  - Prends donc ces deux-là en priorité, puis complète avec le gardien le moins cher parmi Allen, Skinner, Murashov, Markstrom et Blackwood.
- **Ordre de priorité :**
  - Wallstedt d'abord, avec l'équipe qui arrive la première au moment de prendre un gardien.
  - Ullmark ensuite, avec l'autre équipe, à son prochain choix. Il est 9e dans la Liste des listes, donc les poolers qui la suivent risquent de le prendre avant les lecteurs du kit.
  - **Skinner** (G49 au kit) peut attendre les rondes 12 à 14 pour l'une ou l'autre équipe.
  - **Allen** ou **Blackwood** comme 4e gardien.
  - **Variante avec Hellebuyck :** s'il est encore là en toute dernière ronde, ajoute-le **en 3e gardien** dans l'équipe de Wallstedt, en plus d'Allen ou de Blackwood. Pas à leur place : les choix sont définitifs, et une blessure à Wallstedt pendant la grève laisserait l'équipe sans gardien.
- **Murashov :** le kit en fait le partant à Pittsburgh, mais il est absent de la Liste des listes Gardiens, qui place Silovs à Pittsburgh. Vérifie qui sera partant avant de le prendre. Allen est plus sûr.
- **Deux positions dans l'ordre du repêchage :**
  - En serpentin, l'équipe qui choisit tôt dans une ronde choisit tard dans la suivante.
  - Aux rondes où tes deux choix sont rapprochés, prends les deux cibles d'un même type l'une après l'autre (deux gardiens, deux sleepers).
  - Aux rondes où ils sont éloignés, fais prendre la cible la plus rare à l'équipe qui choisit en premier.
- **Les autres sleepers se partagent aussi :**
  - **Équipes :** Ottawa pour l'une, Edmonton ou Vegas pour l'autre (Montréal en repli).
  - **Défenseurs de la ronde 7 :** Byram pour l'une, Cole Hutson pour l'autre.
  - **Défenseurs tardifs :** Cagnoni pour l'une, Nemec pour l'autre. Ufko pour l'équipe qui a encore une place de banc en ronde 16.
  - **Attaquants tardifs :** Stenberg et Kantserov, un de chaque côté.
  - Chaque équipe peut viser son propre boni de duo de défenseurs, mais il n'y a pas assez de défenseurs élites en rondes 1 et 2 pour les deux si vos positions sont proches.
- **Allen gagne de la valeur** avec la rétrogradation de Rittich : Daws (3 matchs dans la LNH l'an dernier) est un réserviste plus faible, donc Allen devrait jouer environ 53 matchs. À 27-28 victoires, il vaut environ 66 à 68 pts pool, au niveau d'un gardien classé 12e ou 13e.

Ta liste de gardiens pour les rondes 7-11 : Saros (70 pts pool) est le seul nettement au-dessus du niveau de remplacement (59). Vladar, Allen, Hofer, Blackwood et Luukkonen tournent autour de 58 à 61 pts. Ajoute Ullmark, Shesterkin et Hart, qui valent autant ou mieux, souvent moins cher. Retire Silovs. Kuemper (G26, 63 pts pool, absent de la Liste des listes) est un bon substitut tardif.

## Objectif 4 : défenseurs (bonus de duo, surenchère et rondes 6 à 8)

Plages de choix : ronde 6 = choix 106 à 126, ronde 7 = 127 à 147, ronde 8 = 148 à 168.

### Le bonus de duo et le dos à dos : ce que dit la simulation

Pour vérifier ta stratégie du dos à dos, j'ai simulé le repêchage complet des patineurs sur 14 rondes (les 16 rondes, moins l'équipe et un gardien), pour chaque position et chaque stratégie. Chaque repêchage est ensuite joué sur 4 000 saisons simulées (script `scripts/duo.js`).

**Comment les autres poolers repêchent.** Ils suivent le kit, mais surpaient les défenseurs. Deux intensités sont testées :

- **Modéré :** environ 8 points de surenchère, soit 32 défenseurs partis à la fin de la ronde 8.
- **Fort :** environ 14 points de surenchère, soit 43 défenseurs partis à la fin de la ronde 8 (2 par pooler).

**Ce qu'on mesure pour toi.** Tu prends tes deux défenseurs aux rondes indiquées et le meilleur attaquant disponible partout ailleurs. On calcule deux choses :

- les points projetés de ton alignement actif (10 patineurs, dont au plus 8 attaquants) ;
- l'espérance du bonus de duo (25, 15 ou 10 points). Pour le calculer, chaque saison simulée fait varier les points réels autour de la projection, avec la marge d'erreur mesurée en 2025-26.

**Défenseurs déjà repêchés à la fin de chaque ronde**

| Fin de ronde | R1 | R2 | R3 | R4 | R5 | R6 | R7 | R8 | R9 | R10 | R12 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Kit neutre | 1 | 5 | 7 | 9 | 15 | 19 | 22 | 25 | 28 | 32 | 44 |
| Surenchère modérée | 4 | 7 | 10 | 16 | 22 | 25 | 28 | 32 | 38 | 46 | 65 |
| Surenchère forte | 5 | 9 | 17 | 22 | 26 | 30 | 35 | 43 | 53 | 62 | 79 |

**Résultat selon ta position**

Le tableau compare trois stratégies : deux défenseurs aux rondes 1 et 2, deux défenseurs aux rondes 7 et 8, et la meilleure des sept stratégies testées. L'« écart » est la différence en points, alignement et bonus compris, avec cette meilleure stratégie.

| Position | Meilleure stratégie (modéré) | Duo typique aux rondes 1-2 | Chances de gagner le bonus avec ce duo (modéré) | Écart rondes 1-2 (modéré / fort) | Écart rondes 7-8 (modéré / fort) |
|---|---|---|---|---|---|
| 1 | Rondes 3-4 (Dahlin + Sergachev) | Bouchard + Dahlin (161) | 50 % | -25 / -20 | -6 / 0 |
| 2 | Rondes 2-3 (Dahlin + Raddysh) | Bouchard + Dahlin (161) | 51 % | -21 / -18 | -4 / 0 |
| 3 | Rondes 2-3 (L. Hutson + Raddysh) | Bouchard + L. Hutson (162) | 51 % | -20 / -15 | -6 / -4 |
| 6 | Rondes 1-2 | Bouchard + L. Hutson (162) | 50 % | 0 / -0,5 | -12 / -4 |
| 11 | Rondes 1-2 | Makar + L. Hutson (154) | 34 % | 0 / 0 | -8 / -4 |
| 16 | Rondes 1-2 | Werenski + Fox (157) | 36 % | 0 / 0 | -14 / -9 |
| 19 | Rondes 1-2 (19 et 24) | Werenski + Fox (157) | 37 % | 0 / -2 | -15 / -3 |
| 20 | Rondes 1-2 (20 et 23) | Q. Hughes + Fox (156) | 34 % | 0 / -3 | -16 / -4 |
| 21 | Rondes 1-2 (21 et 22, dos à dos) | Q. Hughes + Fox (156) | 34 % | 0 / -3 | -19 / -2 |

Comment lire ces résultats :

- **Positions 19 à 21 : ta stratégie du dos à dos est validée.**
  - Avec une surenchère modérée, c'est la meilleure option.
  - Avec une surenchère forte, elle fait jeu égal : écart de 3 points, ce qui reste dans la marge d'erreur.
  - Un duo élite a environ 1 chance sur 3 de gagner les 25 points, et environ 2 sur 3 de finir dans les trois premiers.
  - Cible : Werenski, Q. Hughes, Fox, ou Makar s'il glisse.
- **Positions 6 à 16 :** deux défenseurs élites aux rondes 1 et 2 reste la meilleure option, ce qui correspond au Plan A de ta stratégie pour les choix 15 à 25.
- **Positions 1 à 3 : prends l'attaquant élite.** Deux défenseurs aux rondes 1 et 2 coûtent de 15 à 25 points. Si tu veux quand même viser le bonus, le virage des rondes 2 et 3 (choix 40 à 45) avec Dahlin, Hutson ou Raddysh donne environ 13 % de chances de le gagner, sans rien coûter.
- **Attendre jusqu'aux rondes 7 et 8 pour tes deux premiers défenseurs est la pire option dès la position 6** si la surenchère est modérée (de 8 à 19 points de moins). Sans duo élite, les rondes 6 à 8 servent plutôt à trouver ton 1er ou ton 2e défenseur quand tu es en position 1 à 5.
- **Limites :** la simulation ignore les choix de gardiens et d'équipes, et les autres poolers y repêchent de façon prévisible. Un écart de moins de 5 points ne veut rien dire.

### Disponibilité des défenseurs avec la surenchère (compteur)

**Pendant le repêchage, compte les défenseurs déjà choisis.** Avec la surenchère, le n-ième défenseur du kit part environ une ronde plus tôt que son rang kit :

- s'il y a déjà plus de 25 défenseurs de partis quand arrive ta ronde 6, tu es dans le scénario fort ;
- s'il y en a environ 20, tu es proche du kit neutre.

| Rang D | Défenseur | Rang kit | Choix estimé (neutre / modéré / fort) |
|---|---|---|---|
| 16-19 | Sergachev, Seider, McAvoy, Sanderson | 109-119 | 112-122 / 84-90 / 62-68 |
| 20 | Jackson LaCombe | 135 | 137 / 96 / 76 |
| 21 | Shayne Gostisbehere | 140 | 142 / 100 / 82 |
| 23-25 | Dobson, Faber, Hronek | 157-161 | 157-161 / 115-121 / 91-96 |
| 26-28 | Andersson, Theodore, Dunn | 171-178 | 171-178 / 134-145 / 102-107 |
| 29-30 | Harley, Ekholm | 197-202 | 203-204 / 163-164 / 125-126 |
| 31 | Bowen Byram | 204 | 205 / 165 / 127 |
| 32-33 | Cole Hutson, Luke Hughes | 206-209 | 210-211 / 168-169 / 135-136 |
| 36-38 | Hamilton, Ekman-Larsson, Sanheim | 218-232 | 223-232 / 181-188 / 153-159 |
| 39 | Thomas Chabot | 235 | 242 / 195 / 164 |
| 42 | Brandt Clarke | 243 | 245 / 198 / 167 |
| 46 | Sam Malinski | 255 | 258 / 207 / 173 |
| 50 | Seth Jones | 264 | 265 / 224 / 186 |
| 61 | Philip Broberg | 286 | 289 / 241 / 206 |
| 67 | Jamie Drysdale | 313 | — / 261 / 223 |

**Correction par rapport à ma première version :** avec la surenchère, ta liste pour les rondes 7-8 (Byram, Harley, Luke Hughes, Andersson, puis Clarke) correspond au marché réel de ton pool. Les vrais paris à garder pour la fin sont Cagnoni et Nemec, suivis de Drysdale, Hanifin, Buium, Parekh et Ufko (voir plus bas). Dobber rétrograde Broberg.

La « projection retenue » dans les tableaux suivants est la moyenne du kit et du consensus de la Liste des listes.

### Défenseurs de premier plan à saisir s'ils glissent

Avec la surenchère, ces défenseurs partent normalement dès les rondes 3 à 5. Prends-en un en ronde 6 seulement s'il est encore là.

| Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | Proj. retenue | 2025-26 (rythme 82) | Pourquoi |
|---|---|---|---|---|---|---|---|---|
| **Matthew Schaefer** | NYI | 19 | 86 | 61 | 61/65/61 ; **NHL 72** | 65 | 59 en 82 PJ (59) | Recrue de 18 ans à 59 points ; NHL.com le voit 5e défenseur de la ligue. Même logique que Carlson : prends-le s'il glisse en ronde 5 ou 6 |
| **John Carlson** | TBL | 36 | 89 | 60 | 61/62/60 ; **Dobber 68**, NHL 65 | 61 | 60 en 71 PJ (69) | **Dobber le voit 8 points au-dessus du kit** : AN1 à Tampa. S'il est là en ronde 6, prends-le avant Michkov |
| Miro Heiskanen | DAL | 27 | 94 | 59 | 59/68/60 | 61 | 63 en 77 PJ (67) | Probablement parti ; à saisir s'il glisse |
| Roman Josi | NSH | 36 | 93 | 59 | 59/61/63 | 60 | 55 en 68 PJ (66) | Idem ; l'âge est un risque |
| Jake Sanderson (bl.) | OTT | 24 | 119 | 55 | 55/74/56 | 58 | 54 en 67 PJ (66) | Plus haut plafond (HLM à 74) ; vérifier la blessure |
| Charlie McAvoy (bl.) | BOS | 28 | 118 | 55 | 55/64/55 | 57 | 61 en 69 PJ (72) | Rythme de 72 la saison dernière |
| Mikhail Sergachev | UTA | 28 | 109 | 56 | 56/66/56 | 58 | 59 en 78 PJ (62) | Stable |
| Moritz Seider | DET | 25 | 113 | 56 | 56/66/56 | 58 | 60 en 82 PJ (60) | Stable, 82 matchs |

### Ronde 6, s'ils sont encore là (ils partent normalement en ronde 5)

| Rang | Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | Proj. retenue | 2025-26 (rythme 82) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Jackson LaCombe | ANA | 25 | 135 | 53 | 53/66/52 | 55 | 58 en 82 PJ (58) | Le plus sûr : 58 points, 82 matchs |
| 2 | Shayne Gostisbehere | CAR | 33 | 140 | 52 | 52/59/57 | 54 | 50 en 55 PJ (**75**) | Plus gros potentiel ; spécialiste de l'AN |
| 3 | Brock Faber | MIN | 24 | 158 | 49 | 49/58/48 | 50 | 51 en 80 PJ (52) | **Blessé selon NHL.com** : vérifie avant de le prendre |
| 4 | Noah Dobson | MTL | 26 | 157 | 49 | 49/51/53 | 50 | 47 en 80 PJ (48) | Sources unanimes, faible risque |
| À éviter | Victor Hedman | TBL | 35 | 141 | 52 | 52/**39**/51 | 50 | 17 en 33 PJ (42) | Âge et saison blessée ; HLM le voit à 39 |

### Ronde 7 : ta liste, au prix du marché

| Rang | Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | Proj. retenue | 2025-26 (rythme 82) | Plan (AN) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | **Shea Theodore** | VGK | 31 | 174 | 45 | 45/61/45 ; **Dobber 61 en 69 PJ** | 53 | 39 en 70 PJ (46) | — | **Monté au 1er rang :** HLM et Dobber à 61 (rythme de 72) ; Dobber lui voit une « énorme » valeur. À 61, le kit le classerait vers le 87e rang (environ 4 rondes plus tôt). Risque : 69-70 matchs par saison. Part vers le choix 134-145 selon le scénario fort |
| 2 | Bowen Byram | CHI | 25 | 204 | 41 | 41/55/51 ; NHL 50 | 50 | 42 (42) | 50 (Oui) | Quatre sources à 50-55. Bedard est absent en début de saison, ce qui réduit ses passes au départ. Part au choix 127 selon le scénario fort |
| 3 | **Cole Hutson** | WSH | 20 | 206 (D32) | 40 **en 63 PJ** | 40/50/— ; NHL 51 | 48 | 10 en 14 PJ (59) | — | Dobber pense qu'il prendra l'AN1 **plus tard dans la saison**, donc pas au départ. Plancher réaliste d'environ 45, plafond de 60 et plus |
| 4 | **Luke Hughes** | NJD | 23 | 209 | 40 | 40/51/38 ; Dobber 47 ; NHL 45 | 44 | 35 en 68 PJ (42) | 45 (Oui) | AN1 à la place de Hamilton, mais NHL.com (45) et ESPN (38) le voient plus bas que Byram et Hutson |
| 5 | Rasmus Andersson | VGK | 29 | 171 | 46 | 46/49/45 | 46 | 47 en 81 PJ (48) | 48 (Non) | Plancher sûr, mais en concurrence avec Theodore pour l'AN à Vegas : ne prends pas les deux |
| 6 | Thomas Harley | DAL | 25 | 197 | 41 | 41/48/42 | 42 | 36 en 70 PJ (42) | 49 (PP2) | Plafond crédible |
| — | Filip Hronek | VAN | 28 | 161 | 48 | 48/44/50 | 48 | 49 en 82 PJ (49) | — | S'il reste : plancher stable, équipe faible |

### Ronde 8 : deuxième défenseur ou 3e défenseur

| Rang | Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | 2025-26 (rythme 82) | Plan (AN) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Le reste de la liste de la ronde 7 | | | | | | | | Harley et Luke Hughes partent vers les choix 163-169 selon le scénario modéré |
| 2 | **Brandt Clarke** | LAK | 23 | 243 | 36 | absent ; **Dobber 48** | 40 en 82 PJ (40) | 55 (Oui) | **Monté :** Dobber (48) et ton plan (55) au-dessus du kit, AN1, et un plancher de 40 sur 82 matchs. Équivalent de Byram, deux rondes moins cher au kit. Part au choix 167 selon le scénario fort |
| 3 | Thomas Chabot | OTT | 29 | 235 | 36 | 36/42/45 | 31 en 57 PJ (45) | — | ESPN à 45 ; va avec l'équipe Ottawa |
| 4 | **Seth Jones** | FLA | 31 | 264 | 33 | 33/47/37 ; **NHL 52** | 32 en 52 PJ (50) | 52 (Oui) | **Monté :** NHL.com et ton plan à 52, rythme de 50. Meilleur 2e défenseur de plan B que Nemec (rondes 10-12) |
| 5 | Sam Malinski | COL | 28 | 255 | 35 | absent | 40 (40) | 43 (Non) | Stable, sans AN |

### Rondes 10 et plus : paris sur les jeunes de l'AN1

- **Luca Cagnoni (SJS) : confirmé aujourd'hui dans l'alignement**, sur l'AN1 selon ton plan (40 points).
  - Le kit (10 points, rang 610) est dépassé : ceux qui s'y fient ne le verront pas.
  - Les poolers à l'affût des nouvelles et en manque de défenseurs, eux, oui.
  - Cible : **rondes 10 à 12**, comme 3e défenseur à potentiel.
- **Simon Nemec (CGY) : nouveau sleeper révélé par Dobber.**
  - Dobber le voit à 46 points en 78 matchs, contre 24 au kit (rang 384).
  - Il a fait 26 points en 68 matchs la saison dernière, avec 19:40 de temps de glace.
  - Personne ne le prendra avant la ronde 12. Cible : **rondes 11 à 13**, juste après Cagnoni.
  - **Dobber tranche le débat Nemec-Parekh :** « long terme, Parekh ; cette saison, Nemec ». Ton pool se joue sur une saison : prends Nemec, et jamais les deux, puisqu'ils se disputent le même temps d'AN à Calgary.
- **Drysdale** (D 67, vers la ronde 13) : Dobber l'estime à 36 points et voit une percée possible après 180 minutes d'AN l'an dernier. Il remplace Broberg comme pari de la ronde 13.
- **Noah Hanifin (VGK)** : Dobber l'estime à 40 points (kit 32, rang 277). C'est un 3e défenseur tardif qui va bien avec l'équipe Vegas.
- **Broberg : rétrogradé.** Dobber l'estime à 31, exactement comme le kit, donc aucun avantage. Dobber suggère plutôt **Logan Mailloux** (STL, rang 533, 15 points au kit), à prendre en dernière ronde.
- **Ryan Ufko (NSH) : il fait l'équipe.**
  - Nashville a placé Perbix et Lyubushkin au ballottage le 27 septembre, et Barron a été réclamé par St. Louis. Ufko est l'un des 7 défenseurs retenus, avec Josi, Skjei, Hague, Wilsby, Ahcan et Trudeau ([SI](https://www.si.com/nhl/predators/onsi/news/nashville-places-two-experienced-defensemen-waivers)).
  - Le kit ne lui donne que 34 matchs (11 points, rang 585). L'an dernier, il a fait 11 points en 18 matchs, soit un rythme de 50, en jouant seulement 13:46 par match.
  - Sur une saison complète, sur le 2e avantage numérique : environ **30 à 40 points**. Plus si Josi, qui a 36 ans, manque des matchs, parce qu'Ufko serait alors le candidat naturel pour le premier avantage numérique.
  - **Risque :** les 6 M$ libérés sous le plafond salarial pourraient servir à acquérir un défenseur, qui le repousserait au 7e rang.
  - **Rang parmi les paris en défense :** 3e, derrière Nemec (Dobber 46, 19:40 de temps de glace) et Cagnoni (AN1 à San José). Il ne battra pas tes 2 premiers défenseurs pour le boni, et il ne jouera à la place d'un attaquant que s'il dépasse 42 points. Sa valeur, c'est l'assurance en cas de blessure et le potentiel de percée.
  - Cible : rondes 15 et 16 comme 3e défenseur ; rondes 13 et 14 s'il devient ton 2e défenseur (voir le plan B ci-dessous).
- **Buium** (plancher de 32 selon Dobber, plus s'il obtient l'AN1) **et Parekh :** derniers choix seulement. Parekh seulement si Nemec est déjà parti, puisqu'ils sont en concurrence à Calgary.
- **T.J. Hughes (COL, AN1)** : absent du kit, donc dernière ronde. Vérifie d'abord qu'il est sélectionnable dans PoolExpert.

### Plan B : rien de ta liste en rondes 7 et 8

Ta méthode habituelle : 6 attaquants en rondes 1 à 6, puis tes défenseurs en rondes 7 et 8. Si ta liste est vide, tu continues avec des attaquants et tu vas chercher tes défenseurs en fin de repêchage.

- **Le calcul tient.** La surenchère fait descendre les attaquants : dans le scénario fort, environ 17 défenseurs de plus que le kit sont partis au choix 168.
  - Un attaquant en ronde 7 ou 8 vaut environ 50 points, contre 45 pour Byram ou Luke Hughes.
  - En rondes 11 à 13, l'attaquant disponible vaut environ 40 points. Nemec (Dobber 46) le bat, Cagnoni (40) l'égale et Ufko (30 à 40) est un peu en dessous.
  - Bilan : environ +10 points avec Nemec, +5 avec Cagnoni, à peu près nul avec Ufko. Le gain est réel, mais le risque est plus élevé.
- **Aucune perte de boni.** Un duo Byram et Hutson ne rivalise pas non plus avec les 3 meilleurs duos de la ligue (défenseurs élites des rondes 1 et 2).
- **Le vrai risque : les choix sont définitifs.** Tes 2 défenseurs actifs sont obligatoires. Si l'un s'écroule (Ufko renvoyé au 7e rang par un échange, par exemple), tu ne peux pas le remplacer. Il te faut donc **3 défenseurs tardifs**, et le 3e prend une de tes 3 places de banc.
- **Ordre pour le rôle de 2e défenseur (le plancher compte) :** Clarke d'abord s'il est encore là en ronde 9 (Dobber 48, 40 points en 82 matchs l'an dernier : le contraire d'un pari), puis Seth Jones (NHL.com 52, HLM 47, rythme de 50), Nemec, Montour (NHL 48), Hanifin (Dobber 40, vétéran stable), Cagnoni, Ufko, Drysdale. Ufko est acceptable comme 2e défenseur s'il est jumelé à Nemec ou Hanifin, pas à Cagnoni (deux paris).
- **Signal à surveiller :** compte les défenseurs repêchés à la fin de la ronde 6. S'il y en a 35 ou plus, les autres poolers affamés iront chercher Cagnoni et Nemec plus tôt. Avance alors Nemec aux rondes 9 et 10. Ufko peut attendre les rondes 13 et 14, puisque le kit le cache (rang 585).
- **Deux équipes :** il n'y a pas 6 défenseurs tardifs crédibles pour deux équipes qui vont toutes les deux en fin de repêchage. Si une équipe applique le plan B, l'autre devrait prendre sa liste des rondes 7 et 8.

### Règle de décision aux rondes 7 et 8

La question n'est pas « qui projette le plus », mais « qui ne sera plus là à mon prochain choix ». Classe chaque candidat selon deux critères : potentiel (upside) et visibilité (le kit et les listes publiques le voient-ils ?).

| | Visible (tout le monde le voit) | Caché (kit très bas) |
|---|---|---|
| **Potentiel** | McKenna (HLM 64), Theodore (HLM 61), Coronato (HLM 50, ESPN 48) : **prends-les maintenant**. Frondell est à mi-chemin : seul Dobber et ton plan le voient haut (HLM 45), mais c'est un 3e choix au total connu ; ronde 8 ou 9 | Stenberg (kit 375), Kantserov (320), Nemec (384), Cagnoni (610), Ufko (585) : **attends** |
| **Plancher seulement** | Peterka, Evangelista (kit R7, 53) : **zone de flottement** | Sans intérêt |

1. Un attaquant à potentiel visible est là : prends-le, il ne reviendra pas.
2. Sinon, un défenseur de ta liste est là : prends-le. Les défenseurs partent en surenchère, alors que les attaquants à plancher glissent : il y aura un équivalent de Peterka ou Evangelista (environ 50) plus tard.
3. Sinon, un attaquant à plancher.
4. Ne dépense jamais une ronde 7 ou 8 sur un joueur caché : c'est ton avantage, il sera encore là aux rondes 10 à 14.

- **Positions 20-21 :** tes choix des rondes 7 et 8 sont dos à dos (146-149). Prends un défenseur de ta liste et un attaquant à potentiel visible, et le dilemme disparaît.
- **Positions 1-2 :** ce sont tes rondes 6 et 7 (125-128) et 8 et 9 (167-170) qui sont dos à dos, avec environ 40 choix d'attente entre les deux paires. Le défenseur de ta liste ne tiendra pas 40 choix : prends-le en ronde 7 s'il est là.
- **Au milieu,** environ 20 choix séparent tes deux choix : applique la règle ci-dessus à chaque choix.

### Rondes 9 à 11 : attaquants à plafond

Avec la surenchère sur les défenseurs, les attaquants classés entre les rangs 165 et 260 du kit glissent vers les rondes 9 à 12. Ceux dont le plafond est appuyé par au moins deux éléments parmi HLM, ESPN, Dobber, ton plan et le rythme 2025-26 (Doan n'a que HLM comme source externe : ne le surpaie pas) :

| Joueur | Éq. | Âge | Rang kit | Kit | Sources au-dessus | 2025-26 (rythme 82) | Lecture |
|---|---|---|---|---|---|---|---|
| Zach Benson | BUF | 21 | 190 | 42 | HLM 62, plan 61 | 43 en 65 PJ (54) | Le meilleur plafond appuyé du groupe |
| Josh Doan | BUF | 24 | 175 | 45 | HLM 61 | 52 en 82 PJ (52) | Plancher de 52 déjà atteint, 82 matchs |
| Matt Coronato | CGY | 23 | 186 | 43 | Dobber 57, plan 53, HLM 50 | 45 en 80 PJ (46) | Trois sources ; ronde 8 ou 9 |
| Frank Nazar | CHI | 22 | 211 | 40 | HLM 58, ESPN 46 | 41 en 66 PJ (51) | Plafond ; même équipe que Frondell et Kantserov |
| **Gabe Perreault** | NYR | 21 | 251 | 35 | **Dobber 52**, plan 57, HLM 50 | 27 en 49 PJ (45) | Trois sources ; le moins cher du groupe |
| Logan Stankoven | CAR | 23 | 192 | 42 | Dobber 54, HLM 53 | 44 en 81 PJ (45) | Sûr, plafond modéré |
| Mavrik Bourque | NSH | 24 | 253 | 35 | plan 55, HLM 52 | 41 en 82 PJ (41) | 82 matchs ; peut glisser en ronde 12 |
| Collin Graf | SJS | 24 | 225 | 37 | plan 54, HLM 50 | 46 en 81 PJ (47) | Plancher de 46, 81 matchs |
| Josh Norris | BUF | 27 | 207 | 40 | HLM 49 | 34 en 44 PJ (63) | Rythme de 63, mais historique de blessures |

Évite d'empiler trois Sabres (Benson, Doan, Norris) ou trois Blackhawks (Frondell, Nazar, Kantserov) dans la même équipe.

### Leçons du repêchage simulé de Dobber (multi-catégories, 14 équipes, 16 rondes)

Dobber repêchait 9e sur 14. Ses choix, comparés au rang du kit :

| Choix | Joueur | Rang kit | Écart |
|---|---|---|---|
| 9 | Robertson | 10 | = |
| 20 | Necas | 9 | glissé de 11 |
| 37 | Reinhart | 52 | devancé de 15 (rebond de la Floride, JFresh 108) |
| 48 | Guenther | 54 | = |
| 65 | Fox | 41 | glissé de 24 |
| 76 | Bratt | 38 | glissé de 38 |
| 93 | Aho | 28 | **glissé de 65** |
| 104 | C. Hutson | 206 | **devancé de 102** |
| 121 | Clarke | 243 | **devancé de 122** |
| 132 | Byram | 204 | devancé de 72 |
| 149 | Fantilli | 107 | glissé de 42 |
| 160 | Malinski | 255 | devancé de 95 |
| 177 | Peterka | 137 | glissé de 40 |
| 188 | Cozens | 103 | glissé de 85 |
| 15e-16e rondes | Hofer, Askarov | G24, G22 | Zéro gardien |

- **Ta liste de défenseurs est celle d'un expert.** Hutson, Clarke et Byram aux rondes 8 à 10 : exactement ta liste. Aux choix 104 à 132, ce serait les rondes 5 à 7 d'un pool de 21, mais **peu de poolers de ton pool lisent Dobber** (projections sur X, guide payant). Le marché de ton pool, c'est le kit et la Liste des listes : Clarke (kit 36, absent de la LdL) reste un choix de ronde 8.
- **Dobber est un avantage privé.** Les joueurs que seul Dobber voit au-dessus du kit sont les plus sûrs d'attendre : Clarke, Nemec, Carlson, Stenberg, Kantserov, et Frondell (HLM 45 seulement). Ceux que HLM voit aussi (McKenna 64, Theodore 61, Benson 62) sont visibles pour tes adversaires.
- **Les attaquants établis glissent quand les experts chassent le potentiel :** Aho, Bratt, Fox, Peterka, Cozens et même Fantilli sont partis de 24 à 85 rangs après le kit. Ça confirme la règle : les attaquants à plancher reviennent plus tard, les défenseurs de ta liste non.
- **Fantilli au choix 149 :** il peut se rendre à ta ronde 6 ou 7. Garde-le en ronde 6, pas en ronde 5. Dobber mentionne une « saga Marchenko » à Columbus : à vérifier.
- **Nouvelles tirées des commentaires :** Bedard est absent en début de saison (Byram baisse ; Frondell et Nazar gagnent du temps de glace au départ). Cozens devrait profiter du départ de Brady Tkachuk à Ottawa.
- **Le zéro gardien ne s'applique pas à ton pool.** En multi-catégories avec ballottage, les gardiens se remplacent. Chez toi, sans ballottage, Hofer + Askarov ne vaut que 75 pts pool contre 94 pour Wallstedt + Skinner. Par contre, ça confirme que les experts trouvent les gardiens bon marché : Skinner en ronde 12-13 tient.
- Contexte : multi-catégories (tirs, mises en échec, admissibilité LW/RW) et ballottage disponible. Seuls les défenseurs offensifs et le comportement du marché se transposent à ton pool.

### Ton gabarit de 16 choix

| Rondes | Choix | Cibles |
|---|---|---|
| 1-6 | 6 attaquants | Cooley (R6, consensus 71), Fantilli (R6), Michkov (R6-7) ; Schaefer ou Carlson (D) s'ils glissent en R5-6 |
| 7-8 | Défenseurs 1 et 2, ou un défenseur et un attaquant à potentiel visible | Theodore, Byram, C. Hutson, Luke Hughes, Clarke ; McKenna, Frondell, Blake |
| 9-11 | **Gardien 1** et 2 attaquants à plafond | Ullmark (R9-10) ou Wallstedt (R10-11) ; Stankoven, Benson, Doan, Coronato, Nazar, Perreault |
| 12-13 | **Gardien 2** et un joueur établi ou un sleeper appuyé | Skinner ; Victor Eklund, Graf, Bourque, ou Seth Jones, Montour en défense |
| 14-15 | Équipe et 3e défenseur caché | Ottawa ou Edmonton ; Nemec, Cagnoni, Ufko |
| 16 | Ta signature : l'attaquant caché | Stenberg (s'il est encore là), Helenius (2e trio et AN2 à Buffalo), Kantserov, Ilya Protas, T.J. Hughes |

Total : 10 attaquants, 3 défenseurs, 2 gardiens, 1 équipe. Le banc : 2 attaquants (l'établi et le caché), 1 défenseur, 1 gardien.

- **Le gardien 1 ne peut pas attendre la ronde 12.** Selon le prix (moyenne du rang kit et du rang LdL), Ullmark est environ le 19e gardien du marché et Wallstedt le 26e ou 27e : ils partent vers les rondes 9 à 12. Skinner (environ le 35e) se rend aux rondes 12 à 14.
- **Duos réalistes avec ce gabarit (régime réaliste, 84 matchs) :**
  - Wallstedt + Skinner : 94.
  - Ullmark + Skinner : 88.
  - Ullmark + Knight, Greaves ou Hofer : 84, si Skinner est déjà pris (par ton autre équipe).
  - Ullmark + Allen : 87, mais Allen (environ le 22e) doit être pris en ronde 11.
- **Wallstedt n'est plus un secret** (le beau-père est au courant). S'il repêche entre deux de tes choix, prends Wallstedt au plus tard en ronde 9. S'il te le vole, Ullmark + Skinner (88) ne coûte que 6 points : ne panique pas en ronde 7 ou 8 pour autant.
- **Deux équipes :** Skinner ne va qu'à une seule équipe. Équipe A : Wallstedt + Skinner (94). Équipe B : Ullmark + Knight ou Greaves (84), ou Ullmark + Allen (87) si tu peux prendre Allen en ronde 11.

### Répartition des 16 choix (par équipe)

Un alignement complet compte 15 joueurs et l'équipe : 10 patineurs actifs (au plus 8 attaquants, au moins 2 défenseurs), 1 gardien, l'équipe et 4 joueurs au banc. Avec 2 gardiens, il reste **3 places de banc pour les patineurs**. Comme les choix sont définitifs, il n'y a de la place que pour 3 paris de fin de repêchage par équipe, soit 6 pour tes deux équipes.

| Rondes | Positions 19-21 (dos à dos) | Positions 1-5 |
|---|---|---|
| 1-2 | 2 défenseurs élites | Attaquant élite, puis attaquant |
| 3-8 | 6 attaquants (Fantilli en R5-6, Michkov en R6, McKenna et Frondell en R7-8) | Défenseur 1 (R3-4), attaquants, défenseur 2 (R6-7 : LaCombe, Byram, C. Hutson) |
| 8-11 | Gardien 1 (Wallstedt ou Ullmark) ; 7e et 8e attaquants (Coronato, Stankoven, McTavish) | Gardien 1 ; attaquants |
| 11-13 | Gardien 2 (Allen, Blackwood), ou Skinner plus tard | Gardien 2 |
| 13-16 | Équipe (Ottawa) si elle n'est pas prise ; Skinner ; 2 ou 3 paris | Idem |

- **Trie les paris** : tu n'en auras que 3 par équipe. Ma priorité : Stenberg (Dobber 65), Kantserov (Dobber 55), Nemec ou Cagnoni (défenseur de réserve qui compte pour le boni), puis Ufko ou T.J. Hughes s'il est sélectionnable.
- **Laisse tomber les paris faibles** (Goncalves, Wood, Roslovic, Drysdale, Buium, Parekh, Mailloux, Ellis, Daws), sauf s'il te reste un choix en ronde 16 sans meilleure option.
- **Hellebuyck** : seulement si l'équipe a déjà ses 2 gardiens et qu'il reste une place de banc libre en ronde 15 ou 16.
- **L'équipe (Ottawa)** : vise les rondes 14 à 16. Si Ottawa semble convoité, prends-le en ronde 13.

### Ordre suggéré selon ta position

1. **Positions 19-21 (dos à dos) :** deux défenseurs élites aux rondes 1 et 2, parmi Werenski, Q. Hughes (Dobber 87), Fox et Makar. Seule alternative crédible en ronde 1 : Marner (Dobber 99). Ensuite, pas besoin de défenseur aux rondes 6 à 8 : ton 3e défenseur peut attendre Byram ou Luke Hughes en ronde 7 s'ils sont encore là, sinon Cagnoni ou Nemec aux rondes 10 à 13. Le 3e défenseur ne joue que s'il bat un attaquant à 42 points, mais même au banc il compte pour le boni de duo. Utilise tes rondes 5 à 8 pour les attaquants appuyés par Dobber : Fantilli, Michkov, Peterka ou Evangelista, McKenna, puis Coronato.
2. **Positions 6-18 :** même logique si deux défenseurs élites tombent à tes choix des rondes 1 et 2. Sinon, un défenseur élite en ronde 1, puis Byram, Andersson ou Harley en ronde 7.
3. **Positions 1-5 :** attaquant élite en ronde 1. Défenseur 1 en ronde 3 ou 4 (Dahlin, Raddysh, Carlson, Josi, Heiskanen), défenseur 2 en ronde 6 ou 7 (LaCombe, Gostisbehere, Faber, Byram), défenseur 3 aux rondes 10 à 13 (Cagnoni, Nemec, Chabot, Clarke).

## Leçons de ton pool 2025-26 (5e)

| Groupe | Joueurs (points 2025-26, matchs) | Lecture |
|---|---|---|
| Noyau d'attaquants | Guentzel 88 (81), Draisaitl 97 (65), Carlsson 67 (70), Stamkos 66 (82), Jarvis 66 (71), J.T. Miller 53 (68), Kreider 50 (75), Hintz 44 (53) | Solide ; les blessures (Draisaitl, Hintz) ont coûté environ 40 points |
| Paris recrues au banc | Misa 21 (45), Shabanov 18 (44) | Réservistes au départ, forcés dans l'alignement par les blessures de Draisaitl et Hintz ; rythme d'environ 35, et pas toujours dans l'alignement de leur équipe |
| Défense | Buium 26 (76), Edvinsson 25 (72), Klingberg 27 (56, pari vétéran au banc, n'est plus dans la LNH) | Environ 40 points de moins que deux défenseurs de ta liste (Byram, Luke Hughes à 45) |
| Gardiens et équipe | Dostal 65 pts pool, Greaves 68 ; Tampa 106 | Correct ; le duo valait plus avec des permutations suivies |

- **Le banc, c'est l'assurance blessures.** Sans ballottage, tes réservistes jouent chaque fois qu'un titulaire est blessé. L'an dernier, les absences de ton noyau (Draisaitl 17 matchs, Hintz 29, J.T. Miller 14, Carlsson 12, Jarvis 11, Kreider 7) totalisent environ 90 matchs, soit presque une saison complète d'une place active occupée par le banc.
- **Un pari recrue est une mauvaise assurance :** s'il est renvoyé dans les mineures ou laissé de côté, il ne rapporte rien quand tu en as besoin. Misa et Shabanov n'ont joué que 44-45 matchs.
- **Préfère des paris qui ont déjà un rôle** : Nemec (19:40, 26 points), Ufko (rythme de 50 en LNH), Cagnoni (AN1). Limite les recrues pures (Stenberg, Kantserov) à une par équipe.
- **Ne fais jamais d'un pari ton 2e défenseur actif** (Buium et Edvinsson à 25-26 points).
- **La défense tardive a été le trou.** Ça pèse en faveur de la règle des rondes 7-8 : un défenseur de ta liste s'il est là.
- **Permutations :** fixe une routine (vérification le dimanche soir pour les blessures, puis les matchs dos à dos des gardiens avant la réinitialisation de 3 h). Avec les choix définitifs, les blessés occupent le banc : c'est une raison de plus de ne pas gaspiller de place de banc sur des paris faibles.

## Points à vérifier avant le repêchage

- **Sabres :** vérifie l'état de Luukkonen et de Lyon (Ellis partant le 1er octobre ?) et la date à partir de laquelle les points comptent dans PoolExpert.
- **Régime des changements :** vérifie si PoolExpert permet encore les changements quotidiens (limite de 2 par semaine, avant la réinitialisation de 3 h) plutôt que le lundi seulement, comme le prévoit le point 2.3. Ça décide de la valeur d'un 2e gardien sur le banc.
- **Gustavsson : blessure confirmée** (opéré à la hanche, retour vers début novembre). Si le retour est devancé, Wallstedt perd un peu de valeur. S'il est retardé, Wallstedt tend vers le haut de la fourchette (78 pts pool).
- **Hellebuyck :** il est suspendu depuis le 16 septembre et aucun échange n'est imminent. La durée de sa grève décide de sa valeur et de celle de Skinner, qui a signé à Winnipeg le 1er juillet. Vérifie les nouvelles le jour même, car un échange avant le repêchage changerait tout. La Liste des listes Gardiens le place encore à Pittsburgh, ce qui est dépassé.
- **T.J. Hughes :** vérifie qu'il est sélectionnable dans PoolExpert, car il n'est pas dans le kit.
- **Victor Eklund et Ilya Protas :** le kit les ignore presque (1 et 33 matchs). Vérifie qu'ils sont sélectionnables dans PoolExpert.
- **Blessés selon NHL.com :** Jarvis (rang 59), Terry (85), Fiala (144), Tippett (159), et Faber en défense. Vérifie la durée des absences avant de les laisser passer ou de les prendre.
- **Stenberg :** le kit ne prévoit que 52 matchs. Vérifie s'il risque d'être renvoyé en Europe ou en junior.
- **Pittsburgh :** le kit fait de Murashov le partant ; ta liste mise sur Silovs.
- **Marqueur de blessure :** le kit met un « ° » après le nom de joueurs blessés ou incertains. On le retrouve chez Makar, Bedard, Jarvis, B. Tkachuk, Barzal, Terry, Demidov, Marchand (°°°), Fiala (°°), Duchene, McAvoy, Sanderson, Oettinger, Gustavsson et Hellebuyck. Demidov, McAvoy et Sanderson n'étaient pas dans ta liste de blessés.
- **Changements d'équipe :** le kit est plus récent que la Liste des listes 2026-27 : Quinn Hughes au MIN, Stankoven et Taylor Hall au CAR, Frost au CGY, Maccelli au NYI, Garland au CBJ.

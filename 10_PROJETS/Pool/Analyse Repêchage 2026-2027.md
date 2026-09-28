# Analyse Repêchage 2026-2027

Préparé à partir du kit PoolExpert (`data/draftkit-fr-*.xlsx`), des Listes des listes et des règlements. Les tableaux complets (tous les joueurs, toutes les colonnes) sont dans `scripts/sortie.md`, régénérable avec `node scripts/analyse.js`.

## En bref

- **Le « rang kit » sert d'ADP.** Le `#` du kit n'est pas un ADP : c'est le classement par points projetés. Comme tout le monde repêchera avec ce kit, c'est la meilleure approximation du prix du marché. Un joueur au rang kit 130 devrait partir vers le choix 130.
- **Le kit, c'est Fantrax.** Les projections du kit sont identiques à celles de Fantrax pour 169 joueurs sur 240, et à 1 point près pour 218. La valeur se trouve donc chez les joueurs que **HLM et ESPN** voient tous deux plus haut que Fantrax.
- **Défenseurs : le rang kit ne suffit pas.** Dans ton pool, le bonus de duo pousse les défenseurs à partir tôt. Une simulation du repêchage (section Objectif 4) donne deux résultats :
  - **En positions 6 à 21, deux défenseurs élites aux rondes 1 et 2 est la meilleure stratégie ou fait jeu égal**, et c'est particulièrement vrai à 19-21, où les deux choix sont dos à dos. Aux positions 1 à 3, c'est une erreur (environ 20 points de moins).
  - Avec cette surenchère, les défenseurs partent environ une ronde plus tôt que leur rang kit. Ta liste pour les rondes 7-8 (Byram, Harley, Luke Hughes, puis Clarke) correspond bien au marché réel.
- **Porter Martone n'est pas un diamant caché.** Le kit le projette à 72 points (rang 49, ronde 3), plus haut que ton plan (68).
- **Meilleure équipe sleeper : Ottawa.** Rang kit 28 sur 32 (85 pts), mais 10e dans ton plan (97,8 pts, 58 % de chances de séries) et 99 pts la saison dernière. Ullmark (rang G29 au kit, rang 9 dans la Liste des listes Gardiens) complète le duo.
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
  - **Marner** : 99 (kit 86, rang 19).
  - En défense : **Nemec** (46, contre 24 au kit, rang 384) et **Luke Hughes** (47, sur l'AN1 à la place de Hamilton).
  - **À éviter : Patrick Kane** (Dobber 53 en 65 matchs, contre 64 au kit).
- **Les meilleurs gardiens valent plus que prévu.** Avec 2 points par victoire, 1 par nulle et 3 par blanchissage, Vasilevskiy (96 pts pool) vaut un choix de ronde 2, et Oettinger ou Sorokin un choix de ronde 3. Ta liste de gardiens pour les rondes 7-11 se situe au niveau de remplacement (environ 59 pts) : attendre coûte peu, mais les écarts entre eux sont faibles.

## Règles qui touchent la stratégie

- **16 tours en serpent** (15 joueurs et 1 équipe) : ordre croissant aux tours impairs, décroissant aux tours pairs. Tirage de l'ordre demain à 15h00. Tu as 45 secondes par choix et un seul temps mort de 60 secondes : garde la feuille de référence ouverte.
- **Alignement actif :** au plus 8 attaquants, au moins 2 défenseurs, exactement 1 gardien et l'équipe. Les 4 autres joueurs sont au banc, et on peut faire 2 changements par semaine.
  - Un **3e défenseur** à 50 points ou plus joue à la place d'un attaquant, car l'attaquant de remplacement projette 42 points.
  - Un blessé de longue durée (Bedard, Terry, Fiala…) peut attendre au banc, puis entrer dans l'alignement à son retour.
- **Pointage :** patineurs et équipe comme dans la LNH. Gardiens : points + 2 par victoire + 1 par nulle + 3 par blanchissage.
- **Bonus par duo de défenseurs :** 25, 15 et 10 points pour les trois meilleurs duos de défenseurs de la ligue.
  - Selon la simulation, il faut un duo projeté autour de 150 points ou plus pour avoir de vraies chances de le gagner : deux défenseurs pris aux rondes 1 et 2.
  - Un duo pris aux rondes 7-8 (environ 85 points) n'a pratiquement aucune chance.
- **Niveau de remplacement :** c'est la production du dernier joueur actif requis dans une ligue de 21 équipes.
  - Attaquant n° 168 : 42 pts.
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
| Adam Fantilli | CBJ | C | 107 (R6) | 57 (81) | 79 (83) | +22 | 57/65/60 | 3,4 | **Priorité aux rondes 5 et 6** : HLM, ESPN et Dobber au-dessus |
| Simon Nemec | CGY | D | 384 (non repêché) | 24 (73) | 46 (78) | +22 | absent | 10,4 | **Défenseur sleeper** ; 26 points en 68 matchs, 19:40 de temps de glace |
| Matvei Michkov | PHI | RW | 146 (R7) | 51 (77) | 68 (83) | +17 | 51/60/55 | 4,2 | Diamant du plan confirmé : **prends-le en ronde 6** |
| Matt Coronato | CGY | LW | 186 (R9) | 43 (77) | 57 (82) | +14 | 43/50/48 | 3,9 | Confirmé : **ronde 8** |
| Mitch Marner | VGK | RW | 19 (R1) | 86 (82) | 99 (83) | +13 | 87/93/87 | 0,5 | En positions 19-21, rivalise avec un défenseur élite en ronde 1 |
| Logan Stankoven | CAR | C | 192 (R10) | 42 (77) | 54 (82) | +12 | 42/53/41 | 3,3 | HLM et Dobber : **ronde 9** |
| Gage Goncalves | TBL | C | 326 (R16) | 28 (67) | 39 (76) | +11 | absent | 5,3 | Pari de fin de repêchage (top 6 à Tampa) |
| JJ Peterka | BOS | RW | 137 (R7) | 53 (84) | 63 (82) | +10 | 53/58/54 | 2,8 | Valeur en ronde 7 |
| Mason McTavish | STL | C | 180 (R9) | 44 (75) | 53 (77) | +9 | 44/52/44 | 2,5 | HLM et Dobber : ronde 8 ou 9 |
| Luke Evangelista | NJD | RW | 134 (R7) | 53 (81) | 61 (81) | +8 | 53/62/51 | 2,4 | HLM et Dobber : ronde 7 |
| Noah Hanifin | VGK | D | 277 (R14) | 32 (75) | 40 (80) | +8 | absent | 3,4 | 3e défenseur tardif ; va avec Vegas |
| Quinn Hughes | MIN | D | 31 (R2) | 80 (76) | 87 (77) | +7 | 80/88/81 | 0,6 | Rythme de 93 : cible n° 1 du duo élite |
| Luke Hughes | NJD | D | 209 (R10) | 40 (72) | 47 (76) | +7 | 40/51/38 | 2,2 | **AN1 à la place de Hamilton** : monte en ronde 7 |
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
| Konsta Helenius | BUF | 376 (non repêché) | 24 | 49 | absent | — | recrue | 10,8 / — | Pari, dernier choix |
| Dalibor Dvorsky | STL | 409 (non repêché) | 22 | 42 | absent | — | 21 (24) | 10,4 / — | Pari, dernier choix |

À retenir :

- **Diamants confirmés par au moins une autre source et au rythme 2025-26 :** Will Smith et Demidov (ronde 5), Rossi et Michkov (ronde 7), Coronato et Benson (rondes 9-10), Graf (ronde 11), Bourque, Gridin et Savoie (rondes 13-14). Pour ceux-là, ton plan tient.
- **Dobber confirme aussi Stenberg (65), Kantserov (55), Michkov (68) et Coronato (57).** Avance Michkov en ronde 6 et Coronato en ronde 8 : les lecteurs de Dobber vont les voir.
- **Tes projections du plan (NHL.com) sont en moyenne bien au-dessus de toutes les autres sources.** Pour Frondell, Chinakhov, Mikheyev et Gritsyuk, aucune source ne va plus haut que 45 à 50 points. Ce sont des paris, pas des diamants : ne les prends pas avant leur rang kit.
  - Frondell et Chinakhov : pas avant les rondes 9-10.
  - Helenius et Dvorsky : ils ne seront probablement pas repêchés, donc garde-les pour tes 2-3 derniers choix.
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
| Zayne Parekh | CGY | 405 (non repêché) | 22 (61) | 40 (Oui) | absent | — | 9 en 37 PJ (20) | 17:06 | Pari |
| Ryan Ufko | NSH | 585 (non repêché) | 11 (34) | 50 (PP2) | absent | — | 11 en 18 PJ (50) | 13:46 | Pari : le kit ne le voit pas dans l'alignement |
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

- Newhook (rang 332, 27/52/—), Landeskog, Perreault, Cowan, Doan, Theodore, Eklund, Pinto. McKenna est sorti de cette liste depuis que Dobber le projette à 70.
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

| Équipe | Rang kit | Pts kit | Rang plan | Pts plan | Séries plan | Pts 2025-26 | Duo de gardiens (V kit / V LdL) |
|---|---|---|---|---|---|---|---|
| **Sénateurs** | 28 | 85 | 10 | 97,8 | 58 % | 99 | Ullmark 21 / **29** ; Ersson 13 |
| **Blues** | 24 | 89 | 13 | 94,9 | 56 % | 86 | Hofer 23 / 24 ; Binnington 16 |
| **Golden Knights** | 13 | 98 | 4 | 101,1 | 79 % | 95 | Hart 25 / 27 ; Hill 17 / 19 |
| **Canadiens** | 16 | 94 | 8 | 99,3 | 63 % | 106 | Dobes 26 / 27 ; Fowler 10 / 15 |
| Oilers | 14 | 92 | 9 | 96,7 | 67 % | 93 | Andersen 17 ; Jarry 13 / 19 (duo faible) |
| Kings | 26 | 89 | 21 | 90,6 | 47 % | 90 | Kuemper 22 ; Forsberg 16 / 17 |
| Blue Jackets | 20 | 91 | 16 | 93,8 | 46 % | 92 | Greaves 23 / 24 ; Talbot 8 |

Recommandations :

1. **Ottawa est le meilleur sleeper.** Le kit les place 28e sur 32, alors qu'ils ont fait 99 pts la saison dernière et que ton plan les met 10e. Tu devrais pouvoir les prendre à l'un de tes 3 derniers tours. **Ullmark** suit la même logique : rang G29 au kit, mais 9e selon la Liste des listes Gardiens (28/30/29 victoires). Avec 29 victoires, il vaudrait environ 75 pts pool, soit le niveau d'un gardien top 7, au prix d'un substitut.
2. **Vegas et Montréal** sont des choix de milieu de repêchage à bon prix.
   - Vegas : rang kit 13, 4e dans ton plan. Duo Hart-Hill ; Hart projette 71 pts pool (8 nulles, 4 blanchissages au kit).
   - Montréal : rang kit 16, 106 pts la saison dernière. Duo Dobes-Fowler ; Dobes est 13e selon la Liste des listes Gardiens.
3. **St. Louis** comme plan de repli tardif, avec Hofer, qui est déjà dans ta liste de gardiens.
4. **Edmonton :** l'équipe est sous-estimée, mais le duo Andersen-Jarry est faible. Prends l'équipe, pas le gardien.
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
| Connor Hellebuyck (bl.) | WPG | G9 | 27 | 25 | 21 | 76 | Grève et blessure : risque élevé |
| Stuart Skinner | WPG (signé le 1er juillet) | G49 | 13 (25 PJ) | 25 (projeté comme partant à PIT) | 22 | 34 (réserviste) ; environ 60 comme partant | **Sleeper :** partant à Winnipeg pendant la grève de Hellebuyck |
| Sergei Murashov | PIT | G17 | 25 | absent | — | 64 | Le kit en fait le partant à Pittsburgh, devant Silovs |
| Arturs Silovs | PIT | G40 | 16 | 19 | 35 | 46 | **Retirer de ta liste** : réserviste selon le kit |
| Jake Allen | NJD | G18 | 25 | 23 | 27 | 61 ; **environ 66 à 68** sans Rittich | Rittich rétrogradé le 28 septembre : environ 53 matchs et 27-28 victoires. Ton plan (28) devient réaliste |
| Nico Daws | NJD | G75 | 4 (16 PJ) | absent | — | 12 ; environ 20 à 25 comme réserviste | Réserviste d'Allen : utile seulement si Allen se blesse |
| Yaroslav Askarov | SJS | G22 | 24 | 22 | 29 | 53 | Ton plan (25) est optimiste ; ESPN à 17 |

**Skinner, le vrai sleeper des gardiens :** il a signé à Winnipeg le 1er juillet. Le kit le traite en réserviste (25 matchs, 13 victoires), alors qu'il sera le partant tant que Hellebuyck est en grève.
- En 2025-26, il a obtenu 23 victoires, 9 nulles et 2 blanchissages en 50 matchs, soit 62 pts pool. C'est le niveau de Vladar ou d'Allen, pour un gardien classé 49e au kit.
- Comme personne ne le prendra avant la fin, choisis-le comme **gardien substitut entre les rondes 12 et 14**. Il peut même servir de gardien partant si la grève se prolonge.
- **Évite Hellebuyck** à son prix (9e gardien au kit).
- **Évite aussi l'équipe des Jets** : le kit compte 27 victoires de Hellebuyck dans leur projection.

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
- **Verdict :** à prendre en toute dernière ronde seulement, et seulement si une équipe a une place de banc libre. Si Luukkonen, qui a déjà beaucoup de blessures à son dossier, est absent longtemps, Ellis devient ton gardien de rechange au ballottage. Vérifie aussi à partir de quelle date les points comptent : l'an dernier, l'alignement devait être déposé le 8 octobre. Si c'est encore le cas, la courte fenêtre d'Ellis pourrait être passée avant que ton alignement compte.

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
- **Murashov :** le kit en fait le partant à Pittsburgh, mais il est absent de la Liste des listes Gardiens, qui place Silovs à Pittsburgh. Vérifie qui sera partant avant de le prendre. Allen est plus sûr.
- **Deux positions dans l'ordre du repêchage :**
  - En serpentin, l'équipe qui choisit tôt dans une ronde choisit tard dans la suivante.
  - Aux rondes où tes deux choix sont rapprochés, prends les deux cibles d'un même type l'une après l'autre (deux gardiens, deux sleepers).
  - Aux rondes où ils sont éloignés, fais prendre la cible la plus rare à l'équipe qui choisit en premier.
- **Les autres sleepers se partagent aussi :**
  - **Équipes :** Ottawa pour l'une, Vegas, Montréal ou St. Louis pour l'autre.
  - **Défenseurs de la ronde 7 :** Byram pour l'une, Cole Hutson pour l'autre.
  - **Défenseurs tardifs :** Cagnoni pour l'une, Nemec pour l'autre.
  - **Attaquants tardifs :** Stenberg et Kantserov, un de chaque côté.
  - Chaque équipe peut viser son propre boni de duo de défenseurs, mais il n'y a pas assez de défenseurs élites en rondes 1 et 2 pour les deux si vos positions sont proches.
- **Allen gagne de la valeur** avec la rétrogradation de Rittich : Daws (3 matchs dans la LNH l'an dernier) est un réserviste plus faible, donc Allen devrait jouer environ 53 matchs. À 27-28 victoires, il vaut environ 66 à 68 pts pool, au niveau d'un gardien classé 12e ou 13e.

Ta liste de gardiens pour les rondes 7-11 : Saros (70 pts pool) est le seul nettement au-dessus du niveau de remplacement (59). Vladar, Allen, Hofer, Blackwood et Luukkonen tournent autour de 58 à 61 pts. Ajoute Ullmark, Shesterkin et Hart, qui valent autant ou mieux, souvent moins cher. Retire Silovs. Kuemper (G26, 63 pts pool, absent de la Liste des listes) est un bon substitut tardif.

## Objectif 4 : défenseurs (bonus de duo, surenchère et rondes 6 à 8)

Plages de choix : ronde 6 = choix 106 à 126, ronde 7 = 127 à 147, ronde 8 = 148 à 168.

### Le bonus de duo et le dos à dos : ce que dit la simulation

Pour vérifier ta stratégie du dos à dos, j'ai simulé le repêchage complet des patineurs sur 14 tours, pour chaque position et chaque stratégie. Chaque repêchage est ensuite joué sur 4 000 saisons simulées (script `scripts/duo.js`).

**Comment les autres poolers repêchent.** Ils suivent le kit, mais surpaient les défenseurs. Deux intensités sont testées :

- **Modéré :** environ 8 points de surenchère, soit 32 défenseurs partis à la fin de la ronde 8.
- **Fort :** environ 14 points de surenchère, soit 43 défenseurs partis à la fin de la ronde 8 (2 par pooler).

**Ce qu'on mesure pour toi.** Tu prends tes deux défenseurs aux rondes indiquées et le meilleur attaquant disponible partout ailleurs. On calcule deux choses :

- les points projetés de ton alignement actif (10 patineurs) ;
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
| 3 | Rondes 2-3 (Hutson + Raddysh) | Bouchard + Hutson (162) | 51 % | -20 / -15 | -6 / -4 |
| 6 | Rondes 1-2 | Bouchard + Hutson (162) | 50 % | 0 / -0,5 | -12 / -4 |
| 11 | Rondes 1-2 | Makar + Hutson (154) | 34 % | 0 / 0 | -8 / -4 |
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
| 3 | Brock Faber | MIN | 24 | 158 | 49 | 49/58/48 | 50 | 51 en 80 PJ (52) | Parti en ronde 6 selon le scénario modéré |
| 4 | Noah Dobson | MTL | 26 | 157 | 49 | 49/51/53 | 50 | 47 en 80 PJ (48) | Sources unanimes, faible risque |
| À éviter | Victor Hedman | TBL | 35 | 141 | 52 | 52/**39**/51 | 50 | 17 en 33 PJ (42) | Âge et saison blessée ; HLM le voit à 39 |

### Ronde 7 : ta liste, au prix du marché

| Rang | Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | Proj. retenue | 2025-26 (rythme 82) | Plan (AN) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | Bowen Byram | CHI | 25 | 204 | 41 | 41/55/51 | 45 | 42 (42) | 50 (Oui) | **Priorité** : seul défenseur de ta liste confirmé par HLM et ESPN. Part au choix 127 selon le scénario fort |
| 2 | **Cole Hutson** | WSH | 20 | 206 (D32) | 40 **en 63 PJ** | 40/50/— | 45 | 10 en 14 PJ (59) | — | **Plancher d'environ 52 sur 82 matchs** (0,63 pt par match au kit). Carlson est parti à Tampa, ce qui libère l'AN1 avec Chychrun. Plafond de 60 et plus : le plus haut de la ronde 7 |
| 3 | **Luke Hughes** | NJD | 23 | 209 | 40 | 40/51/38 ; Dobber 47 | 45 | 35 en 68 PJ (42) | 45 (Oui) | AN1 à la place de Hamilton, confirmé par HLM (51) et Dobber (47) |
| 4 | Rasmus Andersson | VGK | 29 | 171 | 46 | 46/49/45 | 46 | 47 en 81 PJ (48) | 48 (Non) | Plancher le plus sûr ; bon avec l'équipe Vegas |
| 5 | Shea Theodore | VGK | 31 | 174 | 45 | 45/61/45 | 48 | 39 en 70 PJ (46) | — | Plafond venant de HLM seulement |
| 6 | Thomas Harley | DAL | 25 | 197 | 41 | 41/48/42 | 42 | 36 en 70 PJ (42) | 49 (PP2) | Plafond crédible |
| — | Filip Hronek | VAN | 28 | 161 | 48 | 48/44/50 | 48 | 49 en 82 PJ (49) | — | S'il reste : plancher stable, équipe faible |

### Ronde 8 : deuxième défenseur ou 3e défenseur

| Rang | Joueur | Éq. | Âge | Rang kit | Kit | LdL F/HLM/ESPN | 2025-26 (rythme 82) | Plan (AN) | Commentaire |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Le reste de la liste de la ronde 7 | | | | | | | | Harley et Luke Hughes partent vers les choix 163-169 selon le scénario modéré |
| 2 | Thomas Chabot | OTT | 29 | 235 | 36 | 36/42/45 | 31 en 57 PJ (45) | — | ESPN à 45 ; va avec l'équipe Ottawa |
| 3 | Brandt Clarke | LAK | 23 | 243 | 36 | absent | 40 (40) | 55 (Oui) | AN1 ; ton plan est seul à 55. Part au choix 167 selon le scénario fort |
| 4 | Seth Jones | FLA | 31 | 264 | 33 | 33/47/37 | 32 en 52 PJ (50) | 52 (Oui) | Rythme de 50 la saison dernière |
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
- **Drysdale** (D 67, vers la ronde 13) : Dobber l'estime à 36 points et voit une percée possible après 180 minutes d'AN l'an dernier. Il remplace Broberg comme pari de la ronde 13.
- **Noah Hanifin (VGK)** : Dobber l'estime à 40 points (kit 32, rang 277). C'est un 3e défenseur tardif qui va bien avec l'équipe Vegas.
- **Broberg : rétrogradé.** Dobber l'estime à 31, exactement comme le kit, donc aucun avantage. Dobber suggère plutôt **Logan Mailloux** (STL, rang 533, 15 points au kit), à prendre en dernière ronde.
- **Buium** (plancher de 32 selon Dobber, plus s'il obtient l'AN1), **Parekh et Ufko :** derniers choix seulement. Ufko n'a qu'un rôle de réserviste au kit (34 matchs).
- **T.J. Hughes (COL, AN1)** : absent du kit, donc dernière ronde. Vérifie d'abord qu'il est sélectionnable dans PoolExpert.

### Ordre suggéré selon ta position

1. **Positions 19-21 (dos à dos) :** deux défenseurs élites aux rondes 1 et 2, parmi Werenski, Q. Hughes (Dobber 87), Fox et Makar. Seule alternative crédible en ronde 1 : Marner (Dobber 99). Ensuite, pas besoin de défenseur aux rondes 6 à 8 : ton 3e défenseur peut attendre Byram ou Luke Hughes en ronde 7 s'ils sont encore là, sinon Cagnoni ou Nemec aux rondes 10 à 13. Le 3e défenseur ne joue que s'il bat un attaquant à 42 points. Utilise tes rondes 5 à 8 pour les attaquants appuyés par Dobber : Fantilli, Michkov, Peterka ou Evangelista, McKenna, puis Coronato.
2. **Positions 6-18 :** même logique si deux défenseurs élites tombent à tes choix des rondes 1 et 2. Sinon, un défenseur élite en ronde 1, puis Byram, Andersson ou Harley en ronde 7.
3. **Positions 1-5 :** attaquant élite en ronde 1. Défenseur 1 en ronde 3 ou 4 (Dahlin, Raddysh, Carlson, Josi, Heiskanen), défenseur 2 en ronde 6 ou 7 (LaCombe, Gostisbehere, Faber, Byram), défenseur 3 aux rondes 10 à 13 (Cagnoni, Nemec, Chabot, Clarke).

## Points à vérifier avant le repêchage

- **Sabres :** vérifie l'état de Luukkonen et de Lyon (Ellis partant le 1er octobre ?) et la date à partir de laquelle les points comptent dans PoolExpert.
- **Régime des changements :** vérifie si PoolExpert permet encore les changements quotidiens (limite de 2 par semaine, avant la réinitialisation de 3 h) plutôt que le lundi seulement, comme le prévoit le point 2.3. Ça décide de la valeur d'un 2e gardien sur le banc.
- **Gustavsson : blessure confirmée** (opéré à la hanche, retour vers début novembre). Si le retour est devancé, Wallstedt perd un peu de valeur. S'il est retardé, Wallstedt tend vers le haut de la fourchette (78 pts pool).
- **Hellebuyck :** la durée de sa grève décide de la valeur de Skinner, qui a signé à Winnipeg le 1er juillet. La Liste des listes Gardiens le place encore à Pittsburgh, ce qui est dépassé.
- **T.J. Hughes :** vérifie qu'il est sélectionnable dans PoolExpert, car il n'est pas dans le kit.
- **Stenberg :** le kit ne prévoit que 52 matchs. Vérifie s'il risque d'être renvoyé en Europe ou en junior.
- **Pittsburgh :** le kit fait de Murashov le partant ; ta liste mise sur Silovs.
- **Marqueur de blessure :** le kit met un « ° » après le nom de joueurs blessés ou incertains. On le retrouve chez Makar, Bedard, Jarvis, B. Tkachuk, Barzal, Terry, Demidov, Marchand (°°°), Fiala (°°), Duchene, McAvoy, Sanderson, Oettinger, Gustavsson et Hellebuyck. Demidov, McAvoy et Sanderson n'étaient pas dans ta liste de blessés.
- **Changements d'équipe :** le kit est plus récent que la Liste des listes 2026-27 : Quinn Hughes au MIN, Stankoven et Taylor Hall au CAR, Frost au CGY, Maccelli au NYI, Garland au CBJ.

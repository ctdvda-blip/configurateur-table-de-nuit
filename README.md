# Configurateur — Table de nuit

Configurateur 3D temps réel d'une table de nuit : 4 pieds, 1 à 3 tiroirs,
essences et finitions au choix. Une seule page HTML, sans build ni dépendance
à installer (Three.js est chargé depuis un CDN).

## Utilisation

Ouvrir la page en ligne, ou `table-de-nuit.html` directement dans un navigateur.

- **Orbite** clic gauche · **zoom** molette · **déplacement** clic droit
- 4 vues prédéfinies : 3/4, face, côté, dessus

## Ce qui est paramétrable

| | |
|---|---|
| Dimensions | largeur 32–70 cm, profondeur 28–52 cm, hauteur 40–75 cm, hauteur des pieds |
| Tiroirs | 1, 2 ou 3, avec jeu de 3 mm entre façades |
| Pieds | droit carré, fuselé, compas, épingle métal |
| Matériaux | 6 bois à veinage procédural + 4 laques, séparément pour le caisson et les façades |
| Poignées | gorge usinée, bouton, barre, lanière cuir — laiton / noir mat / chrome |
| Options | plateau débordant, tiroirs ouverts, rotation automatique, décor et ombre portée |

Le prix indicatif est recalculé en continu à partir des surfaces de panneaux,
du nombre de tiroirs et de la quincaillerie.

## Exports

| Format | Détail |
|---|---|
| **OBJ + MTL** | millimètres, matériaux nommés — deux téléchargements successifs |
| **STL** | binaire, millimètres |
| **GLB** | avec textures |
| **PNG** | capture de la vue courante |
| **TXT** | fiche technique : quantitatif panneaux et chiffrage |

> **STEP** : impossible depuis un navigateur, c'est un format solide B-Rep qui
> exige un noyau CAO. Importer l'OBJ ou le STL dans Rhino / FreeCAD / Fusion,
> puis ré-exporter en `.step`. Les exports étant déjà en millimètres, aucune
> mise à l'échelle n'est nécessaire.

## Technique

Three.js r160 (module ES via importmap), `OrbitControls`, éclairage studio
`RoomEnvironment` + PMREM, ombres PCF douces, tone mapping ACES.
Les veinages de bois sont générés par canvas à la volée : aucune texture externe.

La géométrie est entièrement reconstruite à chaque changement de paramètre
depuis les cotes de fabrication réelles (panneaux 18 mm, plateau 20 mm,
fond 10 mm, caisses de tiroir en contreplaqué 12 mm).

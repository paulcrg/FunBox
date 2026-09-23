# FunBox

> Une boîte à mini-jeux électronique pilotée par Arduino, un peu comme une borne d'arcade miniature.

Projet réalisé dans le cadre du cursus Informatique & Électronique de l'ESEO Dijon (2ᵉ année, E2), par **Paul Crémoux Guiblain** et **Philippe Lecoq**.

![Statut](https://img.shields.io/badge/statut-en%20cours-yellow)
![Plateforme](https://img.shields.io/badge/plateforme-Arduino-00979D)
![Licence](https://img.shields.io/badge/licence-MIT-blue)

<!-- Logo du projet -->
<!-- ![Logo FunBox](docs/logo.png) -->

---

## Sommaire

- [Présentation](#présentation)
- [Les 4 jeux](#les-4-jeux)
- [Matériel utilisé](#matériel-utilisé)
- [Architecture logicielle](#architecture-logicielle)
- [Installation](#installation)
- [Structure du dépôt](#structure-du-dépôt)
- [Feuille de route](#feuille-de-route)
- [Équipe](#équipe)
- [Licence](#licence)

---

## Présentation

FunBox est une boîte de jeux électronique regroupant quatre mini-jeux distincts, accessibles depuis un menu principal. Chaque jeu sollicite une compétence différente du joueur (réflexes, mémoire, précision, timing), avec un affichage des scores sur un écran OLED et un retour sonore via un buzzer.

Le projet met en pratique des compétences en programmation embarquée (C++/Arduino), en électronique (câblage, gestion d'entrées/sorties) et en conception mécanique (boîtier découpé/gravé au laser).

## Les 4 jeux

| # | Jeu | Principe |
|---|-----|----------|
| 1 | **Réaction F1** | Trois LED s'allument façon grille de départ de F1, puis s'éteignent après un délai aléatoire. Le joueur doit appuyer le plus vite possible. Un appui prématuré est pénalisé. |
| 2 | **Mémoire (Simon)** | La boîte allume une séquence de LED que le joueur doit reproduire dans l'ordre. La séquence s'allonge à chaque réussite. |
| 3 | **Angle** | Une jauge est affichée à un angle donné pendant un temps limité. Le joueur doit reproduire cet angle à l'aide d'un potentiomètre. |
| 4 | **Timing** | Une jauge progresse en continu. Le joueur doit appuyer lorsqu'elle se trouve dans une zone cible, sur le principe d'un jeu de rythme. |

## Matériel utilisé

- Carte **Arduino Uno**
- Écran **OLED I2C 0,96" 128x64** (SSD1306)
- Potentiomètre **10 kΩ**
- 6 grosses **LED** type F1
- 9 **boutons-poussoirs dôme lumineux** type arcade (LED intégrée)
- **Buzzer actif** (retour sonore)
- **Boîtier pile 9V** avec interrupteur intégré
- Résistances, câbles de connexion, breadboard/perfboard
- Boîtier découpé et gravé au laser

## Architecture logicielle

Le programme repose sur une machine à états non bloquante (utilisation de `millis()` plutôt que `delay()`), organisée autour d'un menu principal permettant de naviguer entre les quatre jeux et de lancer celui sélectionné.

L'algorigramme détaillé du fonctionnement (vue générale + un algorigramme par jeu) est disponible dans le dossier [`docs/`](docs/).

## Installation

1. Cloner le dépôt :
   ```bash
   git clone https://github.com/paulcrg/FunBox.git
   ```
2. Ouvrir le projet dans l'[IDE Arduino](https://www.arduino.cc/en/software).
3. Installer les bibliothèques nécessaires via le gestionnaire de bibliothèques :
   - `Adafruit_SSD1306`
   - `Adafruit_GFX`
4. Sélectionner la carte **Arduino Uno** et le port série correspondant.
5. Téléverser le sketch principal situé dans `code/FunBox/FunBox.ino`.

## Structure du dépôt

```
FunBox/
├── code/               # Code source Arduino (C++)
│   └── FunBox/
│       └── FunBox.ino
├── docs/               # Documentation, algorigrammes, comptes-rendus
├── hardware/           # Schémas de câblage, modèles de découpe laser
├── README.md
└── LICENSE
```

## Feuille de route

- [x] Définition du concept et des 4 jeux
- [x] Choix du matériel et commande des composants
- [x] Réalisation des algorigrammes détaillés
- [x] Choix de la carte (Arduino)
- [ ] Design final du logo
- [ ] Modèle de découpe/gravure laser du boîtier
- [ ] Prototypage logiciel en ligne (Wokwi)
- [ ] Câblage physique et tests unitaires
- [ ] Intégration complète et assemblage du boîtier
- [ ] Soutenance finale

## Équipe

| Nom | Rôle |
|-----|------|
| **Paul Crémoux Guiblain** | Électronique, logique logicielle, algorigrammes |
| **Philippe Lecoq** | Conception mécanique, identité visuelle (logo, croquis) |

## Licence

Ce projet est distribué sous licence MIT. Voir le fichier [`LICENSE`](LICENSE) pour plus de détails.

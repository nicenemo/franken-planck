## Layouts

Ce dépôt contient des configurations de touches (layouts) personnalisées pour un clavier ortholinéaire Planck.

Tous les répertoires listés ci-dessous s'appuient sur la même base matérielle (Planck v6, disposition 48 touches) :

* **Franken-Planck:** Une configuration à 9 couches (layers) intégrant les fonctionnalités suivantes :
  * Touches de déplacement `hjkl` (style Vim) accessibles sous la couche Lower (maintenir les touches enfoncées déclenche la répétition des flèches).
  * Modificateurs sur la rangée d'accueil (Home-row modifiers).
  * Pavé numérique à gauche et pavé de navigation souris à droite.
  * Une couche dédiée contenant l'intégralité des 24 touches de fonction (F1-F24).
  * Touches multimédias et lanceurs d'applications (optimisés pour une intégration AutoHotkey via des touches de langue asiatique mappées sur la couche souris).
  * Accès direct aux caractères tilde, backtick et guillemets sur la couche 0 (permettant de contourner les restrictions liées aux layer-taps).
  * Contrôle ergonomique via les pouces : une impulsion sur Raise exécute un Backspace, une impulsion sur Lower exécute un Delete.
  * Intégration de la disposition ergonomique NEO2 (optimisée pour la programmation et la syntaxe mathématique), où les umlauts ont été reprogrammés pour produire des guillemets doubles ainsi qu'un deux-points/point-virgule.
* **Angelas Franken-Planck:** Une variante de la Franken-Planck, adaptée spécifiquement pour Angela.
* **Macropad Angela:** Une configuration de type macro-pad qui fonctionne logiquement comme un clavier Planck.

---

## Structure des Répertoires

L'arborescence est structurée de manière à ce que le compilateur QMK puisse mapper directement les fichiers sur le dépôt principal. Les fichiers PDF contenant les aperçus graphiques des layouts se trouvent à la racine du projet :

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Aperçu du layout d'Angela
├── franken-planck.pdf                # Aperçu du layout Franken-Planck
├── macropad-angela.pdf               # Aperçu du layout du Macropad
└── keyboards/
    └── planck/
        └── rev6/
            └── keymaps/
                ├── angelas-franken-planck/
                │   ├── angelas-franken-planck.json
                │   ├── config.h
                │   └── rules.mk
                ├── franken-planck/
                │   ├── franken-planck.json
                │   ├── config.h
                │   └── rules.mk
                └── macropad-angela/
                    ├── keymap.json
                    ├── config.h
                    └── rules.mk


## Compilation

Ce dépôt résidant en dehors de la structure de répertoires standard de QMK, vous devez explicitement indiquer au CLI où localiser ce dossier avant de lancer une compilation.

### 1. Liaison de l'Overlay

Exécutez la commande suivante à la racine de ce projet :



### 2. Build du Firmware

Utilisez les commandes de compilation standards. QMK détectera et analysera automatiquement les fichiers .json pour générer les binaires :

# Compiler le layout Franken-Planck
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Compiler le layout d'Angela (Planck)
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Compiler le layout du Macropad
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## Sources & Références

* Architecture de la couche Vim basée sur [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Configuration des touches fléchées sous Lower basée sur le [Planck de Noah Frederick](https://noahfrederick.com/log/the-planck-keyboard).
* Configuration NEO2 convertie directement depuis le code source C du [Jan Lunge's Planck Layout](https://blog

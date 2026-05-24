## Layouts

Disse repository bevat eigen keyboard layouts veur een Planck ortholinear keyboard.

Alle mappen hierunder maakt gebruuk van krek dezelfde hardwarebasis (Planck v6, 48-key layout):

* **Franken-Planck:** Een 9-laags indeling met de volgende functionaliteiten:
  * `hjkl` cursor-toetsen (Vim-stiel) under de Lower-laag (ingedrukt holden gef herhalende pieltjes).
  * Home-row modifiers.
  * Links-handig num-pad en rechts-handig mouse-pad.
  * Een amparte laag met alle 24 functie-toetsen.
  * Media-keys en applicatie-launchers (ericht op AutoHotkey-integratie via Aziatische taaltoetsen op de muislaag).
  * Directe toegang tot tilde, backtick en quotes op laag 0 (dormee gao'j langs de layer-tap restricties).
  * Ergonomische doembediening: Tikken op Raise gef Backspace, tikken op Lower gef Delete.
  * Integratie van de ergonomische NEO2-indeling (geoptimaliseerd veur programmeren en wiskundige syntax), waorbi'j de umlauts bint hergeprogrammeerd nao dubbele quotes en een dubbele punt/puntkomma.
* **Angelas Franken-Planck:** Een variant op de Franken-Planck, anpassen veur Angela.
* **Macropad Angela:** Een macro-pad configuratie dee logisch functioneert as een Planck-toetsenbord.

---

## Mappenstructuur

De mappen bint zo ingericht dat de QMK-compiler de bestanden direct kan mappen op de hoofd-repository. De PDF-bestanden met grafische lay-outs stoat in de hoofdmap:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layoutoverzicht Angela
├── franken-planck.pdf                # Layoutoverzicht Franken-Planck
├── macropad-angela.pdf               # Layoutoverzicht Macropad
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


## Compileren

Umdat disse repository buten de standaard QMK-mappenstructuur steyt, mu'j de CLI eerst vertellen waor disse map te vinden is veurda'j gaot compileren.

### 1. Overlay koppelen

Voer dit commando ut in de hoofdmap van dit project:



### 2. Firmware bouwen

Gebruuk de standaard compileer-opdrachten. QMK pakt automatisch de .json-bestanden op om de firmware te genereren:

# Bouw Franken-Planck
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Bouw Angela's Planck
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Bouw Macropad
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## Bronnen & Referenties

* Vim-layer ebaseerd op [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Pijltoetsen under Lower ebaseerd op [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2-configuratie geconverteerd vanut de C-code van [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

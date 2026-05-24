## Layouts

Dees repository bevat eige keyboard layouts veur 'n Planck ortholinear keyboard.

Alle mappen hiejónger make gebroek van krek dezelfde hardwarebasis (Planck v6, 48-key layout):

* **Franken-Planck:** 'N 9-laogs indeiling mèt de volgende functionaliteiten:
  * `hjkl` cursor-toetse (Vim-stiel) ónder de Lower-laog (ingedrök hauwte gief herhaolende pielkes).
  * Home-row modifiers.
  * Links-handig num-pad en rechs-handig mouse-pad.
  * 'N apaarte laog mèt alle 24 functie-toetse.
  * Media-keys en applicatie-launchers (gerich op AutoHotkey-integratie via Aziatische taaltoetse op de moeslaog).
  * Directe toegank tot tilde, backtick en quotes op laog 0 (daomit gank geir veurbiej de layer-tap restricties).
  * Ergonomische doembeejiening: Tikke op Raise gief Backspace, tikke op Lower gief Delete.
  * Integratie van de ergonomische NEO2-indeiling (geoptimaliseerd veur programmeren en wiskundige syntax), waorbie de umlauts zeen hergeprogrammeerd nao dubbele quotes en 'ne dubbele punt/puntkomma.
* **Angelas Franken-Planck:** 'N variant op de Franken-Planck, aangepas veur Angela.
* **Macropad Angela:** 'N macro-pad configuratie deeg logisch functioneert es 'n Planck-toetseboerd.

---

## Mappenstructuur

De mappen zeen zó ingerich dat de QMK-compiler de bestande direct kan mappen op de hoofd-repository. De PDF-bestande mèt grafische lay-outs staon in de hoofdmap:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layoutoverzich Angela
├── franken-planck.pdf                # Layoutoverzich Franken-Planck
├── macropad-angela.pdf               # Layoutoverzich Macropad
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

Omdat dees repository boete de standaard QMK-mappenstructuur sjteit, mót geir de CLI iers vertelle woe dees map te vinde is veurdat geir geit compileren.

### 1. Overlay koppelen

Veurt dit commando oet in de hoofdmap van dit project:

qmk config user.overlay_dir="$(realpath .)"


### 2. Firmware bouwen

Gebroek de standaard compileer-opdrachte. QMK pak automatisch de .json-bestande op óm de firmware te genereren:

# Bouw Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Bouw Angela's Planck
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Bouw Macropad
qmk compile -kb planck/rev6 -km macropad-angela


---

## Bronne & Referenties

* Vim-layer gebaseerd op [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Pieltoetse ónder Lower gebaseerd op [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2-configuratie geconverteerd oet de C-code van [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

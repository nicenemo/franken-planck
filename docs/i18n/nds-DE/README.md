## Layouts

Disse Repository verwohrt egen Keyboard-Layouts för een Planck ortholinear Keyboard.

Alle Ordners hierünner bruukt de nipp un glaake Hardware-Basis (Planck v6, 48-Key-Layout):

* **Franken-Planck:** Een Layout mit 9 Lagen (Layer) un disse Funkshonen:
  * `hjkl` Cursor-Tasten (Vim-Stil) ünner de Lower-Laag (wenn du de Tasten fasthöllst, warrt de Piele herhaalt).
  * Home-Row Modifier.
  * Links-bannig Num-Pad un rechts-bannig Mouse-Pad.
  * Een amparte Laag mit alle 24 Funkshons-Tasten.
  * Media-Keys un Applikashons-Starter (utricht op AutoHotkey-Integrashon över asiaatsche Spraaktasten op de Muus-Laag).
  * Direkten Togang to Tilde, Backtick un Quotes op Laag 0 (dormit geihst du bi de Layer-Tap Restrikshonen bi langs).
  * Ergonoomsche Dumen-Bedienung: Tippen op Raise gifft Backspace, tippen op Lower gifft Delete.
  * Integrashon van dat ergonoomsche NEO2-Layout (optimert för dat Programmeren un wiskundige Syntax), woorbi de Umlauten to dubbelte Anföhrungsteken un een Dubbelpunkt/Semikolon ümprogrammeert sünd.
* **Angelas Franken-Planck:** Een Variant van dat Franken-Planck-Layout, klookmaakt för Angela.
* **Macropad Angela:** Een Macro-Pad-Konfigurashon, de logisch as een Planck-Tastatur arbeidt.

---

## Ordnerstruktuur

De Ordners sünd so opboot, dat de QMK-Compiler de Dateinen direktemang op dat Haupt-Repository afbellen kann. De PDF-Dateinen mit de graafschen Layout-Översichten liggt in den Root-Ordner:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layout-Översicht Angela
├── franken-planck.pdf                # Layout-Översicht Franken-Planck
├── macropad-angela.pdf               # Layout-Översicht Macro-Pad
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


## Kompileren

Wieldat disse Repository buten de normole QMK-Ordnerstruktuur liggt, musst du de CLI eerst vertellen, woor disse Ordner to finnen is, ehr du dat Kompileren startst.

### 1. Overlay verknüppen

Fehr dissen Befehl in den Root-Ordner van düt Projekt ut:



### 2. Firmware buen

Bruuk de Standard-Kompileerbefehlen. QMK finnt un parst de .json-Dateinen automaatsch, üm de Binärdateinen to maken:

# Franken-Planck buen
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Angela ehr Planck buen
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Macro-Pad buen
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## Quellen & Referenzen

* Vim-Laag baseert op [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Pieltasten ünner Lower baseert op [Noah Frederick sien Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2-Konfigurashon direktemang konvertert ut den

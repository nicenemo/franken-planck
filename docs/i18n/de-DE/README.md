## Layouts

Dieses Repository enthält benutzerdefinierte Tastaturlayouts (Custom Keyboard Layouts) für eine ortholineare Planck-Tastatur.

Alle unten aufgeführten Verzeichnisse nutzen exakt dieselbe Hardwarebasis (Planck v6, 48-Key-Layout):

* **Franken-Planck:** Ein 9-Ebenen-Layout (9-Layer-Layout) mit folgenden funktionalen Merkmalen:
  * `hjkl` Cursortasten (Vim-Stil) unter der Lower-Ebene (Halten der Tasten löst wiederholende Pfeiltasten aus).
  * Home-Row-Modifier.
  * Linkshändiges Num-Pad und rechtshändiges Mouse-Pad.
  * Eine dedizierte Ebene, die alle 24 Funktionstasten enthält.
  * Medientasten und Anwendungsstarter (optimiert für die AutoHotkey-Integration über asiatische Sprachtasten auf der Maus-Ebene).
  * Direkter Zugriff auf Tilde, Backtick und Anführungszeichen auf Ebene 0 (unter Umgehung von Layer-Tap-Restriktionen).
  * Ergonomische Daumensteuerung: Tippen auf Raise führt Backspace aus, Tippen auf Lower führt Delete aus.
  * Integration des ergonomischen NEO2-Layouts (optimiert für Programmierung und mathematische Syntax), bei dem die Umlaute zu doppelten Anführungszeichen sowie einem Doppelpunkt/Semikolon umprogrammiert wurden.
* **Angelas Franken-Planck:** Eine Variante des Franken-Planck-Layouts, die speziell auf Angela zugeschnitten ist.
* **Macropad Angela:** Eine Makro-Pad-Konfiguration, die logisch als Planck-Tastatur operiert.

---

## Verzeichnisstruktur

Die Verzeichnisse sind präzise so strukturiert, dass der QMK-Compiler die Dateien direkt auf das Haupt-Repository abbilden kann. Die PDF-Dateien mit den grafischen Layout-Übersichten befinden sich im Wurzelverzeichnis (Root):

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layout-Übersicht Angela
├── franken-planck.pdf                # Layout-Übersicht Franken-Planck
├── macropad-angela.pdf               # Layout-Übersicht Makro-Pad
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


## Kompilierung

Da sich dieses Repository außerhalb der standardmäßigen QMK-Verzeichnisstruktur befindet, müssen Sie der CLI explizit mitteilen, wo dieses Verzeichnis zu finden ist, bevor Sie einen Build initiieren.

### 1. Overlay verknüpfen

Führen Sie den folgenden Befehl im Wurzelverzeichnis dieses Projekts aus:

qmk config user.overlay_dir="$(realpath .)"


### 2. Firmware bauen

Nutzen Sie die Standard-Kompilierungsbefehle. QMK erkennt und parst die .json-Dateien automatisch, um die Binärdateien zu generieren:

# Franken-Planck bauen
qmk compile -kb planck/rev6 -km franken-planck

# Angela's Planck bauen
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Macropad bauen
qmk compile -kb planck/rev6 -km macropad-angela


---

## Quellen & Referenzen

* Vim-Ebene basierend auf [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Pfeiltasten-Konfiguration unter Lower basierend auf [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2-Konfiguration direkt konvertiert aus dem C-Quellcode von [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

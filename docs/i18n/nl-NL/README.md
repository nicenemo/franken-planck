## Layouts

Deze repository bevat custom keyboard Layouts voor een Planck ortholinear keyboard.

Alle onderstaande mappen maken gebruik van dezelfde hardwarebasis (Planck v6, 48-key layout):

* **Franken-Planck:** Een 9-laags indeling met de volgende functionaliteiten:
  * `hjkl` cursor-toetsen (Vim-stijl) onder de Lower-laag (ingedrukt houden geeft herhalende pijltjes).
  * Home-row modifiers.
  * Links-handig num-pad en rechts-handig mouse-pad.
  * Een aparte laag met alle 24 functieToetsen.
  * Media-keys en applicatie-launchers (gericht op AutoHotkey-integratie via Aziatische taaltoetsen op de muislaag).
  * Directe toegang tot tilde, backtick en quotes op laag 0 (omzeiling van layer-tap restricties).
  * Ergonomische duombiening: Tikken op Raise geeft Backspace, tikken op Lower geeft Delete.
  * Integratie van de ergonomische NEO2-indeling (geoptimaliseerd voor programmeren en wiskundige syntax), waarbij de umlauts zijn hergeprogrammeerd naar dubbele quotes en een dubbele punt/puntkomma.
* **Angelas Franken-Planck:** Een variant op de Franken-Planck, aangepast voor Angela.
* **Macropad Angela:** Een macro-pad configuratie die logisch functioneert als een Planck-toetsenbord.

---

## Mappenstructuur

De mappen zijn zo ingericht dat de QMK-compiler de bestanden direct kan mappen op de hoofd-repository. De PDF-bestanden met grafische lay-outs staan in de hoofdmap:

```text
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
```

## Compileren

Omdat deze repository buiten de standaard QMK-mappenstructuur staat, moet je de CLI eerst vertellen waar deze map te vinden is voordat je compileert.

### 1. Overlay koppelen

Voer dit commando uit in de hoofdmap van dit project:

```text
```

### 2. Firmware bouwen

Gebruik de standaard compileer-opdrachten. QMK pakt automatisch de .json-bestanden op om de firmware te genereren:

```text
# Bouw Franken-Planck
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Bouw Angela's Planck
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Bouw Macropad
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json
```

---

## Bronnen & Referenties

* Vim-layer gebaseerd op [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Pijltoetsen onder Lower gebaseerd op [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2-configuratie geconverteerd vanuit de C-code van [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

## Layouts

This repository contains custom keyboard layouts for a Planck ortholinear keyboard.

See for translations into American English and other languages the documentation in [docs/i18n](docs/i18n)

All directories listed below utilize the exact same hardware base (Planck v6, 48-key layout):

* **Franken-Planck:** A 9-layer layout featuring the following functional capabilities:
  * `hjkl` cursor keys (Vim-style) positioned under the Lower layer (holding the keys triggers repeating arrows).
  * Home-row modifiers.
  * Left-handed num-pad and right-handed mouse-pad.
  * A dedicated layer containing all 24 function keys.
  * Media keys and application launchers (optimized for AutoHotkey integration via Asian language keys mapped on the mouse layer).
  * Direct access to tilde, backtick, and quotes on layer 0 (bypassing layer-tap restrictions).
  * Ergonomic thumb control: Tapping Raise executes Backspace, tapping Lower executes Delete.
  * Integration of the ergonomic NEO2 layout (optimized for programming and mathematical syntax), where the umlauts have been remapped to double quotes and a colon/semicolon.
* **Angelas Franken-Planck:** A variation of the Franken-Planck layout, tailored specifically for Angela.
* **Macropad Angela:** A macro-pad configuration that logically operates as a Planck keyboard.

---

## Directory Structure

The directories are structured precisely so that the QMK compiler can map the files directly onto the main repository. The PDF files containing the graphical layout overviews are located in the root directory:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layout overview Angela
├── franken-planck.pdf                # Layout overview Franken-Planck
├── macropad-angela.pdf               # Layout overview Macropad
├── docs                              # documentation folder
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

Because this repository resides outside the standard QMK directory structure, you must explicitly instruct the CLI where to locate this directory before shipping a build.

### 1. Linking the Overlay

Execute the following command within the root directory of this project:

qmk config user.overlay_dir="$(realpath .)"


### 2. Building the Firmware

Utilize the standard compilation commands. QMK will automatically detect and parse the .json files to generate the binaries:

# Build Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Build Angela's Planck
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Build Macropad
qmk compile -kb planck/rev6 -km macropad-angela


---

## Sources & References

* Vim-layer architecture based on [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Arrow key configuration under Lower based on [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* NEO2 configuration converted directly from the C source of [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

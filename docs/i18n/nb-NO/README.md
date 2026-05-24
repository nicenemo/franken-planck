## Layouts

Dette arkivet (repository) inneholder tilpassede tastaturoppsett (custom keyboard layouts) for et Planck ortolineært tastatur (Planck ortholinear keyboard).

Alle mappene nedenfor bruker nøyaktig samme maskinvarebasis (Planck v6, 48-tasters oppsett):

* **Franken-Planck:** Et 9-lags oppsett med følgende funksjonalitet:
  * `hjkl` piltaster (Vim-stil) under Lower-laget (hvis du holder tastene inne, utløses repeterende piler).
  * Home-row modifiers.
  * Venstrehendt num-pad og høyrehendt mouse-pad.
  * Et eget dedikert lag som inneholder alle de 24 funksjonstastene (F1-F24).
  * Mediataster og applikasjonsstartere (optimalisert for AutoHotkey-integrasjon via asiatiske språktaster mappet på muselaget).
  * Direkte tilgang til tilde, backtick og hermetegn på lag 0 (slik at du går utenom layer-tap-restriksjoner).
  * Ergonomisk tommelstyring: Et trykk på Raise gir Backspace, et trykk på Lower gir Delete.
  * Integrasjon av det ergonomiske NEO2-oppsettet (optimalisert for programmering og matematisk syntaks), hvor tødler (umlauts) er omprogrammert til doble hermetegn og kolon/semikolon.
* **Angelas Franken-Planck:** En variant av Franken-Planck-oppsettet, skreddersydd spesifikt for Angela.
* **Macropad Angela:** En makropad-konfigurasjon som logisk sett fungerer som et Planck-tastatur.

---

## Mappestruktur

Mappene er strukturert slik at QMK-compileren kan mappe filene direkte over på hovedarkivet. PDF-filene med de grafiske layout-oversiktene ligger i rotmappen (root):

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Layoutoversikt Angela
├── franken-planck.pdf                # Layoutoversikt Franken-Planck
├── macropad-angela.pdf               # Layoutoversikt Macropad
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


## Kompilering

Siden dette arkivet ligger utenfor den standard QMK-mappestrukturen, må du eksplisitt fortelle CLI-en hvor denne mappen finnes før du starter kompileringen.

### 1. Koble til Overlay

Kjør denne kommandoen i rotmappen til dette prosjektet:

qmk config user.overlay_dir="$(realpath .)"


### 2. Bygge Firmware

Bruk de standard kompileringskommandoene. QMK vil automatisk fange opp og tolke .json-filene for å generere binærfilene:

# Bygg Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Bygg Angela's Planck
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Bygg Macropad
qmk compile -kb planck/rev6 -km macropad-angela


---

## Kilder & Referanser

* Vim-lagets arkitektur er basert på [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Konfigurasjon av piltaster under Lower er basert på [Noah Fredericks Planck](

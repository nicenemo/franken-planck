## Layouts

Questo repository contiene configurazioni di tastiera (layouts) personalizzate per una tastiera ortolineare Planck.

Tutte le directory elencate di seguito utilizzano esattamente la stessa base hardware (Planck v6, configurazione a 48 tasti):

* **Franken-Planck:** Una configurazione a 9 livelli (layers) che presenta le seguenti funzionalità:
  * Tasti cursore `hjkl` (stile Vim) posizionati sotto il livello Lower (tenendo premuti i tasti si attiva la ripetizione delle frecce).
  * Modificatori sulla riga home (Home-row modifiers).
  * Tastierino numerico (num-pad) per la mano sinistra e tastierino del mouse (mouse-pad) per la mano destra.
  * Un livello dedicato contenente tutti i 24 tasti funzione.
  * Tasti multimediali e scorciatoie di avvio applicazioni (ottimizzati per l'integrazione con AutoHotkey tramite tasti di lingue asiatiche mappati sul livello del mouse).
  * Accesso diretto a tilde (~), backtick (`) e virgolette sul livello 0 (aggirando le restrizioni delle pressioni layer-tap).
  * Controllo ergonomico del pollice: premendo Raise si esegue Backspace, premendo Lower si esegue Delete.
  * Integrazione del layout ergonomico NEO2 (ottimizzato per la programmazione e la sintassi matematica), dove le dieresi (umlauts) sono state rimappate in virgolette doppie e due punti/punto e virgola.
* **Angelas Franken-Planck:** Una variante del layout Franken-Planck, personalizzata specificamente per Angela.
* **Macropad Angela:** Una configurazione di macro-pad che funziona logicamente come una tastiera Planck.

---

## Struttura delle Directory

Le directory sono strutturate in modo preciso in modo che il compilatore QMK possa mappare i file direttamente sul repository principale. I file PDF contenenti le panoramiche grafiche dei layout si trovano nella directory radice (root):

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Panoramica del layout di Angela
├── franken-planck.pdf                # Panoramica del layout Franken-Planck
├── macropad-angela.pdf               # Panoramica del layout del Macropad
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


## Compilazione

Poiché questo repository si trova al di fuori della struttura standard delle directory di QMK, è necessario istruire esplicitamente la CLI su dove trovare questa directory prima di avviare una compilazione.

### 1. Collegamento dell'Overlay

Esegui il seguente comando all'interno della directory radice di questo progetto:

qmk config user.overlay_dir="$(realpath .)"


### 2. Compilazione del Firmware

Utilizza i comandi di compilazione standard. QMK rileverà e analizzerà automaticamente i file .json per generare i file binari:

# Compila Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Compila la Planck di Angela
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Compila il Macropad
qmk compile -kb planck/rev6 -km macropad-angela


---

## Fonti & Riferimenti

* Architettura del livello Vim basata su [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Configurazione dei tasti freccia sotto Lower basata su [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* Configurazione NEO2 convertita direttamente dal codice sorgente in C di [Jan Lunge's Planck Layout](https://blog.heaper.

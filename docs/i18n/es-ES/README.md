## Layouts

Este repositorio contiene configuraciones de teclado (layouts) personalizadas para un teclado ortolineal Planck.

Todos los directorios listados a continuación utilizan exactamente la misma base de hardware (Planck v6, disposición de 48 teclas):

* **Franken-Planck:** Una disposición de 9 capas (layers) que cuenta con las siguientes capacidades funcionales:
  * Teclas de cursor `hjkl` (estilo Vim) posicionadas bajo la capa Lower (mantener presionadas las teclas activa la repetición de las flechas).
  * Modificadores en la fila de inicio (Home-row modifiers).
  * Teclado numérico (num-pad) para la mano izquierda y panel de ratón (mouse-pad) para la mano derecha.
  * Una capa dedicada que contiene las 24 teclas de función.
  * Teclas multimedia y lanzadores de aplicaciones (optimizado para la integración con AutoHotkey a través de teclas de idiomas asiáticos mapeadas en la capa del ratón).
  * Acceso directo a tilde (~), backtick (`) y comillas en la capa 0 (omitiendo las restricciones de las pulsaciones layer-tap).
  * Control del pulgar ergonómico: presionar Raise ejecuta Backspace, presionar Lower ejecuta Delete.
  * Integración de la distribución ergonómica NEO2 (optimizada para programación y sintaxis matemática), donde las diéresis (umlauts) se han remapeado a comillas dobles y dos puntos/punto y coma.
* **Angelas Franken-Planck:** Una variante de la disposición Franken-Planck, diseñada específicamente para Angela.
* **Macropad Angela:** Una configuración de macro-pad que opera lógicamente como un teclado Planck.

---

## Estructura de Directorios

Los directorios están estructurados de forma precisa para que el compilador QMK pueda mapear los archivos directamente en el repositorio principal. Los archivos PDF que contienen las vistas generales de las disposiciones gráficas se encuentran en el directorio raíz:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Vista general del layout de Angela
├── franken-planck.pdf                # Vista general del layout Franken-Planck
├── macropad-angela.pdf               # Vista general del layout del Macropad
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


## Compilación

Debido a que este repositorio se encuentra fuera de la estructura de directorios estándar de QMK, debe indicarle explícitamente a la CLI dónde ubicar este directorio antes de iniciar una compilación.

### 1. Vincular el Overlay

Ejecute el siguiente comando dentro del directorio raíz de este proyecto:

qmk config user.overlay_dir="$(realpath .)"


### 2. Compilar el Firmware

Utilice los comandos de compilación estándar. QMK detectará y analizará automáticamente los archivos .json para generar los binarios:

# Compilar Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Compilar el Planck de Angela
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Compilar el Macropad
qmk compile -kb planck/rev6 -km macropad-angela


---

## Fuentes & Referencias

* Arquitectura de la capa Vim basada en [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Configuración de las teclas de flecha bajo Lower basada en [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* Configuración de NEO2 convertida directamente desde el código fuente en C de [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

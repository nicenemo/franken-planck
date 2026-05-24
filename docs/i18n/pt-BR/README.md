## Layouts

Este repositório contém layouts de teclado personalizados para um teclado ortolinear Planck.

Todos os diretórios listados abaixo utilizam exatamente a mesma base de hardware (Planck v6, layout de 48 teclas):

* **Franken-Planck:** Um layout de 9 camadas (layers) que apresenta os seguintes recursos funcionais:
  * Teclas de cursor `hjkl` (estilo Vim) posicionadas sob a camada Lower (segurar as teclas ativa a repetição das setas).
  * Modificadores na linha inicial (Home-row modifiers).
  * Teclado numérico (num-pad) para a mão esquerda e controle de mouse (mouse-pad) para a mão direita.
  * Uma camada dedicada contendo todas as 24 teclas de função.
  * Teclas de mídia e inicializadores de aplicativos (otimizados for integração com AutoHotkey por meio de teclas de idiomas asiáticos mapeadas na camada do mouse).
  * Acesso direto a til (~), crase (`) e aspas na camada 0 (contornando as restrições de pressionamento layer-tap).
  * Controle ergonômico do polegar: tocar em Raise executa Backspace, tocar em Lower executa Delete.
  * Integração do layout ergonômico NEO2 (otimizado para programação e sintaxe matemática), onde os tremas (umlauts) foram remapeados para aspas duplas e dois-pontos/ponto e vírgula.
* **Angelas Franken-Planck:** Uma variação do layout Franken-Planck, adaptada especificamente para a Angela.
* **Macropad Angela:** Uma configuração de macro-pad que opera logicamente como un teclado Planck.

---

## Estrutura de Diretórios

Os diretórios estão estruturados de forma precisa para que o compilador QMK possa mapear os arquivos diretamente no repositório principal. Os arquivos PDF contendo as visões gerais dos layouts gráficos estão localizados no diretório raiz:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Visão geral do layout - Angela
├── franken-planck.pdf                # Visão geral do layout - Franken-Planck
├── macropad-angela.pdf               # Visão geral do layout - Macropad
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


## Compilação

Como este repositório reside fora da estrutura de diretórios padrão do QMK, você deve instruir explicitamente a CLI sobre onde localizar este diretório antes de iniciar o build.

### 1. Vinculando o Overlay

Execute o seguinte comando dentro do diretório raiz deste projeto:



### 2. Compilando o Firmware

Utilize os comandos padrão de compilação. O QMK detectará e parseará automaticamente os arquivos .json para gerar os binários:

# Compilar Franken-Planck
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Compilar o Planck da Angela
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Compilar o Macropad
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## Fontes & Referências

* Arquitetura da camada Vim baseada em [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Configuração das teclas de seta sob Lower baseada em [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* Configuração NEO2 convertida diretamente do código-fonte em C de [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

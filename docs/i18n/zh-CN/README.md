## 布局 (Layouts)

本仓库包含针对 Planck 48键直列式机械键盘（Ortholinear Keyboard） 的自定义键位映射布局（Keymaps）。

以下所有目录均基于完全相同的硬件基础（Planck v6，48键配置）：

* **Franken-Planck:** 一个包含 9 个图层（Layers）的复杂布局，具备以下核心功能：
  * 在 Lower 图层下配置了 `hjkl` 光标方向键（Vim 风格）（长按按键可触发方向键连续输入）。
  * 主手行修饰键（Home-row modifiers）。
  * 左手数字键盘（Num-pad）与右手鼠标键盘（Mouse-pad）。
  * 包含完整 24 个功能键（F1-F24）的独立专用图层。
  * 媒体控制键与应用程序启动快捷键（通过将亚洲语言键映射至鼠标图层，优化了与 AutoHotkey 的集成）。
  * 在图层 0（Layer 0）上可直接输入 tilde (~)、backtick (`) 和引号，从而绕过了 layer-tap 功能的连击限制。
  * 人体工程学大拇指控制：点按 Raise 触发退格键（Backspace），点按 Lower 触发删除键（Delete）。
  * 集成了针对编程与数学公式语法优化的 NEO2 人体工程学布局，其中分音符（Umlauts）被重新编程为双引号和冒号/分号。
* **Angelas Franken-Planck:** Franken-Planck 布局的变体版本，专为 Angela 量身定制。
* **Macropad Angela:** 一个在逻辑层面上完全模拟 Planck 键盘运行的的宏按键垫（Macro-pad）配置。

---

## 目录结构 (Directory Structure)

目录结构经过精确设计，以便 QMK 编译器能够将文件直接映射到主仓库中。包含图形化布局总览的 PDF 文件位于根目录下：

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Angela 布局总览
├── franken-planck.pdf                # Franken-Planck 布局总览
├── macropad-angela.pdf               # 宏按键垫布局总览
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


## 编译说明 (Compilation)

由于本仓库位于标准 QMK 目录结构之外，在初始化编译构建之前，你必须明确指示 CLI 本目录的所在位置。

### 1. 挂载外部目录 (Linking the Overlay)

请在此项目的根目录下执行以下命令：



### 2. 构建固件 (Building the Firmware)

使用标准的 QMK 编译命令。QMK 会自动检测并解析 .json 文件来生成二进制固件：

# 构建 Franken-Planck 布局
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# 构建 Angela 的 Planck 布局
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# 构建 宏按键垫（Macropad）
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## 来源与参考资料 (Sources & References)

* Vim 图层架构基于 [MacinPlanck](https://macintacos.github.io/macinplanck-configuration)。
* Lower 图层下的方向键配置参考了 [Noah Frederick 的 Planck 布局](https://noahfrederick.com/log/the-planck-keyboard)。
* NEO2 配置直接转换自 [Jan Lunge 的 Planck 布局](https://blog.heaper.de/planck-neo2-config/) 的 C 语言源码。

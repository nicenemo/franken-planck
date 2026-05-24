## 佈局 (Layouts)

本儲存庫包含針對 Planck 48鍵直列式機械鍵盤（Ortholinear Keyboard） 的自訂鍵位映射佈局（Keymaps）。

以下所有目錄均基於完全相同的硬體基礎（Planck v6，48鍵配置）：

* **Franken-Planck:** 一个包含 9 個圖層（Layers）的複雜佈局，具備以下核心功能：
  * 在 Lower 圖層下配置了 `hjkl` 游標方向鍵（Vim 風格）（長按按鍵可觸發方向鍵連續輸入）。
  * 主手行修飾鍵（Home-row modifiers）。
  * 左手數字鍵盤（Num-pad）與右手滑鼠鍵盤（Mouse-pad）。
  * 包含完整 24 個功能鍵（F1-F24）的獨立專用圖層。
  * 媒體控制鍵與應用程式啟動快捷鍵（透過將亞洲語言鍵映射至滑鼠圖層，優化了與 AutoHotkey 的整合）。
  * 在圖層 0（Layer 0）上可直接輸入 tilde (~)、backtick (`) 和引號，從而繞過了 layer-tap 功能的連擊限制。
  * 人體工學大拇指控制：點按 Raise 觸發退格鍵（Backspace），點按 Lower 觸發刪除鍵（Delete）。
  * 整合了針對程式設計與數學公式語法優化的 NEO2 人體工學佈局，其中分音符（Umlauts）被重新程式化為雙引號和冒號/分號。
* **Angelas Franken-Planck:** Franken-Planck 佈局的變體版本，專為 Angela 量身定制。
* **Macropad Angela:** 一個在邏輯層面上完全模擬 Planck 鍵盤運作的巨集按鍵墊（Macro-pad）配置。

---

## 目錄結構 (Directory Structure)

目錄結構經過精確設計，以便 QMK 編譯器能夠將檔案直接映射到主儲存庫中。包含圖形化佈局總覽的 PDF 檔案位於根目錄下：

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Angela 佈局總覽
├── franken-planck.pdf                # Franken-Planck 佈局總覽
├── macropad-angela.pdf               # 巨集按鍵墊佈局總覽
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


## 編譯說明 (Compilation)

由於本儲存庫位於標準 QMK 目錄結構之外，在初始化編譯建置之前，你必須明確指示 CLI 本目錄的所在位置。

### 1. 掛載外部目錄 (Linking the Overlay)

請在此專案的根目錄下執行以下指令：



### 2. 建置韌體 (Building the Firmware)

使用標準的 QMK 編譯指令。QMK 會自動偵測並解析 .json 檔案来產生二進位韌體：

# 建置 Franken-Planck 佈局
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# 建置 Angela 的 Planck 佈局
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# 建置 巨集按鍵墊（Macropad）
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## 來源與參考資料 (Sources & References)

* Vim 圖層架構基於 [MacinPlanck](https://macintacos.github.io/macinplanck-configuration)。
* Lower 圖層下的方向鍵配置參考了 [Noah Frederick 的 Planck 佈局](https://noahfrederick.com/log/the-planck-keyboard)。
* NEO2 配置直接轉換自

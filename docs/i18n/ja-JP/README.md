## レイアウト (Layouts)

本リポジトリには、Planckオーソリニア（直列式）キーボード用のカスタムキーマップ（レイアウト）が格納されています。

以下にリストされているすべてのディレクトリは、まったく同じハードウェアベース（Planck v6、48キーレイアウト）を使用しています：

* **Franken-Planck:** 以下の機能制限や特徴を備えた、多機能な9レイヤー構成のレイアウトです：
  * Lowerレイヤーの下に配置された `hjkl` カーソルキー（Vimスタイル）（キーを長押しすることで矢印が連続入力されます）。
  * ホーム行モディファイア（Home-row modifiers）。
  * 左手用のテンキー（Num-pad）と右手用のマウス操作パッド（Mouse-pad）。
  * 全24個のファンクションキー（F1〜F24）を網羅した独立した専用レイヤー。
  * メディアキーとアプリケーションランチャー（マウスレイヤーにマッピングされたアジア言語入力切り替えキーを介して、AutoHotkeyと高度に連携・最適化されています）。
  * レイヤー0（デフォルトレイヤー）から、チルダ（~）、バックティック（`）、クォーテーションへの直接アクセス（これにより、layer-tap機能による連打制限のストレスを回避します）。
  * 人間工学に基づいた親指コントロール：Raiseをタップするとバックスペース（Backspace）が実行され、Lowerをタップするとデリート（Delete）が実行されます。
  * プログラミングや数学的構文向けに最適化された、人間工学に基づくNEO2レイアウトの統合。ウムラウト（Umlaut）キーは、ダブルクォーテーションおよびコロン/セミコロンにリマップされています。
* **Angelas Franken-Planck:** Franken-Planckレイアウトをベースに、Angela向けに細かくカスタマイズされたバリエーションです。
* **Macropad Angela:** 論理的にPlanckキーボードとして動作する、マクロパッド用のコンフィグレーションです。

---

## ディレクトリ構造 (Directory Structure)

各ディレクトリは、QMKコンパイラがメインリポジトリへ直接ファイルをマッピングできるように正確に構造化されています。グラフィカルなレイアウト図を含むPDFファイルは、ルートディレクトリに配置されています：

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Angela用レイアウト概要
├── franken-planck.pdf                # Franken-Planckレイアウト概要
├── macropad-angela.pdf               # マクロパッドレイアウト概要
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


## コンパイル方法 (Compilation)

本リポジトリは通常のQMKディレクトリ構造の外に配置されているため、ビルドを開始する前に、CLIに対してこのディレクトリの場所を明示的に指定する必要があります。

### 1. オーバーレイのリンク (Linking the Overlay)

このプロジェクトのルートディレクトリで、以下のコマンドを実行します：



### 2. ファームウェアのビルド (Building the Firmware)

標準のコンパイルコマンドを使用します。QMKは自動的に .json ファイルを検出・解析し、バイナリファイルを生成します：

# Franken-Planckのビルド
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Angela用Planckのビルド
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# マクロパッドのビルド
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

##

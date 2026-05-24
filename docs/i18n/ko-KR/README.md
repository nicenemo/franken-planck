## 레이아웃 (Layouts)

본 저장소(repository)는 Planck 오소리니어(직렬식) 키보드를 위한 사용자 정의 키맵(레이아웃)을 포함하고 있습니다.

아래 나열된 모든 디렉토리는 완전히 동일한 하드웨어 베이스(Planck v6, 48키 레이아웃)를 사용합니다.

* **Franken-Planck:** 다음과 같은 기능적 특징을 갖춘 9개 레이어(layer) 구성의 레이아웃입니다:
  * Lower 레이어 아래에 배치된 `hjkl` 커서 키(Vim 스타일)(키를 길게 누르면 화살표가 연속으로 입력됩니다).
  * 홈 로우 모디파이어 (Home-row modifiers).
  * 왼손용 숫자 패드(Num-pad) 및 오른손용 마우스 패드(Mouse-pad).
  * 24개의 기능 키(F1-F24)를 모두 포함하는 전용 레이어.
  * 미디어 키 및 애플리케이션 실행 단축키(마우스 레이어에 매핑된 아시아권 언어 입력 전환 키를 통해 AutoHotkey와의 연동이 최적화되었습니다).
  * 레이어 0(기본 레이어)에서 틸드(~), 백틱(`), 따옴표에 직접 접근 가능(이를 통해 layer-tap 기능의 연타 제한으로 인한 지연을 우회합니다).
  * 인체공학적 엄지손가락 제어: Raise를 탭하면 백스페이스(Backspace)가 실행되고, Lower를 탭하면 딜리트(Delete)가 실행됩니다.
  * 프로그래밍 및 수학적 구문에 최적화된 인체공학적 NEO2 레이아웃의 통합. 움라우트(Umlaut) 키는 큰따옴표 및 콜론/세미콜론으로 리매핑되었습니다.
* **Angelas Franken-Planck:** Franken-Planck 레이아웃을 기반으로 Angela의 사용 환경에 맞춰 세부 조정한 변형 버전입니다.
* **Macropad Angela:** 논리적으로 Planck 키보드와 동일하게 작동하는 매크로 패드(Macro-pad) 구성입니다.

---

## 디렉토리 구조 (Directory Structure)

각 디렉토리는 QMK 컴파일러가 메인 저장소에 파일을 직접 매핑할 수 있도록 정밀하게 구조화되어 있습니다. 그래픽 레이아웃 도면을 포함한 PDF 파일은 루트 디렉토리에 위치해 있습니다.

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Angela 레이아웃 개요
├── franken-planck.pdf                # Franken-Planck 레이아웃 개요
├── macropad-angela.pdf               # 매크로 패드 레이아웃 개요
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


## 컴파일 방법 (Compilation)

본 저장소는 표준 QMK 디렉토리 구조 외부에 위치하므로, 빌드를 시작하기 전에 CLI에 이 디렉토리의 위치를 명확히 지정해야 합니다.

### 1. 오버레이 연결 (Linking the Overlay)

이 프로젝트의 루트 디렉토리에서 다음 명령어를 실행합니다.

qmk config user.overlay_dir="$(realpath .)"


### 2. 펌웨어 빌드 (Building the Firmware)

표준 컴파일 명령어를 사용합니다. QMK는 자동으로 .json 파일을 감지하고 분석하여 바이너리 파일을 생성합니다.

# Franken-Planck 빌드
qmk compile -kb planck/rev6 -km franken-planck

# Angela용 Planck 빌드
qmk compile -kb planck/rev6 -km angelas-franken-planck

# 매크로 패드 빌드
qmk compile -kb planck/rev6 -km macropad-angela


---

## 출처 및 참고 자료 (Sources & References)

* Vim 레이어 설계 아키텍처: [MacinPlanck](https://macintacos.github.io/macinplanck-configuration) 기반.
* Lower 레이어 하단의 화살표 키 설정: [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard) 기반.
* NEO2 설정: [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/)의 C언어 소스 코드에서 직접 변환.

## Розкладки (Layouts)

Цей репозиторій містить власні розкладки клавіатури (keymaps) для ортолінійної клавіатури Planck.

Усі каталоги, перелічені нижче, використовують абсолютно однакову апаратну базу (Planck v6, 48-клавішна розкладка):

* **Franken-Planck:** 9-шарова розкладка, що має такі функціональні можливості:
  * Клавіші керування курсором `hjkl` (у стилі Vim), розташовані під шаром Lower (утримування клавіш активує повторення стрілок).
  * Модифікатори домашнього рядка (Home-row modifiers).
  * Цифрова панель (num-pad) під ліву руку та панель керування мишею (mouse-pad) під праву руку.
  * Окремий виділений шар, що містить усі 24 функціональні клавіші.
  * Медіа-клавіші та ярлики запуску додатків (оптимізовано для інтеграції з AutoHotkey за допомогою клавіш азіатських мов, призначених на шарі миші).
  * Прямий доступ до тильди (~), зворотного апострофа (`) та лапок на шарі 0 (в обхід обмежень подвійного натискання layer-tap).
  * Ергономічне керування великим пальцем: натискання Raise виконує Backspace, натискання Lower виконує Delete.
  * Інтеграція ергономічної розкладки NEO2 (оптимізованої для програмування та математичного синтаксису), де умлаути (umlauts) були перепризначені на подвійні лапки та двокрапку/крапку з комою.
* **Angelas Franken-Planck:** Варіант розкладки Franken-Planck, адаптований спеціально для Анжели.
* **Macropad Angela:** Конфігурація макропаду (macro-pad), яка логічно працює як клавіатура Planck.

---

## Структура каталогів (Directory Structure)

Каталоги структуровані таким чином, щоб компілятор QMK міг безпосередньо відображати файли в головному репозиторії. PDF-файли з графічними оглядами розкладок розташовані в кореневому каталозі (root):

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Огляд розкладки Анжели
├── franken-planck.pdf                # Огляд розкладки Franken-Planck
├── macropad-angela.pdf               # Огляд розкладки макропаду
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


## Компіляція (Compilation)

Оскільки цей репозиторій розташований поза стандартною структурою каталогів QMK, ви повинні чітко вказати CLI, де шукати цей каталог, перед початком збирання.

### 1. Зв'язування накладання (Linking the Overlay)

Виконайте наступну команду в кореневому каталозі цього проєкту:

qmk config user.overlay_dir="$(realpath .)"


### 2. Збирання прошивки (Building the Firmware)

Використовуйте стандартні команди компіляції. QMK автоматично виявить і проаналізує файли .json для генерації бінарних файлів:

# Зібрати Franken-Planck
qmk compile -kb planck/rev6 -km franken-planck

# Зібрати розкладку Planck для Анжели
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Зібрати макропад (Macropad)
qmk compile -kb planck/rev6 -km macropad-angela


---

## Джерела та посилання (Sources & References)

* Архітектура шару Vim базується на проєкті [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Конфігурація клавіш зі стрілками під шаром Lower базується на [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* Конфігурація NEO2 конвертована безпосередньо з вихідного коду C проєкту [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

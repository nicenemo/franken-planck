## Układy klawiszy (Layouts)

To repozytorium zawiera niestandardowe układy klawiszy (keymaps) dla klawiatury ortoliniowej Planck.

Wszystkie katalogi wymienione poniżej korzystają dokładnie z tej samej bazy sprzętowej (Planck v6, układ 48 klawiszy):

* **Franken-Planck:** 9-warstwowy układ oferujący następujące funkcjonalności:
  * Klawisze kursora `hjkl` (w stylu Vim) umieszczone na warstwie Lower (przytrzymanie klawiszy aktywuje powtarzanie strzałek).
  * Modyfikatory w rzędzie domowym (Home-row modifiers).
  * Leworęczny blok numeryczny (num-pad) oraz praworęczny blok myszy (mouse-pad).
  * Wydzielona warstwa zawierająca wszystkie 24 klawisze funkcyjne.
  * Klawisze multimedialne i skróty uruchamiania aplikacji (zoptymalizowane pod kątem integracji z programem AutoHotkey za pomocą klawiszy języków azjatyckich zmapowanych na warstwie myszy).
  * Bezpośredni dostęp do tyldy (~), backticka (`) i cudzysłowów na warstwie 0 (z pominięciem ograniczeń funkcji layer-tap).
  * Ergonomiczna kontrola kciukiem: stknięcie Raise wywołuje Backspace, stknięcie Lower wywołuje Delete.
  * Integracja ergonomicznego układu NEO2 (zoptymalizowanego pod kątem programowania i składni matematycznej), gdzie umlauty zostały przemmapowane na podwójny cudzysłów oraz dwukropek/średnik.
* **Angelas Franken-Planck:** Wariant układu Franken-Planck, dostosowany specjalnie dla Angeli.
* **Macropad Angela:** Konfiguracja typu macro-pad, która logicznie działa jak klawiatura Planck.

---

## Struktura katalogów (Directory Structure)

Katalogi są ustrukturyzowane w precyzyjny sposób, tak aby kompilator QMK mógł bezpośrednio mapować pliki na główne repozytorium. Pliki PDF zawierające graficzne przeglądy układów znajdują się w katalogu głównym (root):

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Przegląd układu Angeli
├── franken-planck.pdf                # Przegląd układu Franken-Planck
├── macropad-angela.pdf               # Przegląd układu Macropada
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


## Kompilacja (Compilation)

Ponieważ to repozytorium znajduje się poza standardową strukturą katalogów QMK, przed rozpoczęciem kompilacji musisz jednoznacznie wskazać interfejsowi CLI lokalizację tego katalogu.

### 1. Linkowanie nakładki (Linking the Overlay)

Uruchom następujące polecenie w katalogu głównym tego projektu:



### 2. Budowanie oprogramowania układowego (Building the Firmware)

Użyj standardowych poleceń kompilacji. QMK automatycznie wykryje i sparsuje pliki .json w celu wygenerowania plików binarnych:

# Budowanie Franken-Planck
qmk compile keyboards/planck/rev6/keymaps/franken-planck/franken-planck.json

# Budowanie Planck Angeli
qmk compile keyboards/planck/rev6/keymaps/angelas-franken-planck/angelas-franken-planck.json

# Budowanie Macropada
qmk compile keyboards/planck/rev6/keymaps/macropad-angela/keymap.json


---

## Źródła i odniesienia (Sources & References)

* Architektura warstwy Vim oparta na projekcie [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Konfiguracja klawiszy strzałek na warstwie Lower oparta na [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard).
* Konfiguracja NEO2 przekonwertowana bezpośrednio z kodu źródłowego C projektu [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/).

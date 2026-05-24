## Layouts

Bu depo (repository), bir Planck ortolineer klavye (Planck ortholinear keyboard) için özel tuş dizilimleri (custom keyboard layouts) içermektedir.

Aşağıda listelenen tüm dizinler tamamen aynı donanım tabanını (Planck v6, 48 tuşlu düzen) kullanmaktadır:

* **Franken-Planck:** Aşağıdaki işlevselliklere sahip 9 katmanlı (layer) bir düzen:
  * Lower katmanının altında `hjkl` imleç tuşları (Vim stili) yer alır (tuşları basılı tutmak okların tekrarlanmasını sağlar).
  * Ana sıra değiştiriciler (Home-row modifiers).
  * Sol el için num-pad ve sağ el için mouse-pad.
  * Tüm 24 fonksiyon tuşunu (F1-F24) içeren ayrı bir katman.
  * Medya tuşları ve uygulama başlatıcılar (fare katmanına eşlenen Asya dili tuşları aracılığıyla AutoHotkey entegrasyonuna yönelik optimize edilmiştir).
  * Katman basma kısıtlamalarını (layer-tap restrictions) baypas ederek Katman 0 üzerinde tilde, backtick ve tırnak işaretlerine doğrudan erişim.
  * Ergonomik başparmak kontrolü: Raise tuşuna basıldığında Backspace, Lower tuşuna basıldığında Delete komutu yürütülür.
  * Programlama ve matematiksel sözdizimi için optimize edilmiş ergonomik NEO2 düzeninin entegrasyonu; bu düzende umlautlar çift tırnak ve iki nokta/noktalı virgül olarak yeniden programlanmıştır.
* **Angelas Franken-Planck:** Franken-Planck düzeninin Angela için özel olarak uyarlanmış bir varyasyonu.
* **Macropad Angela:** Mantıksal olarak bir Planck klavye gibi çalışan bir makro ped (macro-pad) konfigürasyonu.

---

## Dizin Yapısı

Dizinler, QMK derleyicisinin (QMK compiler) dosyaları doğrudan ana depo ile eşleştirebileceği şekilde yapılandırılmıştır. Grafiksel düzen genel görünümlerini içeren PDF dosyaları kök dizinde (root) yer almaktadır:

.
├── LICENSE
├── README.md
├── angelas-franken-planck.pdf        # Düzen genel görünümü Angela
├── franken-planck.pdf                # Düzen genel görünümü Franken-Planck
├── macropad-angela.pdf               # Düzen genel görünümü Makro Ped
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


## Derleme (Compilation)

Bu depo standart QMK dizin yapısının dışında kaldığından, derleme işlemine başlamadan önce CLI'a bu dizinin nerede olduğunu açıkça belirtmeniz gerekir.

### 1. Overlay Bağlantısı Oluşturma

Bu komutu projenin kök dizininde çalıştırın:

qmk config user.overlay_dir="$(realpath .)"


### 2. Donanım Yazılımını (Firmware) Derleme

Standart derleme komutlarını kullanın. QMK, ikili dosyaları (binaries) oluşturmak için .json dosyalarını otomatik olarak algılayıp ayrıştıracaktır:

# Franken-Planck Derleme
qmk compile -kb planck/rev6 -km franken-planck

# Angela'nın Planck'ını Derleme
qmk compile -kb planck/rev6 -km angelas-franken-planck

# Makro Ped Derleme
qmk compile -kb planck/rev6 -km macropad-angela


---

## Kaynaklar & Referanslar

* Vim katmanı mimarisi [MacinPlanck](https://macintacos.github.io/macinplanck-configuration) çalışmasına dayanmaktadır.
* Lower altındaki ok tuşu konfigürasyonu [Noah Frederick's Planck](https://noahfrederick.com/log/the-planck-keyboard) çalışmasını temel almaktadır.
* NEO2 konfigürasyonu, doğrudan [Jan Lunge's Planck Layout](https://blog.heaper.de/planck-neo2-config/) C kaynak kodundan dönüştürülmüştür.

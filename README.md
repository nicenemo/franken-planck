# Franken-Planck

Franken-Planck is my evolving 14 layer custom keymap for a 47 key Rev 6. Planck Keyboard. 
Ideas from others were assimilated in Borg like fashion. Resistance is futile, I am a Cyclon |)

The Francken-Planck Layout firmwate was created with the online [QMK Configurator](https://config.qmk.fm).
It is just a JSON file that can be turned into C code and baked into firmware. Either using QMK's online tooling or locally  with the [QMK CLI tools](https://docs.qmk.fm/#/cli).

My workflow is as follows:

1. Upload the francken-planck.json to the above mentioned site
2. Adjust the layout to changed I consider to be a good idea.
3. Download the JSON of the changed keymap
4. Create a PDF to use as a cheat cheat.
5. Change the JSON into a _keymap.c_ C code file using the qmk command line tooling.
6. Copy the C code into my keymap in the qmk source tree
7. Build the firmware using _qmk compile_
8. Flash the firmware to my keyboard using _qmk flash_
9. Commit made changes to this repository

The include frankenplank.pdf is a printable layout of the current version.

## Own ideas

Ideas I considered to be my own, or which I could not recall where I had seen it before, but I am sure I assimilated and twisted them.

_Please if you think I got it from you or anybody else, let me know and I will add it to the list of assimilated ideas_

* My media key layer which is accessible by holding space. Media keys such as volume up and mute and the media player. A complete set of keys can be accessed with either the left or right hand.
* Both a left and right hand mouse layer.
* Both a left and right hand num pad
* A layer with all 24 Function keys.
* A layer with all the Asian language related keys, I want to sort out whether I can use these as application lauchers from [AutoHotkey](https://www.autohotkey.com/)
* Tapping raise is enter and Tapping lower is backspace so they can be used with the thumbs
* Moving shift keys next to raise/lower so that they can be used with the thumbs like in some split layout such as the [Kyria](https://blog.splitkb.com/blog/introducing-the-kyria)
* Tapping the left modifier keys for big arrow movements, Home, Page-Down, Page-Up, End.
* Holding the the raise or lower gives me repeatable arrow keys and also a caps lock under escape, if I might ever need that.
* I swapped tilde and backtick from lower and raise. I tend to use tilde more, since that is a home directory in Linux.

## Assimilated ideas

* Vim layer [MacinPlanck](https://macintacos.github.io/macinplanck-configuration). I am still looking into this, since this is MAC specific, and I am using Windows and Linux.
* Making arrow keys available [Noah Fredricl's Planck](https://noahfrederick.com/log/the-planck-keyboard)
  _Sadly this custom layout with some extra coding for macros does not work for a Rev6_ I think I got close with using just the JSON file.
* Raise space does backspace and  Lower space does delete. _Not sure who I stole that one from _

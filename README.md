# Franken-Planck

Franken-Planck is my evolving 8 layer custom keymap for a 47 key Rev 6. Planck Keyboard. 
Ideas from others were assimilated in Borg like fashion. _Resistance is futile, I am a Cyclon |)_

1. hjkl cursor keys
2. home row modifiers
3. left num-pad
4. right mouse-pad
5. num-pad style function keys layer
6. media key layer
7. start calculator and other apps layer
8. NEO2 layer
9. Hyper key on ESC

The Franken-Planck Layout firmware was created with the online [QMK Configurator](https://config.qmk.fm).
It is just a JSON file that can be turned into C code and baked into firmware. Either using QMK's online tooling or locally  with the [QMK CLI tools](https://docs.qmk.fm/#/cli).

You can use the online configurator.

## Own ideas

Ideas I considered to be my own, or which I could not recall where I had seen it before, but I am sure I assimilated and twisted them.

_Please if you think I got it from you or anybody else, let me know and I will add it to the list of assimilated ideas_

* separate media layer.
* A right-hand mouse layer.
* A left-hand num-pad
* A layer with all 24 Function keys.
* Asian languages related keys on the mouse layer. I want to sort out whether I can use these as application lauchers from [AutoHotkey](https://www.autohotkey.com/)
* Tapping raise is backspace and tapping lower is delete.
* Holding the lower gives me repeatable arrow keys under `hijkl`.
* Below `hjkl` for bigger movements
* Having tilde, backtick, quote and double quote available on layer zero without using modifiers was a happy work around for not being able to use modifiers in combination with layer tap in QMK. At least not without some additional code.
* NEO2 layout sticky on layer 1.

## Initial Assimilated ideas

* Vim layer [MacinPlanck](https://macintacos.github.io/macinplanck-configuration).
* Making arrow keys available [Noah Fredricl's Planck](https://noahfrederick.com/log/the-planck-keyboard)
  _Sadly this custom layout with some extra coding for macros does not work for a Rev6_ I think I got close with using just the JSON file.
* Raise space does backspace and  Lower space does delete. _Not sure who I stole that one from_

## Move to Neo2

I discovered [Neo2](https://neo-layout.org) in a video by [Jan Lunge](https://www.youtube.com/watch?v=rhdMVXlnQIM), an alternative keyboard layout optimized for the German language and programming and mathematics.
It is said to work well for English too. Dutch is close enough to German so that that would work well too. It has special layers for programming and mathematics. However, moving away from the known QUERTY, QUERTZ or AZERTY layout might be challenging.

On Android NEO2 is available as a keyboard Layout under the German language. I gave it a try. Although it was still a bit of hunt and peck, it still felt more comfortable and faster than QUERTY and certainly something I wanted learn.

## My NEO2 adaptation

Jan  kindly shared his [Planck layout](https://blog.heaper.de/planck-neo2-config/). I converted his `keymap.c` to JSON using the QMK toolkit. I uploaded this to the QMK configurator and started to copy his NEO2 adaptation for the Planck into my own config.
 As a Dutch native I do not use umlauts so I repurposed those keys for colon/semicolon and double quotes.

## keymap layers

[keymap layers pdf](franken-planck.pdf)

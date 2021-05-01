# lexaloffle

This is a miscellaneous collection of code and material related to products by Lexaloffle Games LLP.

## PICO-8 file format routines

The PICO-8 fantasy game console stores game cartridges in one of several documented file formats. The most canonical file format is the [P8PNG](https://pico-8.fandom.com/wiki/P8PNGFileFormat) format (`.p8.png`), an encoding of the game data stored stegonographically with a PNG image of the game's "cartridge." The Lua code for a cartridge is compressed using one of two documented proprietary methods: the legacy `:c:` method and the newer `pxa` method.

This repository contains C routines that can compress and decompress data using the two methods:

* `pxa_compress_snippets.c`: the PXA method, supported by PICO-8 versions 0.2.0 and newer
* `p8_compress.c`: the legacy `:c:` method, supported by all versions of PICO-8
  * This includes `FUTURE_CODE` that was injected for forwards compatibility with PICO-8 0.1.7. This was added to the default wrapper code in PICO-8 0.1.8 and no longer needs to be injected by the save routine.

This code was created and officially released by Lexaloffle Games LLP under open source licenses. See each file for the text of the license.

For a Python implementation of the complete P8PNG format including stegonographic decoding, see [picotool](https://github.com/dansanderson/picotool). (As of this writing, picotool only supports `:c:` compression.)

For a prose description of the file formats and compression algorithms, see [P8PNGFileFormat in the PICO-8 wiki](https://pico-8.fandom.com/wiki/P8PNGFileFormat).

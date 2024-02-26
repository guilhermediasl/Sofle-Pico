---
layout: page
title: Drag-and-drop
# permalink: /pcb-ordering
parent: Flashing
nav_order: 1
---

# Flashing Sofle Pico using 'drag-n-drop'
1. Make sure halves are not connected together with TRRS cable.
1. Connect one half to USB.
1. Enter the bootloader using any of the following methods. These are dependant on where your RP2040 came from. You may have to remove an OLED to access the `BOOT` button.
    * Hold down `BOOT` and tap `RESET`.
    * Hold the `BOOT` button while pluging in the usb cable.
    * Double tapping the `RESET` button on the RP2040. ([Double tap reset is enabled by default on the RP2040](https://github.com/qmk/qmk_firmware/blob/master/platformdev_RP2040.md#double-tap-reset-boot-loader-entry-iddouble-tap)).
    * **Bootmagic reset** (works after you have flashed once): Hold down the top far corner key while plugging in the keyboard (`~` left half, `-` right half). This will also clear the EEPROM.
1. Wait for the OS to detect the device.
1. Copy the .uf2 file to the new USB disk.
  * The files can be found in this repo at `./Sofle_Pico/Firmware`. The VIA version is recommended: `sofle_pico_via_LH.uf2` and `sofle_pico_via_RH.uf2`.
  * There is a different file for right hand and left hand, as denoted by a `_RH` or `_LH` suffix.
  * On Mac after the file is dropped, the 'Keyboard setup assistant' may be triggered. You can ignore and quit the assistant.(@todo add relative path to UF2 files.) 
1. Unplug the side you just flashed, and repeat the process with the other side.
1. Disconnect both halves from USB.
1. Connect both halves together using the TRRS cable. 
1. Connect the left half to USB.
1. Test everything using VIA. (See [details below](#via)).

### Flashing the second time around
After the fist flash, subsequent flashes are even easier. Sofle Pico uses [Bootmagic lite](https://github.com/qmk/qmk_firmware/blob/master/feature_bootmagic.md). You can enter boot mode by holding down the upper-left-most key while pluggin in the USB cable. (Or upper-right-most, respectively). Once your in boot mode, the Pico appears as a drive, and you can drag and drop the new `.uf2` file.



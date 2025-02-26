# Marlin Configuration for **Kingroon KP3S 3D Printer**

This repository contains the **Configuration** files needed to
compile your the MARLIN firmware for **Kingroon KP3S 3D Printer**.

I have also included the **Robin_nano.bin** firmware files you can copy directly to your SD card to in

It uses the KP3S configuration from [Marlin/Configuration repo](https://github.com/dulfe/Kingroon-KP3S-Marlin) as a base and some modifications to make it work with this board.

**This configuration has been tested with Marlin 2.1.x**

## Notes
- It uses a modified version of the **MKS Robin Nano** board named **Kingroon KP3 v1.3**
- It uses **TMC2225** drivers which are compatible to **A4988**.
- Stock firmware uses Marlin Emulation mode in the TFT screen that communicates with the mainboard using G-Codes, but uses an old MKS UI library (not supported by stock Marlin)
- Marlin Emulation mode (a.k.a. Modern UI) currently only supported with TFT35 screens, so TFT24 needs to use full TFT.
  
Even thought the PID values have been taken from the default configuration file, I found out it is better to calibrate it yourself.
## **Calibration Sources**
- [3dmakerengineering](https://www.3dmakerengineering.com/blogs/3d-printing/pid-tuning-marlin-firmware)
- [Teaching Tech Github](https://teachingtechyt.github.io/calibration.html#intro)

## My current config
- Stock, no ABL
- Will update as I go and create branches

---
# **USE IT AT YOUR OWN RISK**
## I am not responsible for any 3D printer converted into a glorified paper weight!
---

# Compilation Instructions
## This is if you need to modify and recompile your firmware

### Expert:

If you have done it before for any printer using Marlin, then just copy both configuration files to your marlin source code and compile as normal.

### Not So Expert (NSE):
If you are new to that, you can:

- Install [Visual Studio Code](https://code.visualstudio.com/Download)
- Install [PlatformIO Visual Studio Code Extension](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide)
- Install [Auto Build Marlin Extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=MarlinFirmware.auto-build).
- Download the latest MARLIN code from [Marlin Official Site](https://marlinfw.org/meta/download/)
- Unpack it (lets say you did it into `c:\sources\marlin`)
- Copy this repo `Configuration.h` and `Configuration_avd.h` to the folder `Marlin` inside the folder you just created in the previous step. (lets say `c:\sources\marlin\Marlin`)
- Follow [Auto Build Marlin](https://marlinfw.org/docs/basics/auto_build_marlin.html) usage instructions.

## Installation

- Rename the BIN file generated in the previous step to `Robin_nano.bin` (if you use the NSE method, the file is `<marlin source>\.pio\build\mks_robin_nano35\Robin_nano35.bin`)
- Copy that file to your Micro SD (backup your original Micro SD so you have the stock firmare just in case you want to go back)
- Make sure to delete the old files from the Micro SD.
- Take that Micro SD and put it in your printer.
- Turn ON your printer.
- It will update automatically.


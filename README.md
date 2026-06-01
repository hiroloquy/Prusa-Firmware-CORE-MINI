# Prusa CORE MINI Firmware

This repository contains the modified firmware for **Prusa CORE MINI**, a CoreXY conversion project based on the **Original Prusa MINI+** by Prusa Research.

Prusa CORE MINI reuses several parts from the Original Prusa MINI+, including the Buddy board, LCD, motors, rods, heatbed, and other components, while redesigning the frame, XY motion system, Z axis, and printhead assembly.

This firmware is based on **Prusa-Firmware-Buddy** and has been modified for the Prusa CORE MINI hardware configuration.

> [!WARNING]
> This firmware is intended for an experimental custom printer based on the Original Prusa MINI+.
> It is provided as-is, without any warranty.
> Flashing and using this firmware is entirely at your own risk.

## Supported printer

- Prusa CORE MINI

## Configuration

The main CORE MINI-specific configuration is located in the MINI configuration files:

- `include/marlin/Configuration_MINI.h`
- `include/marlin/Configuration_MINI_adv.h`

Other configuration files for MK3.5, MK3.9, MK4, XL, CORE One, etc. are inherited from the upstream Prusa-Firmware-Buddy repository and are not the target of this project.

## Status

This firmware is currently in an early prototype stage.

Basic functions such as homing, mesh bed leveling, heating, and printing have been tested on the prototype machine, but further tuning and validation are still in progress.

## Credits

This project is based on Prusa-Firmware-Buddy by Prusa Research.  
[https://github.com/prusa3d/Prusa-Firmware-Buddy](https://github.com/prusa3d/Prusa-Firmware-Buddy)

Prusa-Firmware-Buddy itself includes work from the open-source firmware community, including:

- [Marlin](https://marlinfw.org/) - 3D printing core firmware
- [Klipper](https://www.klipper3d.org/) - input shaper code based on Klipper

## Acknowledgements

Prusa CORE MINI would not have been possible without the Original Prusa MINI+, the Buddy board, and the open-source hardware and firmware published by Prusa Research.

Many thanks to Prusa Research and the open-source 3D printing community for making projects like this possible.

## Getting Started

### Requirements

- Python 3.8 or newer
- Python `requests` package, installed via pip or your system package manager

### Cloning this repository

Run `git clone https://github.com/hiroloquy/Prusa-Firmware-CORE-MINI.git`.

### Building

Build the firmware using the MINI preset:

```bash
python3 utils/build.py --preset mini --build-type release
```

The binaries will be stored under `./build/products`.

#### Windows 10 troubleshooting

If you have Python installed and in your PATH but still get the CMake error `Python3 not found`, try running `python` and `python3` from Command Prompt.

If one of them opens the Microsoft Store instead of starting the Python interpreter or showing an error such as `'python3' is not recognized as an internal or external command, operable program or batch file`, open `Manage app execution aliases` and disable the App Installer associations with `python.exe` and `python3.exe`.

### Development

The build process of this project is driven by CMake and `build.py` is just a high-level wrapper around it. As most modern IDEs support some kind of CMake integration, it should be possible to use almost any editor for development. Below are some documents describing how to set up some popular text editors.

- [Visual Studio Code](doc/editor/vscode.md)
- [Vim](doc/editor/vim.md)
- [Eclipse, STM32CubeIDE](doc/editor/stm32cubeide.md)
- [Other LSP-based IDEs (Atom, Sublime Text, ...)](doc/editor/lsp-based-ides.md)

#### Contributing

If you want to contribute to the codebase, please read the [Contribution Guidelines](doc/contributing.md).

## Flashing Custom Firmware

To install custom firmware on the Buddy board, you need to break the appendix on the board.  
Learn more in the following Prusa article:
[https://help.prusa3d.com/article/flashing-custom-firmware-mini-mini_14](https://help.prusa3d.com/article/flashing-custom-firmware-mini-mini_14)

## License

The firmware source code is licensed under the GNU General Public License v3.0 and the graphics and design are licensed under Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0). Fonts are licensed separately (see [LICENSE](LICENSE.md)).

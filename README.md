# die-hard-nakatomi-plaza-die-hard-trilogy
## Die Hard: Nakatomi Plaza - Die Hard Trilogy Remake
A total conversion project that rebuilds the three-game arcade structure of *Die Hard Trilogy* (1996) — action, driving, and light-gun shooting — inside the first-person engine and Nakatomi Plaza setting of *Die Hard: Nakatomi Plaza* (2002), built on the open-sourced LithTech engine source.

## Github Treeview
[https://treegit.macosxjs.com/?url=igiteam/die-hard-nakatomi-plaza-die-hard-trilogy](https://treegit.macosxjs.com/?url=igiteam/die-hard-nakatomi-plaza-die-hard-trilogy)

## Github Tree Api Direct JSON
[https://api.github.com/repos/igiteam/die-hard-nakatomi-plaza-die-hard-trilogy/git/trees/main?recursive=1](https://api.github.com/repos/igiteam/die-hard-nakatomi-plaza-die-hard-trilogy/git/trees/main?recursive=1)

## Base of the gameplay
[![Die Hard: Nakatomi Plaza (2002) - PC Gameplay 4k 2160p / Win 10](https://img.youtube.com/vi/_u7VVN11oyE/maxresdefault.jpg)](https://ytembed.macosxjs.com/?X3U3VlZOMTFveUU)

## Reference Links
[https://archive.org/details/Die_Hard_Nakatomi_Plaza_USA](https://archive.org/details/Die_Hard_Nakatomi_Plaza_USA)

[https://archive.org/details/die-hard-trilogy.-7z](https://archive.org/details/die-hard-trilogy.-7z)

[![Die Hard: Nakatomi Plaza Editing Package](https://media.moddb.com/images/members/5/4014/4013508/profilenolf/009.png)](https://www.moddb.com/games/die-hard-nakatomi-plaza/downloads/die-hard-nakatomi-plaza-editing-package)

[![How to make custom levels for Die Hard: Nakatomi Plaza](https://media.moddb.com/images/members/5/4014/4013508/profilenolf/004.png)](https://www.moddb.com/games/die-hard-nakatomi-plaza/tutorials/how-to-make-custom-levels-for-die-hard-nakatomi-plaza)

[https://media.moddb.com/cache/images/downloads/1/283/282570/thumb_620x2000/Untitled.png](https://media.moddb.com/cache/images/downloads/1/283/282570/thumb_620x2000/Untitled.png)

[![Die Hard Trilogy PSX](https://img.youtube.com/vi/X4wulMtgLWc/maxresdefault.jpg)](https://ytembed.macosxjs.com/?WDR3dWxNdGdMV2M)

[![Michael Kamen - Wild Percussion](https://img.youtube.com/vi/LCAwcWt1F-E/maxresdefault.jpg)](https://ytembed.macosxjs.com/?TENBd2NXdDFGLUU)

---

## WS11WineCX20.0.4 (MacOSX Big Sur 32bit)
[WS11WineCX20.0.4.tar.7z](https://github.com/vitor251093/porting-kit-engines/releases/download/wineskin/WS11WineCX20.0.4.tar.7z)

[![wine windows games on macosx](https://raw.githubusercontent.com/igiteam/igi1-macbook-3d-workstation/refs/heads/main/wine-engine-config.png)](https://github.com/igiteam/wine_engines)

---

# Die Hard Trilogy decompilation *in progress*

A byte-matching decompilation of Die Hard Trilogy (PlayStation, 1996), with a native PC port to follow. See `docs/code-map.md` for where the code lives on the disc and `docs/compiler-notes.md` for the toolchain.

This repository contains no game data. You need your own copy of the game.

## Progress

<p align="center">
  <a href="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp"><img alt="Code matched" src="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp.svg?label=Code%20matched&measure=matched_code_percent&style=for-the-badge"></a>
  <a href="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp"><img alt="Functions" src="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp.svg?label=Functions&measure=matched_functions&style=for-the-badge"></a>
</p>
<p align="center">
  <a href="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp"><img alt="Die Hard" src="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp.svg?label=Die%20Hard&measure=matched_code_percent&category=dh1&style=for-the-badge"></a>
  <a href="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp"><img alt="Die Harder" src="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp.svg?label=Die%20Harder&measure=matched_code_percent&category=dh2&style=for-the-badge"></a>
  <a href="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp"><img alt="With a Vengeance" src="https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp.svg?label=With%20a%20Vengeance&measure=matched_code_percent&category=dh3&style=for-the-badge"></a>
</p>

The badges count bytes of each game's code that build from matching C, and link to the full breakdown on [bytematch.dev](https://bytematch.dev/FeverDreams420/die-hard-trilogy-decomp). `python3 tools/progress.py` prints the same figures from a local build.

`make report` writes them to `build/report.json` in objdiff's report format, with one unit per C file and one category per game. `make upload-progress` checks the build, then sends that report for the current commit, which updates the badges. It needs the project's upload token, either in `BYTEMATCH_TOKEN` or in `~/.bytematch_token`, and no uncommitted changes. Keep the token out of the repo.

If you want to help, you can see the code map here: [View Code Map](docs/code-map.md)


## Build environment

The project builds under **WSL2 (Ubuntu 24.04)**. The repo lives on the Windows side at `C:\src\die-hard-trilogy-decomp`, which WSL sees as `/mnt/c/src/die-hard-trilogy-decomp`, so Windows tools (Ghidra, DuckStation) and the Linux build share one copy.

Ubuntu packages:

```
sudo apt install binutils-mips-linux-gnu make git python3 python3-venv
```

## Setup

1. Extract the disc's files into `disc/` (git-ignored), then check them against the known hashes:
   ```
   .venv/bin/python tools/extract_disc.py "/path/to/Die Hard Trilogy (USA) (Rev 1) (Track 01).bin" disc
   cd disc && sha1sum -c ../config/hashes.txt
   ```
2. Copy the Linux builds of the PS1 GCC compilers into `tools/gcc-<version>/` (git-ignored).
3. Install the Python tools into a virtual environment (see `tools/README.md` once it exists).

## Layout

| Folder | Contents |
| --- | --- |
| `config/` | splat configs, `symbol_addrs.txt`, `hashes.txt` |
| `asm/` | splat output (generated, git-ignored) |
| `src/` | C sources: `main/`, then one folder per game |
| `include/` | game headers; `include/psyq/` for Sony SDK headers |
| `tools/` | maspsx, compilers, scripts |
| `docs/` | code map, findings, compiler notes |
| `disc/` | your extracted game files (git-ignored) |
| `build/` | build outputs (git-ignored) |


## Dev Environment

**Official White Wii Remote With Nunchuk — Tested And Working — £14.99**
[https://www.ebay.co.uk/itm/800847189353](https://www.ebay.co.uk/itm/800847189353)

**Infrared Sensor Bar USB for Wii Emulator Remote Motion Detection Setup — £6.69**
[https://www.ebay.co.uk/itm/227423830875](https://www.ebay.co.uk/itm/227423830875)

**Apple MacBook Pro Retina 15in (2014) i7 2.8GHz 16GB 1TB SSD GT 750M — £120.30**
[https://www.ebay.co.uk/itm/800844561513](https://www.ebay.co.uk/itm/800844561513)

**WS11WineCX20.0.4 (Wine engine)**
[https://igiteam.github.io/wine_engines/](https://igiteam.github.io/wine_engines/)

**Official Genuine Sony PS3 PlayStation 3 DualShock 3 Wireless Controller Black — £19.99**
[https://www.ebay.co.uk/itm/840031043465](https://www.ebay.co.uk/itm/840031043465)

**Amazon Basics 4K HDMI Cable 3m — 18Gbps High Speed with Ethernet, 4K@60Hz, 2160p — £8.44**
[https://www.ebay.co.uk/itm/327352257557](https://www.ebay.co.uk/itm/327352257557)

**wiimote_nunchuk_macosx**
[https://github.com/igiteam/wiimote-nunchuk](https://github.com/igiteam/wiimote-nunchuk)

**xbox360_input_gui_py**
[https://github.com/igiteam/xbox360_input_gui_py](https://github.com/igiteam/xbox360_input_gui_py)

**logitec_mx_mouse_3_macos**
[https://github.com/igiteam/logitec_mx_mouse_3_macos](https://github.com/igiteam/logitec_mx_mouse_3_macos)

**igi1-macbook-3d-workstation**
[https://github.com/igiteam/igi1-macbook-3d-workstation](https://github.com/igiteam/igi1-macbook-3d-workstation)

---


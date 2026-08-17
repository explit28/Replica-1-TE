# Briel's Replica-1-TE Rev. 3 (2010)

This repository is a maintained fork of the original **Briel Computers Replica-1-TE Rev. 3** repository:

https://github.com/Retrotink/Replica-1-TE

The goal of this fork is to preserve the original Replica-1-TE design files, make the repository easier to browse, and add practical improvements for building and using the machine today.

## Modifications in This Fork

- Unpacked and reorganized the original archive files
- Added a modified **Parallax P8X32A Propeller Display/TV driver with PAL composite video support**
- Improved PAL output for use with modern PAL LCD TVs
- Added a BOM / parts list derived from the original Replica-1-TE manual
- Preserved original NTSC and firmware files for reference and rollback

## PAL Video Support

The original Replica-1-TE firmware was designed primarily for **NTSC composite video**.

This fork contains a modified Propeller display/TV backend providing proper **PAL composite output** while retaining the original Replica-1-TE 40×24 character display and the TE keyboard/serial architecture.

The PAL implementation uses:

- PAL 50 Hz timing
- 312-line frame
- 4.433618 MHz PAL reference frequency
- 320-pixel active text display
- 40 × 24 character layout
- monochrome black/white text output
- timing optimized for improved text clarity on modern PAL LCD TVs

Working PAL source:

`Firmware/P8X32A/char_mode_08_TV_PAL_PARALLAX_V1.spin`

Original/known-good NTSC files are preserved alongside it.

## Repository Contents

### `Firmware/`

Firmware and binary images used by the Replica-1-TE.

- `6502.rom0x100 irq address .bin` — original 6502-side ROM binary preserved from the source archive.
- `P8X32A/` — source and EEPROM image for the Parallax P8X32A Propeller used for video, keyboard and serial I/O.

Important Propeller files:

- `replica 1TE IOREV04.spin` — top-level Replica-1-TE Propeller firmware.
- `replica 1TE IOREV04.eeprom` — compiled EEPROM image for the 24LC256.
- `char_mode_08.spin` — 40×24 character-display and font handling.
- `char_mode_08_TV.spin` — active TV/composite backend.
- `char_mode_08_TV_Original.spin` — preserved original TV driver.
- `char_mode_08_TV_NTSC_GOOD.spin` — known-good NTSC backup.
- `char_mode_08_TV_PAL_PARALLAX_V1.spin` — modified PAL TV backend.
- `char_mode_09.spin` / `char_mode_09_TV.spin` — alternate character-mode object names retained by the original firmware layout.
- `Keyboard.spin` / `keyboard.spin` — keyboard handling sources.
- `Serial_IO.spin` — serial I/O integration.
- `FullDuplex.spin` / `fullduplex.spin` — full-duplex serial helper.

### `Gerber Files/`

PCB manufacturing data for the Replica-1-TE Rev. 3.

- `r1terev3.zip` — Gerber fabrication archive.
- `readme` — short description of the Gerber package.

### `Manuals/`

Original and related documentation.

- `r1temanJUL2010.pdf` — Replica-1-TE setup, user and kit-assembly manual. The kit inventory/BOM is on pages 13–15.
- `replica1TEschematic.pdf` — Replica-1-TE schematic.
- `Apple1Manual.pdf` — Apple-1 operation/reference manual.
- `Apple1Basic.pdf` — Apple-1 BASIC documentation.
- `krusader12.pdf` — Krusader assembler manual.
- `Slot Expander I board.pdf` — Slot Expander I documentation.
- `mos_hardware.pdf` — MOS Technology hardware reference material.

### `Software/`

Apple-1 software collection in text/source form, including games and utilities such as Acey Ducey, Blackjack, Bowling, Craps, Disassembler, FIG-Forth, Hammurabi, Life, Lunar, Mastermind, Microchess, Nim, Star Trek and Wumpus.

The `Software/BASIC/` directory contains additional BASIC programs such as ELIZA, Checkers, Hangman, Gomoku, Word Search and Yahtzee.

## BOM

The Excel BOM derived from the original Replica-1-TE manual is:
https://github.com/Retrotink/Replica-1-TE/Replica-1-TE_Rev3_BOM.xlsx


## Firmware Build

The Propeller firmware is written in **Spin/PASM**.

With OpenSpin, the top-level firmware can be compiled to a 24LC256 EEPROM image, for example:

```bash
openspin -e "replica 1TE IOREV04.spin"
```

Keep a backup of a known-working EEPROM image before testing modified firmware.

## Photos

### Replica-1-TE Rev. 3 from 2010

<img width="2560" height="1920" alt="Replica_1_TE3" src="https://github.com/user-attachments/assets/2f17fa03-fc75-4cc8-81f5-b762c55fe4bb" />

### Replica-1-TE Rev. 0 from 2007

![replica1TEDETAILS](https://github.com/Retrotink/Replica-1-TE/assets/121696513/3de8c58d-4384-4ac6-88e8-9ecb62998096)

## Original Project

Original repository:

https://github.com/Retrotink/Replica-1-TE

The Replica-1 was designed by Vince Briel / Briel Computers as a modern recreation of the Apple-1 computer.

## Status

- Replica-1-TE Rev. 3 files: **preserved**
- Repository cleanup/reorganization: **in progress**
- PAL Propeller video driver: **working**
- BOM reconstruction: **manual-derived spreadsheet created; schematic verification still recommended**

Contributions, corrections and additional information about the Replica-1-TE Rev. 3 are welcome.

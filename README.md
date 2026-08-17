# Briel's Replica-1-TE Rev. 3 (2010)

This repository is a maintained fork of the original **Briel Computers Replica-1-TE Rev. 3** repository:

https://github.com/Retrotink/Replica-1-TE

The goal of this fork is to preserve the original Replica-1-TE design files while making the repository easier to use and adding several practical improvements.

## Modifications in This Fork

* Unpacked and reorganized the original archive files
* Added a modified **Parallax P8X32A Propeller Display/TV driver with PAL composite video support**
* Improved PAL output for use with modern PAL LCD TVs
* Added a BOM / parts list (**work in progress**)
* Preserved the original Replica-1-TE Rev. 3 design and firmware files

## PAL Video Support

The original Replica-1-TE firmware was designed primarily for **NTSC composite video**.

This fork contains a modified Propeller TV/display driver providing proper **PAL composite output** while retaining the original Replica-1-TE 40×24 character display.

The PAL implementation uses:

* PAL 50 Hz video timing
* 312-line frame
* 4.433618 MHz PAL reference frequency
* 320-pixel active text display
* 40 × 24 character layout
* monochrome black/white text output
* PAL timing optimized for improved text clarity on modern LCD TVs

On PAL LCD displays, the modified driver produces noticeably sharper character output than the original NTSC firmware.

The PAL modification affects the **display/TV driver only**. The Replica-1-TE keyboard, serial interface, Apple-1 interface and other I/O functionality remain based on the original Replica-1-TE firmware.

## Hardware

The Replica-1-TE Rev. 3 is an Apple-1 compatible computer designed by **Briel Computers**.

Among other components, the Rev. 3 uses a **Parallax P8X32A Propeller** as its I/O controller for functions including:

* Composite video generation
* PS/2 keyboard interface
* ASCII keyboard interface
* Serial communication

The Propeller firmware is stored in a **24LC256 EEPROM** and can be rebuilt and programmed independently.

## Repository Structure

The repository contains the original Replica-1-TE Rev. 3 design material together with the modifications from this fork.

Depending on the directory, this includes:

* Schematics
* PCB/design files
* Propeller firmware sources
* Apple-1 software
* Documentation
* BOM / component information

The original compressed archives have been unpacked and rearranged to make the individual files easier to browse and use.

## Firmware

The firmware is written in **Spin/PASM** for the Parallax P8X32A Propeller.

The PAL modification is implemented in the Display/TV driver while retaining the original higher-level Replica-1-TE firmware.

For the PAL version, the relevant display driver is based on the Replica-1-TE character display code with the low-level video generation adapted for proper PAL timing.

### Building

The firmware can be compiled with a compatible Propeller Spin compiler such as **OpenSpin**.

Example:

```bash
openspin -e "replica 1TE IOREV04.spin"
```

This generates an EEPROM image suitable for the **24LC256** used by the Replica-1-TE.

Always keep a backup of a known-working EEPROM image before testing modified firmware.

## BOM

A Bill of Materials for the Replica-1-TE Rev. 3 is being reconstructed and verified.

**Status: Work in progress**

Some original documentation does not provide manufacturer part numbers or exact mechanical specifications for every component, so the BOM should currently be treated as a reference rather than a production-ready PCBA BOM.

## Photos

<img width="2560" height="1920" alt="Replica-1-TE Rev. 3" src="https://github.com/user-attachments/assets/2f17fa03-fc75-4cc8-81f5-b762c55fe4bb" />

### Original Replica-1-TE Rev. 3

![Replica-1-TE Details](https://github.com/Retrotink/Replica-1-TE/assets/121696513/3de8c58d-4384-4ac6-88e8-9ecb62998096)

## Original Project

This repository is based on the original Replica-1-TE repository:

https://github.com/Retrotink/Replica-1-TE

The **Replica-1** was designed by Vince Briel / Briel Computers as a modern recreation of the Apple-1 computer.

This fork is intended to preserve that work while adding documentation, organization and firmware improvements useful for building and operating the Replica-1-TE Rev. 3 today.

## Status

* Replica-1-TE Rev. 3 files: **preserved**
* Repository cleanup/reorganization: **in progress**
* PAL Propeller video driver: **working**
* BOM reconstruction: **in progress**

Contributions, corrections and additional information about the Replica-1-TE Rev. 3 are welcome.

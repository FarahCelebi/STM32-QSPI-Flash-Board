# STM32-QSPI-Flash-Board

A high-speed QSPI interface board: an STM32F407VG reading and writing an
external W25Q128JVS NOR flash chip over a full 4-bit Quad-SPI bus.

**Status: schematic complete, PCB layout in progress.**

## Overview

This board pairs the STM32F407's QUADSPI peripheral (Bank1) with a 16MB
Winbond flash chip, intended as fast external storage for applications like
data logging or firmware staging — workloads where a single-bit SPI EEPROM
would be too slow.

## What's done so far

- Power architecture: 6×VDD with individual decoupling, VDDA isolated
  through a ferrite bead, dedicated VCAP regulator capacitors, NRST/BOOT0
  handling
- QUADSPI bus (CLK, NCS, IO0-IO3) wired between the STM32 and the flash chip,
  using ST's documented Bank1 pin mapping (PB2, PB6, PD11, PD12, PD13, PE2)
- Schematic passes ERC with 0 violations

## Coming next

- PCB layout with controlled-impedance and length-matched QUADSPI routing
- DRC-clean board, Gerber generation

## Tools

- KiCad

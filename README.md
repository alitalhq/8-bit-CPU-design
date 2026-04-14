# 8-Bit CPU Design

A simple 8-bit CPU designed and simulated in **Logisim-Evolution v4.1.0**.

## Overview

This project implements a basic 8-bit CPU from scratch using digital logic components. The design covers all fundamental building blocks of a CPU, wired together into a working simulation.

## Circuit Modules

| Module | Description |
|--------|-------------|
| `main` | Top-level circuit connecting all components |
| `ALU` | Arithmetic Logic Unit — performs addition and logic operations |
| `Register` | 8-bit general-purpose register |
| `MAR` | Memory Address Register |
| `Memory` | RAM module for data storage |
| `Decimal_Decode` | Decodes binary output to 7-segment display |

## Project Files

| File | Description |
|------|-------------|
| `8-bit-CPU-design.circ` | Main Logisim-Evolution circuit file |
| `RAM File` | Memory initialization file — loaded into RAM at simulation start |
| `Decimal Decoder File` | Lookup table used by the Decimal_Decode module |

## Control Signals (Main Circuit)

The main circuit exposes the following control pins:

| Signal | Direction | Description |
|--------|-----------|-------------|
| `WE1`–`WE7` | Input | Write Enable signals for each register/memory unit |
| `OE1`–`OE8` | Input | Output Enable signals for each register/memory unit |
| `Count_Enable` | Input | Enables the Program Counter to increment |
| `Counter_OE` | Input | Enables Program Counter output onto the bus |
| `Internal_OE` | Input | Enables internal data bus output |
| `OE_Testing_Data` | Input | Output enable for external test data |
| `OE_Testing_Data2` | Input | Secondary output enable for external test data |

## Bus Structure

| Bus | Width | Description |
|-----|-------|-------------|
| Internal Data Bus | 8-bit | Connects registers and ALU internally |
| External Data Bus | 8-bit | Interface for external read/write |
| Internal Address Bus | 4-bit | Selects memory address internally |
| External Address Bus | 4-bit | External memory addressing |

## Screenshots

### Main Circuit
![Main Circuit](images/main.png)

### ALU
![ALU](images/ALU.png)

### Register
![Register](images/register.png)

### MAR
![MAR](images/MAR.png)

### Memory
![Memory](images/memory.png)

### Decoder
![Decoder](images/decoder.png)

## Requirements

- **[Logisim-Evolution v4.1.0](https://github.com/logisim-evolution/logisim-evolution/releases/tag/v4.1.0)** or later

> **Warning:** This file was created with Logisim-Evolution v4.1.0. Opening it in the original Logisim (by Carl Burch) or older versions may cause issues — component pin positions and sizes differ between the two applications, which can break wire connections and require manual fixes.

## Usage

1. Download and install [Logisim-Evolution v4.1.0+](https://github.com/logisim-evolution/logisim-evolution/releases)
2. Open `8-bit-CPU-design.circ`
3. Load `RAM File` into the RAM component via **right-click → Load Image**
4. Use the **Simulate** menu to start the clock and step through the circuit

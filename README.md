# Vending Machine Controller - Verilog FSM

A vending machine controller implemented as a Finite State Machine (FSM) in Verilog HDL. Designed and simulated using Xilinx Vivado.

---

## Overview

This project models a vending machine that accepts coins of 10, 20, and 50 denominations and dispenses an item once the total reaches 40 or more. It also handles change when the inserted amount exceeds 40.

---

## Features

- 9-state Moore FSM tracking cumulative coin input
- Supports three coin types — 10, 20, and 50
- Automatically dispenses item when total reaches 40
- Change output signal activated when total exceeds 40
- Synchronous reset that brings the machine back to the initial idle state
- Clean separation of state transition logic and output logic

---

## State Details

- Sin is the initial idle state with 0 total
- S10 means 10 has been inserted
- S20 means 20 has been inserted
- S30 means 30 has been inserted
- S40 and above means item is dispensed — S50, S60, S70, S80 also return change

---

## Coin Encoding

- 2'b00 represents a 10 coin
- 2'b01 represents a 20 coin
- 2'b10 represents a 50 coin

---

## Module Ports

- coin (input, 2-bit) — coin inserted by the user
- clk (input, 1-bit) — clock signal
- reset (input, 1-bit) — active-high synchronous reset
- Z (output, 1-bit) — goes high when item is dispensed
- change_given (output, 1-bit) — goes high when change is returned

---

## File Structure

The src folder contains vending_machine.v which is the main FSM module.

---

## How to Simulate

Clone the repository and open Xilinx Vivado. Create a new project and add the file inside the src folder as a design source. Run Behavioral Simulation, apply a clock signal, toggle reset, and provide coin inputs to observe state transitions and output behavior.

You can also simulate online by pasting the source code into EDA Playground at edaplayground.com.

---

## Tools Used

- Xilinx Vivado for RTL design and simulation
- Verilog HDL for hardware description

---

## Author

Aakankshith Sangarsu
Electronics and Communication Engineering
GITAM School of Technology, Hyderabad

---

## License

This project is open-source under the MIT License.

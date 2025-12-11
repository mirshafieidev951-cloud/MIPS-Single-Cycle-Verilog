# 32-bit Single-Cycle MIPS Processor in Verilog ⚡

This repository contains a Verilog implementation of a **32-bit Single-Cycle MIPS Processor**. The design aims to execute a subset of the MIPS Instruction Set Architecture (ISA) without any internal pipeline delays, suitable for educational simulation and FPGA prototyping.

This project was developed as part of the **Computer Architecture & Microprocessors** course at Sharif University of Technology.

## 📄 Technical Report
For a detailed explanation of the Control Unit design, datapath diagrams, and critical path analysis, please refer to the full project report:
👉 **[Download Project Report (PDF)](docs/single_cycle_report.pdf)**

## 🛠 Supported Instructions
The processor successfully implements the following MIPS instructions:

* **R-Type (Arithmetic & Logic):** `add`, `sub`, `addu`, `subu`, `and`, `or`, `xor`, `nor`, `slt`, `sltu`
* **I-Type (Immediate & Branching):** `addi`, `addiu`, `slti`, `sltiu`, `andi`, `ori`, `xori`, `lui`, `lw`, `sw`, `beq`, `bne`

## 🧩 Architecture Highlights
* **Modular Design:** The processor is built using distinct modules (ALU, Register File, Instruction Memory, Data Memory, Control Unit) defined in `building_blocks.v`.
* **Control Unit:** A dedicated combinatorial logic block that generates control signals (RegDst, ALUSrc, MemtoReg, etc.) based on the Opcode and Funct fields.
* **Memory Mapped I/O:** Supports separate Instruction and Data memories (Harvard Architecture concept for simulation).

## 🧪 Verification & Simulation
The design has been verified using two robust testbenches:

1.  **Basic Testbench:** Validates individual instructions (ALU operations, Memory R/W, Branching) to ensure basic functionality.
2.  **Insertion Sort (ISORT) Algorithm:** The processor successfully executes a complex assembly program (`isort32`) that sorts an array of integers. This test confirms the correct interaction between instructions, memory, and control logic over thousands of clock cycles.

## 🚀 How to Run
1.  Open the project in a Verilog simulator (e.g., ModelSim, Vivado, or Icarus Verilog).
2.  Compile `src/building_blocks.v` and `src/single_cycle_mips.v`.
3.  Load the desired testbench from the `testbench/` folder (e.g., `single_cycle_mips_tb_isort.v`).
4.  Ensure the corresponding `.hex` file (machine code) is in the simulation directory so the instruction memory can initialize.
5.  Run the simulation.

---
*Controller Designed by Mirshafiei*

# CS-385 Course Project

Course project for Computer Architecture.  
[Circuit diagrams](./digital) are drawn in [Digital](https://github.com/hneemann/Digital).

## Description
Design a simplified version of a MIPS machine and write a Verilog program that describes its structure and simulates its functioning. Use gate-level modeling for all components unless otherwise specified. The machine should include the following components:

1. <u>General purpose registers (register file)</u>:
   * 4 registers, 16-bit long, numbered 0 - 3.
   * Register $0 must contain 0 (read-only).
   * Implemented in behavioral modeling.
2. <u>Other registers</u>:
   * 16-bit program counter, pipeline registers.
   * Implemented by reg vectors in Verilog.
3. <u>Instruction Memory</u>:
   * Word size: 16 bits
   * Word addressed, size: 1024 bytes
   * Implemented by reg array in Verilog.
4. <u>Data Memory</u>:
   * Word size: 16 bits
   * Word addressed, size: 1024 bytes
   * Implemented by reg array in Verilog.
5. <u>ALU</u>:
   * 16-bit data, 4-bit control.
   * Functions: and, or, nor, nand, add, sub, slt, Zero.
   * Implemented at gate-level.
6. <u>Main Control unit</u>: Behavioral model.
7. <u>Branch Control unit</u>: Gate-level model.
8. <u>Other components necessary to connect the main components</u>:
   * Multiplexers implemented at gate-level.
   * Sign-extend in behavioral modeling.

## Instruction Set

| Instruction | Opcode |
|-------------|-------:|
| add         |   0000 |
| sub         |   0001 |
| and         |   0010 |
| or          |   0011 |
| nand        |   0101 |
| slt         |   0110 |
| addi        |   0111 |
| lw          |   1000 |
| sw          |   1001 |
| beq         |   1010 |
| bne         |   1011 |

## Instruction Format

R-format (add, sub, and, or, nor, nand, slt)

| op | rs | rt | rd | unused |
|----|----|----|----|--------|
| 4  | 2  | 2  | 2  | 6      |
I-format (addi, lw, sw, beq, bne)

| op | rs | rt | address/value |
|----|----|----|---------------|
| 4  | 2  | 2  | 8             |

## Progress Reports

### Progress Report 1

A simpilfied single-cycle datapath capable of executing all R-type and immediate arithmetic instructions (add, sub, and, or, nor, nand, slt, addi).  
Major components: Instruction memory, ALU, and Register File.

### Progress Report 2

Complete single-cycle datapath. Implement all instructions and run a complete test program as explained in section "Testing".

### Progress Report 3

Using the architecture and the instruction format for the 16-bit CPU described in the Semester Project design and implement a 3-stage pipelined datapath capable of executing all R-type and immediate arithmetic instructions (add, sub, and, or, nor, nand, slt, addi). The stages are IF, ID and a third stage combining EX, MEM and WB stages of the 5-stage standard MIPS pipeline.

### Final Report

Implement the final version of the complete (5-stage) pipelined datapath.

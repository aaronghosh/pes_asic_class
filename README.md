# VLSI Physical Design for ASICs

Welcome to the VLSI Physical Design for ASICs course repository offered by PES University and taught by Kunal Ghosh. This repository contains files and resources to guide you through the process of ASIC design from scratch, focusing on the RISC-V architecture. You'll learn how to translate high-level languages into physical layout designs.

## Table of Contents
- [Introduction](#introduction)
- [Flow Overview](#flow-overview)
- [Tools and Prerequisites](#tools-and-prerequisites)
- [Course Structure](#course-structure)
  - [Day 1](./DAY1#day-1-introduction-to-riscv-isa-and-gnu-compiler-toolchain)
  - [Day 2](./DAY2#day-2-introduction-to-abi-and-basic-verification-flow)
  - [Day 3](./DAY3#day-3-introduction-to-verilog-rtl-design-and-synthesis)
  - [Day 4](./DAY4#day-4-introduction-to-timing-labs)
  - [Day 5](./DAY5#day-5-combinational-and-sequential-optimizations) - [Details Below]
  - [Day 6](./DAY6#day-6-gls-synthesis-solution-mismatch) - [Details Below]

## <a name="introduction"></a>Introduction
This repository provides essential materials to guide you through the ASIC design flow, starting from the fundamentals and leading to physical layout design. You will gain a comprehensive understanding of the entire process.

## <a name="flow-overview"></a>Flow Overview
1. **HLL (High-Level Language)**: Understand the basics of high-level programming languages such as C and C++.
2. **ALP (Assembly Level Program)**: Dive into assembly language programming and its importance in CPU architecture.
3. **HDL (Hardware Description Language)**: Explore hardware description languages like Verilog, System Verilog, and VHDL for designing digital circuits.
4. **GDS (Graphic Data System)**: Learn about layout design using tools like Klayout and Magic.

## <a name="tools-and-prerequisites"></a>Tools and Prerequisites
Before you begin, make sure you have the necessary tools and prerequisites installed on your system. You can follow the provided installation script to set up the required environment. The installation script is provided in the [run_ubuntu.sh](./run_ubuntu.sh) file.

## <a name="course-structure"></a>Course Structure
### <a name="day-1-introduction-to-riscv-isa-and-gnu-compiler-toolchain"></a>Day 1: Introduction to RISC-V ISA and GNU Compiler Toolchain
- Learnt about Instruction Set Architecture (ISA) and its importance in CPU functionality.
- Understood the RISC-V ISA, an open-source and customizable instruction set.
- Explored various extensions in the RISC-V ISA, such as integer, floating-point, and atomic instructions.
- Compiled and executed programs using both C compiler and RISC-V compiler.

### <a name="day-2-introduction-to-abi-and-basic-verification-flow"></a>Day 2: Introduction to ABI and Basic Verification Flow
- Dove into Application Binary Interface (ABI) and its role in software-hardware interaction.
- Discovered the basics of verification flow and how it ensures proper design functionality.
- Explored compressed instruction formats that optimize code size while maintaining functionality.
- Learnt about supervisor-level instructions for managing system operations.

### <a name="day-3-introduction-to-verilog-rtl-design-and-synthesis"></a>Day 3: Introduction to Verilog RTL Design and Synthesis
- Introduction to Verilog, a programming language used for designing and simulating digital systems.
- Understanding key concepts like modules, ports, signals, combinational logic, sequential logic, clock, and edges.
- Hands-on experience with GTKWave labs and an introduction to Yosys, an RTL synthesis framework for digital design.

### <a name="day-4-introduction-to-timing-labs"></a>Day 4: Introduction to Timing Labs
- Exploring timing libraries and their significance in ASIC design.
- Understanding hierarchical and flat synthesis.
- Synthesizing flip-flops with various coding styles and optimizations.

### <a name="day-5-combinational-and-sequential-optimizations"></a>Day 5: Combinational and Sequential Optimizations
- Combinational Logic Optimization
      
    -Introduction to optimizing combinational logic circuits.
    -Techniques for reducing gate count and improving performance.
    -Examples of constant propagation and boolean logic optimization.
-Sequential Logic Optimization
    
    -Introduction to optimizing sequential logic circuits.
    -Techniques for reducing flip-flop count and improving timing.
    -Sequential constant propagation and state optimization.

-Retiming
      
      Explanation of retiming as a technique to optimize sequential circuits.
      How retiming helps improve the performance of a design.
      Sequential Logic Cloning

Overview of sequential logic cloning as an optimization technique.
Use cases and benefits of cloning sequential logic elements.

### <a name="day-6-gls-synthesis-solution-mismatch"></a>Day 6: GLS, Synthesis Solution Mismatch

-Gate Level Simulation (GLS)

    Introduction to GLS and its importance in post-synthesis verification.
    Using GLS to verify the functionality and timing requirements of a design.
    Synthesis Solution Mismatch

-Common reasons for synthesis simulation mismatches.
    Identifying issues such as missing sensitivity lists and non-standard Verilog coding.
    How to debug and resolve synthesis simulation mismatches.


## Conclusion
The aim of this course is to gain a solid understanding of the complete ASIC design flow, from programming in high-level languages to creating layout designs.

---



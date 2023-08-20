
# VLSI Physical Design for ASICs

## Objective
The primary aim of VLSI (Very Large Scale Integration) physical design for ASICs (Application-Specific Integrated Circuits) is to transform a logical design description (RTL - Register Transfer Level) into a physical layout that can be fabricated as an integrated circuit. This involves translating the high-level functional representation of the circuit into a physical implementation that meets design constraints, performance targets, and manufacturability requirements.

## Skill Outcomes
- Architectural Design
- RTL Design / Behavioral Modeling
- Floorplanning
- Placement
- Clock Tree Synthesis
- Routing

## Installation
You can find the installation script [here](https://github.com/kunalg123/riscv_workshop_collaterals/blob/master/run.sh).

To run the installation:
1. Download the `run.sh` script.
2. Open your terminal.
3. Navigate to the `Downloads` directory using the command `cd Downloads`.
4. Execute the script using `./run.sh`.

## Table of Contents
### [DAY 1](#day-1)
- [Introduction to RISCV ISA and GNU Compiler Toolchain](#introduction-to-riscv-isa-and-gnu-compiler-toolchain)
- [Introduction to Basic Keywords](#introduction-to-basic-keywords)
  - [Introduction](#introduction)
  - [From Apps to Hardware](#from-apps-to-hardware)
- [Detailed Course Content Description](#detailed-course-content-description)
- [Labwork for RISCV Toolchain](#labwork-for-riscv-toolchain)
  - [C Program](#c-program)
  - [RISCV GCC Compiler and Disassemble](#riscv-gcc-compiler-and-disassemble)
  - [Spike Simulation and Debug](#spike-simulation-and-debug)
  - [Integer Number Representation](#integer-number-representation)

### [DAY 2](#day-2)
- [Introduction to ABI and Basic Verification Flow](#introduction-to-abi-and-basic-verification-flow)
  - [Application Binary Interface (ABI)](#application-binary-interface-abi)
- [Memory Allocation for Double Words](#memory-allocation-for-double-words)
- [Load, Add, and Store Instructions](#load-add-and-store-instructions)
- [32-Registers and Their ABI Names](#32-registers-and-their-abi-names)
- [Labwork using ABI Function Calls](#labwork-using-abi-function-calls)
  - [Algorithm for C Program using ASM](#algorithm-for-c-program-using-asm)
  - [Review ASM Function Calls](#review-asm-function-calls)
  - [Simulate C Program using Function Call](#simulate-c-program-using-function-call)

### [ISA (Instruction Set Architecture)](#isa-instruction-set-architecture)
ISA defines how a computer's hardware and software interact. It encompasses instructions, addressing modes, data types, registers, memory organization, and execution mechanisms.

**[RISC-V (Reduced Instruction Set Computing - Five)](#risc-v-reduced-instruction-set-computing---five)**
An open-source ISA gaining prominence in computer architecture and semiconductor design. RISC architectures focus on a smaller set of instructions, often leading to faster execution.

### [From Apps to Hardware](#from-apps-to-hardware)
Applications, system software, operating systems, compilers, and assemblers together form a layered approach to computing, bridging the gap between user tasks and hardware operations.

### [Detail Description of Course Content](#detail-description-of-course-content)
- [Pseudo Instructions](#pseudo-instructions) simplify coding patterns (e.g., li, mv).
- [Base Integer Instructions](#base-integer-instructions) for arithmetic and logic (e.g., add, sub, and, or, xor, sll).
- [Multiply Extension Instructions](#multiply-extension-instructions) enhance multiplication capabilities (e.g., mul, mulh).
- [Single and Double Precision Floating Point Extensions](#single-and-double-precision-floating-point-extensions) for accurate calculations (F and D extensions).
- [Application Binary Interface (ABI)](#application-binary-interface-abi) rules for software interaction.
- [Memory Allocation and Stack Pointer](#memory-allocation-and-stack-pointer) management.
- [Load, Add, and Store Instructions](#load-add-and-store-instructions) for data manipulation.
- [32-Registers and Their ABI Names](#32-registers-and-their-abi-names) to standardize register usage.

### [Labwork for RISCV Toolchain](#labwork-for-riscv-toolchain)
- [C Program](#c-program) Calculate sum from 1 to n.
- [RISCV GCC Compiler and Disassemble](#riscv-gcc-compiler-and-disassemble) Compile and view assembly code.
- [Spike Simulation and Debug](#spike-simulation-and-debug) Verify instruction correctness.
- [Integer Number Representation](#integer-number-representation) Understand signed and unsigned numbers.

### [Application Binary Interface (ABI)](#application-binary-interface-abi)
ABI defines rules for binary code interaction, enabling different software components to work seamlessly. It governs function calls, parameter passing, memory allocation, and more.

### [Memory Allocation for Double Words](#memory-allocation-for-double-words)
Learn to load 64-bit numbers into memory using little-endian and big-endian representations.

### [Load, Add, and Store Instructions](#load-add-and-store-instructions)
Master fundamental operations for data manipulation in assembly programming.

### [32-Registers and Their ABI Names](#32-registers-and-their-abi-names)
Understand the significance of ABI names for registers and their roles in software compatibility and communication.

### [Labwork using ABI Function Calls](#labwork-using-abi-function-calls)
Implement algorithms, simulate programs, and review ASM function calls for effective code generation.

### [Algorithm for C Program using ASM](#algorithm-for-c-program-using-asm)
Integrate assembly language code with C programs using inline assembly or separate files.

## Simulation
Compile the code and execute the object file using Spike for thorough testing and debugging.

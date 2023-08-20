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
### DAY 1
- Introduction to RISCV ISA and GNU Compiler Toolchain
- Introduction to Basic Keywords
  - Introduction
  - From Apps to Hardware
- Detailed Course Content Description
- Labwork for RISCV Toolchain
  - C Program
  - RISCV GCC Compiler and Disassemble
  - Spike Simulation and Debug
  - Integer Number Representation

### DAY 2
- Introduction to ABI and Basic Verification Flow
  - Application Binary Interface (ABI)
- Memory Allocation for Double Words
- Load, Add, and Store Instructions
- 32-Registers and Their ABI Names
- Labwork using ABI Function Calls
  - Algorithm for C Program using ASM
  - Review ASM Function Calls
  - Simulate C Program using Function Call

### ISA (Instruction Set Architecture)
ISA defines how a computer's hardware and software interact. It encompasses instructions, addressing modes, data types, registers, memory organization, and execution mechanisms.

*RISC-V (Reduced Instruction Set Computing - Five)*
An open-source ISA gaining prominence in computer architecture and semiconductor design. RISC architectures focus on a smaller set of instructions, often leading to faster execution.

### From Apps to Hardware
Applications, system software, operating systems, compilers, and assemblers together form a layered approach to computing, bridging the gap between user tasks and hardware operations.

### Detail Description of Course Content
- Pseudo Instructions simplify coding patterns (e.g., li, mv).
- Base Integer Instructions for arithmetic and logic (e.g., add, sub, and, or, xor, sll).
- Multiply Extension Instructions enhance multiplication capabilities (e.g., mul, mulh).
- Single and Double Precision Floating Point Extensions for accurate calculations (F and D extensions).
- Application Binary Interface (ABI) rules for software interaction.
- Memory Allocation and Stack Pointer management.
- Load, Add, and Store Instructions for data manipulation.
- 32-Registers and their ABI Names to standardize register usage.

### Labwork for RISCV Toolchain
- C Program: Calculate sum from 1 to n.
- RISCV GCC Compiler and Disassemble: Compile and view assembly code.
- Spike Simulation and Debug: Verify instruction correctness.
- Integer Number Representation: Understand signed and unsigned numbers.

### Application Binary Interface (ABI)
ABI defines rules for binary code interaction, enabling different software components to work seamlessly. It governs function calls, parameter passing, memory allocation, and more.

### Memory Allocation for Double Words
Learn to load 64-bit numbers into memory using little-endian and big-endian representations.

### Load, Add, and Store Instructions
Master fundamental operations for data manipulation in assembly programming.

### 32-Registers and Their ABI Names
Understand the significance of ABI names for registers and their roles in software compatibility and communication.

### Labwork using ABI Function Calls
Implement algorithms, simulate programs, and review ASM function calls for effective code generation.

### Algorithm for C Program using ASM
Integrate assembly language code with C programs using inline assembly or separate files.

## Simulation
Compile the code and execute the object file using Spike for thorough testing and debugging.

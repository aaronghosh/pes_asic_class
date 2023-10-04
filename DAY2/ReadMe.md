# Lab 2
### RISC-V Instructions:

RISC-V instructions can be categorized into different categories based on their functionality. Here are some common types of RISC-V instructions:

- **R-Type Instructions:** These are used for arithmetic and logic operations between two source registers, storing the result in a destination register. Common R-type instructions include:
  - `add`: Addition
  - `sub`: Subtraction
  - `and`: Bitwise AND
  - `or`: Bitwise OR
  - `xor`: Bitwise XOR
  - `slt`: Set Less Than (signed)
  - `sltu`: Set Less Than (unsigned)

- **I-Type Instructions:** These are used for arithmetic and logic operations that involve an immediate value (constant) and a source register. Common I-type instructions include:
  - `addi`: Add Immediate
  - `andi`: Bitwise AND with Immediate
  - `ori`: Bitwise OR with Immediate
  - `xori`: Bitwise XOR with Immediate
  - `lw`: Load Word (load data from memory)
  - `sw`: Store Word (store data to memory)
  - `beq`: Branch if Equal
  - `bne`: Branch if Not Equal

- **S-Type Instructions:** These are similar to I-type instructions but are used for storing values from a source register into memory. Common S-type instructions include:
  - `sb`: Store Byte
  - `sh`: Store Halfword
  - `sw`: Store Word

- **U-Type Instructions:** These are used for setting large immediate values into registers or for jumping to an absolute address. Common U-type instructions include:
  - `lui`: Load Upper Immediate (set the upper bits of a register)
  - `auipc`: Add Upper Immediate to PC (used for address calculations)

- J-Type Instructions: These are used for jumping or branching to different program locations. Common J-type instructions include:
  - `jal`: Jump and Link (used for function calls)
  - `jalr`: Jump and Link Register (used for function calls)

- **F-Type and D-Type Instructions (Floating-Point):** These instructions are used for floating-point arithmetic and include various operations like addition, multiplication, and comparison. These instructions typically have an 'F' or 'D' prefix to indicate single-precision or double-precision floating-point operations.
  - `fadd.s`: Single-precision floating-point addition
  - `fmul.d`: Double-precision floating-point multiplication
  - `fcmp.s`: Single-precision floating-point comparison

- **RV64 and RV32 Variants:** RISC-V can be configured in different bit-widths, with RV64 being a 64-bit architecture and RV32 being a 32-bit architecture. Instructions for these variants have slightly different encoding to accommodate the different data widths.
![instr](https://devopedia.org/images/article/110/3808.1535301636.png)

RISC-V instructions have a common structure with several fields that serve different purposes. The specific fields may vary depending on the type of instruction (R-type, I-type, S-type, U-type, etc.), but here are the typical fields you'll find in a RISC-V instruction:

- **Opcode (OP):** The opcode field specifies the operation to be performed by the instruction. It indicates what type of instruction it is (e.g., arithmetic, load, store, branch) and what specific operation within that type is being carried out.

- **Destination Register (rd):** This field specifies the destination register where the result of the instruction should be stored. In R-type instructions, this is often the first source register. In I-type and S-type instructions, this is sometimes used to specify the target register.

- **Source Register(s) (rs1, rs2):** These fields specify the source registers for the operation. For R-type instructions, rs1 and rs2 are typically the two source registers. In I-type and S-type instructions, rs1 is the source register, and immediate values may be used in place of rs2.

- **Immediate (imm):** The immediate field contains a constant value that is used as an operand in I-type and S-type instructions. This value can be an immediate constant, an offset, or an immediate value for arithmetic or logical operations.

- **Function Code (funct3, funct7):** In R-type and some I-type instructions, these fields further specify the operation. funct3 typically selects a particular function within an opcode category, and funct7 may provide additional information or further differentiate the instruction.

- **Extension-specific Fields:** Depending on the RISC-V extension being used (e.g., F for floating-point, M for integer multiplication/division), there may be additional fields to accommodate the specific requirements of that extension. These fields are not part of the base RISC-V instruction format.

### Register Naming in RISC-V according to ABI

![abi-reg](https://web.eecs.utk.edu/~smarz1/courses/ece356/notes/risc/imgs/regfile.png)

## ASM calls in C

Create a C file, [sum1to9.c]
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/956dabac-6ad5-4011-bd65-f74a12158242)

In the same directory, we have our load function, [load.S] in assembly.
```asm
.section .text
.global load
.type load, @function
; function takes in 10, which is stored in a1
load:
        add  a4, a0, zero    ; a4 initialized with 0x0
        add  a2, a0, a1      ; store 10 in a2, which is stored in a1
        add  a3, a0, zero    ; a3 will store intermediate sum, initializing it with 0
loop:   add  a4, a3, a4      ; a4 stores final sum which is added at each point in the loop
        addi a3, a3, 1       ; increments a3, which is the value that has to be added at each stage
        blt  a3, a2, loop    ; loop if a3 is less than 10
        add  a0, a4, zero    ; a0 stores final result
        ret
```

Compile the above C code with the Ofast optimization. Remember to include the assembly file as well, and then view the output using spike.
```bash
riscv64-unknown-elf-gcc -01 -mabi=lp64 -march=rv64i -o 1to9.o 1to9.c load.S
spike pk -o 1to9.o 
```
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/9080897b-370c-4687-b2df-0c324c04c413)

# C code on a RISC V CPU

Clone this repo to get started.
```
git clone https://github.com/kunalg123/riscv_workshop_collaterals.git
```
cd into the labs directory within the repo, and then make the rv32im.sh an executeable
```
chmod 777 rv32im.sh
./rv32im.sh
```

- First taking a look at the rv32im.sh file, we can see that we first compile the 1to9.c code using 32 bit arch. We also compile the load.S file.
- Next Syscalls.c is compiled.
- We then link the load.o and 1to9_custom.c into a firmware.elf file.
- start.elf is compiled, and then converted to verilog.
- Same is done with firmware.
- Next we concatenate verilog files and generate a firmware hex file.
- The 8 bit hex file is converted to a 32 bit hex file.
- A testbench is compiled and finally, executed.
- ![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/dd9361fc-1dbe-4f0d-85f0-cb16935cfbcb)

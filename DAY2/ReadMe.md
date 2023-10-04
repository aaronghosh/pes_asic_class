## RISC-V Instructions Overview

### R-Type Instructions
- `add`: Addition
- `sub`: Subtraction
- `and`: Bitwise AND
- `or`: Bitwise OR
- `xor`: Bitwise XOR
- `slt`: Set Less Than (signed)
- `sltu`: Set Less Than (unsigned)

### I-Type Instructions
- `addi`: Add Immediate
- `andi`: Bitwise AND with Immediate
- `ori`: Bitwise OR with Immediate
- `xori`: Bitwise XOR with Immediate
- `lw`: Load Word
- `sw`: Store Word
- `beq`: Branch if Equal
- `bne`: Branch if Not Equal

### S-Type Instructions
- `sb`: Store Byte
- `sh`: Store Halfword
- `sw`: Store Word

### U-Type Instructions
- `lui`: Load Upper Immediate
- `auipc`: Add Upper Immediate to PC

### J-Type Instructions
- `jal`: Jump and Link
- `jalr`: Jump and Link Register

### Floating-Point Instructions (F-Type and D-Type)
- `fadd.s`: Single-precision floating-point addition
- `fmul.d`: Double-precision floating-point multiplication
- `fcmp.s`: Single-precision floating-point comparison

### RV64 and RV32 Variants
RISC-V can be configured in different bit-widths, with RV64 (64-bit) and RV32 (32-bit) variants. Instructions for these variants have slightly different encodings.

### RISC-V Instruction Fields
RISC-V instructions share common fields with different purposes:
- **Opcode (OP):** Specifies the operation.
- **Destination Register (rd):** Specifies the destination register.
- **Source Register(s) (rs1, rs2):** Specifies source registers.
- **Immediate (imm):** Contains a constant value.
- **Function Code (funct3, funct7):** Further specify the operation.
- **Extension-specific Fields:** Depending on the extension (e.g., F for floating-point, M for integer multiplication/division), there may be additional fields.

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

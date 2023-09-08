# DAY 4: Timing Libraries and Efficient Flop Coding Styles

## Liberate File Explained

### `.lib` File Name: `sky130_fd_sc_hd__tt_025C_1v80.lib`

- `tt`: Typical PMOS typical NMOS (Regular working speed)
- `025C`: Temperature
- `1v80`: Supply voltage
- `sky130`: 130nm Technology node
- `fd`: Foundry design
- `sc`: Standard cell
- `hd`: High density (optimized for smaller chip area)

This `.lib` file contains essential information about standard cells, including leakage power, area, timing, and more. It covers various input combinations and loads, facilitating the synthesis process.

## Hierarchical Synthesis vs. Flat Synthesis

### Hierarchical Synthesis

- Maintains hierarchy: Submodules displayed as submodule blocks.
- Submodule logic is not visible when flattened.
- Useful for larger designs with clear functional divisions.
 
### Flat Synthesis

- Synthesizes the entire design as a single entity.
- Ignores functional separation.
- Suitable for smaller, highly interconnected designs or global optimizations.

## Synthesis Steps

### Hierarchical Synthesis

1. `read_liberty -lib <PATH_TO_.lib_FILE>/sky130_fd_sc_hd__tt_025C_1v80.lib`
2. `read_verilog multiple_modules.v`
3. `synth -top multiple_modules` (Use `synth -top <submodule_name>` for submodule level synthesis)
4. `abc -liberty <PATH_TO_.lib_FILE>/sky130_fd_sc_hd__tt_025C_1v80.lib`
5. `write_verilog -noattr multiple_modules_mapped_hier.v`
6. `show multiple_modules`
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/0dc677ee-b977-4d77-baa5-1c4e09b975f7)


### Flat Synthesis

1. Follow steps 1 and 2 from Hierarchical Synthesis.
2. `flatten`
3. `write_verilog -noattr multiple_modules_mapped_flat.v`
4. `show multiple_modules`
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/72b81d9f-7a5f-4b66-aa26-488d06cdc58a)

### Submodule Synthesis

1. Follow steps 1 and 2 from Hierarchical Synthesis.
2. Use `synth -top <submodule_name>`.
3. Continue with steps 4 to 6.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/6774b5d9-a128-4355-ba31-cf4d5a071eb3)

## Flop Coding Styles and Synthesis

- Flops are used to store values and eliminate glitches.
- Different flop styles include asynchronous reset, asynchronous set, synchronous reset, and both synchronous and asynchronous reset.

## Flop Synthesis and Simulation

 
Flip-flops, often referred to as flops.

Here are some usage of flip flops

Memory Elements:
Flip-flops provide memory elements that can store binary values (0 or 1) over time. This ability to retain information is fundamental to building sequential logic circuits like registers and memory.

Clock Synchronization:
Flip-flops are often triggered by clock signals, allowing them to synchronize with the clock's rising or falling edges. This synchronization is vital for managing the timing and sequencing of operations within a digital system.

Sequential Logic:
Digital systems often require the ability to respond to previous inputs or states. Flip-flops enable the creation of sequential logic circuits, where the current state depends on both the current inputs and the previous states.

State Machines:
Sequential circuits built using flip-flops can implement state machines, which are used to model systems that have different operational modes and respond differently based on their current state and inputs.

Counters and Registers:
Flip-flops are the building blocks of counters and registers. Counters are used for tasks like generating clock dividers, frequency dividers, and timing events. Registers are used for temporary data storage, data manipulation, and data transfer between different parts of a circuit.

# D-flip-flop with an asynchronous reset

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/99e00261-3b19-4208-8453-271b64836fd4)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/8da9d303-bc4f-4e6b-8f90-4a3d328226cb)

# D-flip-flop with synchronous  reset
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/cd0b5056-b2f5-455e-bdcc-9a535d70d894)

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/d2634fbf-3e65-4774-b666-cce16c2b6f52)

Optimizations include appending ground bits for multiplication, reducing resource usage, and complexity.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/81563226-7277-4609-9cfd-8538f49452a3)

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/662c70d4-17bf-4dd1-aca9-ac1df82a0063)

# Optimized Netlist
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/0de8de0a-abae-4eda-8fa6-4f3cfbf584ea)

---

**Note:** Replace `<PATH_TO_.lib_FILE>` with the actual `.lib` file path in synthesis commands.

For detailed examples and further information, explore the respective files and directories.


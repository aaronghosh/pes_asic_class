# Day 3: Introduction to Verilog RTL Design and Synthesis
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/aa501517-ca8c-43e6-bbb6-ca5adcd907f1)


## Yosys: Introduction and More

Yosys is a powerful open-source framework designed for Verilog RTL synthesis. It plays a crucial role in transforming higher-level hardware descriptions, such as those written in Verilog, into lower-level netlist representations, which are essential for subsequent stages in the RTL to netlist workflow.

### Understanding Key Terms

#### Netlist
A netlist is a structural representation of a digital circuit. It consists of interconnected gates, flip-flops, and other logic elements.

#### Synthesis
Synthesis is the process of transforming a high-level hardware description into a lower-level representation suitable for implementation in hardware.

#### RTL (Register Transfer Level)
RTL is a hardware description abstraction that captures digital circuit behavior through sequential logic elements and data transfers between registers.

#### Synthesizer
A synthesizer is the tool used for converting RTL into a netlist.

#### .lib
A .lib file is a collection of various logical modules.

### Lab Work for Day 3

1. Enable administrative mode using the command `sudo -i`.
2. Navigate to the `verilog_files` directory and invoke Yosys.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/d14f4c93-c748-46ab-ab18-6493285fa6c9)

3. Read the library using the command `read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib`.

4. Read the design using the command `read_verilog good_mux.v`.

5. Go to the synthesis step using the command `synth -top good_mux`.

6. After completing synthesis, generate the netlist using the ABC tool, which is present in Yosys itself, with the command `abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib`.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/b50f4ce5-e599-40bf-9afc-f488adacf430)

7. To view the logic-level design, use the command `show`.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/2054f5a7-3639-44e5-8734-eabf5d20b5ff)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/63b4c984-f7f6-4285-b2b6-8591b64d391f)


8. To see or change the netlist, use the command `write_verilog good_mux_netlist.v` and open it using `!gedit good_mux_netlist.v`.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/ab6071bb-6c16-4873-850e-b14b93f9245d)

9. To simplify the netlist, use the command `write_verilog -noattr good_mux_net.v`.
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/aae661b4-ef49-4f5c-96a3-50b014fe592b)

This completes the Day 3 lab work for Introduction to Verilog RTL Design and Synthesis.

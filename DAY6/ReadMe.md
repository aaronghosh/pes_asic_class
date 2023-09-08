## Gate Level Simulation(GLS)

- used for post-synthesis verification to ensure functionality and timing requirements
- input : testbench ,synthesized netlist of a deisgn, gate level verilog models (since design now is synthesised one , it has library gate definitions in it.so we have to pass those verilog models too)
- sometimes there is a mismatch in simulation results for post-synthesis netlist that's called synthesis simulation mismatch

### Synthesis Simulation Mismatch

Reasons : 
- **Missing Sensitivity list**
- **Blocking(sequential execution) vs Non Blocking assignments(parallel Execution)**
- **Non standard verilog codeing**

### GLS Lab

# ternary_operator_mux.v

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/80b830b5-786e-42d5-a68f-ad07ffe8be91)

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/a2724723-b524-420e-8a33-1273893ee06f)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/6943fb38-89b1-40ec-840e-5acdc00ebd03)

# bad_mux.v

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/138e05ef-a58b-45ab-8157-1c6040df2e40)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/ee385940-e170-4cf9-98fe-c4b2dc51b0c7)
## Gate Level Simulation
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/59202aba-d084-4d43-8b2e-1b222c2d7f64)

# blocking_caveat.v


![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/30f47eb6-7389-4a82-b7e4-67a47fc2d91e)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/7f0bd236-4a70-4bb7-b72a-160ce6faa0e3)
## Gate Level Simulation
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/61a57454-ad3c-4780-b240-4d36de9c3602)






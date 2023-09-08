# Logic Optimization

## Combinational Logic Optimization

### Constant Propagation
# Logic Optimization

## Combinational Logic Optimization

### Constant Propagation
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/3c7b2ba1-6cd1-4c33-a480-708fc04c9910)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/06f0b386-779b-4c8c-ba2a-e196d6057f7c)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/7fd87f2f-b452-4ced-a3ce-00519e66b216)

### Boolean Logic Optimization
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/92846045-606d-4780-aade-3d89ea8151b1)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/6b18cdfc-6a38-43b7-85fe-18f9ae144458)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/727ddc83-56cf-4c7d-9692-a6a3dc8fa4b6)

### Sequential Logic Optimization

#### Sequential Constant Propagation
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/084ec010-196b-4930-92da-7f26e19b4a11)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/ca6f0155-503f-4552-b4d6-fdadf3ef9845)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/3cc3e426-11f0-4f47-9497-50039084d1e4)

#### State Optimization
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/23d16397-044d-4cfa-899c-922f760f58a4)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/1443fd8f-870e-42eb-9150-85281e814ec6)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/7fd9f660-ebfb-4c29-b548-13e4f061370f)

#### Sequential Logic Cloning
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/ac1252da-ed84-4d2f-9591-2e8655637afc)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/02735c24-8ef0-45ba-ab83-8f660b7cf6f2)

To perform the combinational logic optimization, use the command `opt_clean -purge` before linking to abc and synthesize.

Here we can observe that instead of using `and` gate and `or` gates, it's using `AOI`.

## Sequential Logic Optimization

### dff_const1.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/1f7f709c-fe3e-4bdd-9baf-a82883f46194)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/98ec09ac-ead3-4f87-bd51-50b2f6cbe23c)


### dff_const2.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/32eed02c-2909-4da7-bbdb-74d2d6390caf)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/31dce4fe-a9a7-490b-93f8-3b9682eef40f)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/b6ba3b4c-5519-409b-93a3-77999b9215dd)


### dff_const3.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/5c273d42-0235-4f4a-bf54-ec992fab60fb)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/3e33f815-66c6-4f68-9f12-d46761b89c97)


### dff_const4.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/08bea055-8aba-48d2-8d23-4ccdcba396d6)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/dc2ed355-760c-446d-aa64-afe3c6ad90ec)


### dff_const5.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/9e5d450a-a908-4266-b3ef-37acf4dddda2)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/4b2fc9f7-392a-41c8-84ad-8ccf14cb378e)

### counter_opt.v
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/672f79dd-31b6-47f4-b948-c93bdd860b21)

Usually, a 3-bit counter requires 3 flops, but since the output here is dependent on only the LSB and the other 2 bits are unused, only one flop is being used. As we know that the LSB toggles every clock cycle, it's just using an inverter to invert the output at every clock cycle.


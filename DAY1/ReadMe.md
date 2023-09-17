# Day 1
## Sum 1 to n program
Open your terminal and run the following command to create a  ```.c```  file. 

```shell 
vim lab1/sum1ton.c 
```
This code sums numbers from 1 to n
 ![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/9f4639f9-04ef-4e8b-80a3-b24996bc170c)

- To run the above code use :

```bash 
gcc lab1/sum1ton.c
```

This runs it using gcc, on our machine.

```shell
cat lab1/sum1ton.c
```

Gives the output ```Sum from 1 to 50 = 1275```

### C to Disassembly 

- To generate a RISC-V object file we need to use the  ```riscv64-unknown-elf-gcc``` command

```bash

>lp64 - l (long integer) p(pointer) 
>march -  risc v 64 bit arch

- To view the assembly code:

```bash
riscv64-unknown-elf-objdump -d  sum1ton.o 
```
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/58d7c9fd-913b-4f4a-a431-11865771612a)


    Repeating the above but with ofast :

riscv64-unknown-elf-gcc -0fast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/4a562ed5-5208-4bbc-9632-5ac271c2c7fd)
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/96043cc0-5ae3-4774-96e2-f8c861937288)


## Signed and Unsigned Integers

Put this code in a c file unsignedHighest.c to calculate the largest int.
```c
#include <stdio.h>
#include <math.h>

int main(){
	unsigned long long int max = (unsigned long long int) (pow(2,64) -1);
	printf("Largest unsigned long long int = %llu/n", max);
	return 0;
}
```
Compile the code and view output using:
```bash
riscv64-unknown-elf-gcc -0fast -mabi=lp64 -march=rv64i -o unsignedHighest.o unsignedHighest.c

spike pk -d unsignedHighest.o
```
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/9288dddc-ad4b-4ac4-b798-6edb3bcaee1f)





riscv64-unknown-elf-gcc -01 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
ls -ltr sum1ton.o
```

>o1 - Level 1 optimization
>lp64 - l (long integer) p(pointer) 
>march -  

# Day 1
## Sum 1 to n program
Open your terminal and run the following command to create a  ```.c```  file. 

```shell 
gedit lab1/sum1ton.c 
```
This code sums numbers from 1 to n
 ![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/9f4639f9-04ef-4e8b-80a3-b24996bc170c)

- To run the above code use :

```bash 
gcc lab1/sum1ton.c
```

running it using gcc

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
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/581f6fc7-d2cd-4980-8379-259d03c73d97)

riscv64-unknown-elf-gcc -0fast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
Now check the output using spike
![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/25badfaf-5ac5-4e8a-afb6-6224d09a656d)

## Signed and Unsigned Integers
create a new C file
```c
#include <stdio.h>
#include <math.h>

int main(){
	unsigned long long int max = (unsigned long long int) (pow(2,64) -1);
	printf("Largest unsigned long long int = %llu/n", max);
	return 0;
}
```
Compile the code and view output 
```bash
riscv64-unknown-elf-gcc -0fast -mabi=lp64 -march=rv64i -o unsignedHighest.o unsignedHighest.c

spike pk -d unsignedHighest.o
```


![image](https://github.com/aaronghosh/pes_asic_class/assets/124378527/4eed4226-a2a8-4a8c-9b12-d3096ab06189)


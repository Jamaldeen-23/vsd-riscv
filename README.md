# vsd-riscv
## the below screenshots are from the RISC V MYTYH workshop

## TASK 1

We will try to see the assemble code of the C program that we wrote. When we type this command, it will give a bunch of assembly codes.

![Screenshot from 2025-03-06 20-36-29](https://github.com/user-attachments/assets/5657c89d-807e-461d-b519-7ad81ddd16bb)


So, we will change the code to show less

There are many things shown. But, we are interested in the 'main' section, so type '/main' and click 'n'. Here, the address of the 'main' is 10184(in video) and there are 15 instructions inside the 'main' when we use the option '-o1' in the command. If we wish to count the instructions without counting one by one, subtract 101c0 and 10184 and divide the resultant by 4. Because, If we look into the instructions, it increment by 4.

![Screenshot from 2025-03-08 16-29-42](https://github.com/user-attachments/assets/b245f0ac-8599-4024-8f48-4297a362a5f0)

Now we are running the same command by replacing '-o1' by '-ofast'. Now the number of instructions will be higher or lesser.



We use './a.out' to get the output in 'c'. Now we will see what command to use to get the output in riscv. The command is 'spike pk sum1ton.o'. Now let us debug it using the command 'spike -d pk sum1ton.o'.   
pc->program counter  
We want our program to run till above the main and after that we will debug manually. To run till above the main we use the command 'until pc 0 address_of_main'. In this case(in video) it is, 'until pc 0 100b0'.  To find the contents of 'a2', we use the command 'reg 0 a2'. If we press enter, next instruction will run. And again if we run 'reg 0 a2', it gets modified. 'lui' means load upper intermediate which means, the data present in the right side of the instruction is loaded to the left side register from 12 to 31 bits.

![Screenshot from 2025-03-08 16-33-00](https://github.com/user-attachments/assets/703458e6-484d-41bc-9a2e-22e00fa24a26)


![image](https://github.com/user-attachments/assets/dd5c650a-7f45-4cdc-a996-b9c304bbaf08)

Here we are interested to know what is the value of 'sp' before running that instruction. So we quit it run from the beginning.


When we do that, 10 is subtracted from the value as shown below.

![Screenshot from 2025-03-08 17-26-49](https://github.com/user-attachments/assets/cf66daec-e7e5-46dd-bc6b-e204e4bc9cc6)

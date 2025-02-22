# NASSCOM-RISC-V-based-MYTH-program
RV Day 1 - Introduction to RISC-V ISA and GNU compiler toolchain  
RV-D1SK1 - Introduction to RISC-V basic keywords  
RV_D1SK1_L1_Introduction  

In the right side we have the layout of the entire chip present in our laptop. In the left side, we have a 'C' code. To pass this code to the layout, there are certain flows. The C code is first converted into assembly language(riscv here), then it is converted to binary language. And this will sent to the layout and we get the required output. There is another interface that should be present in between the riscv architecture and the layout is HDL.

![image](https://github.com/user-attachments/assets/41f357e0-1ef4-4179-a2b8-b4872ea530e4)

RV_D1SK1_L2_From Apps To Hardware

RV_D1SK1_L3_Detailed Description Of Course Content

This is the simple C program performing addition, multiplication and division.

![image](https://github.com/user-attachments/assets/b0db44d9-6d11-4d82-b3bd-d7221dca6506)

when it enters into the compiler, the instruction set will be looking like,

![image](https://github.com/user-attachments/assets/d90b4493-3c36-4038-9b27-c88200cd730a)

The instructions other than pseudo instructions will act on integer numbers.

![image](https://github.com/user-attachments/assets/6cc43153-e978-4d56-ad20-61102b923444)

If any CPU core has both the integer instructions and multiply extension, they are called as 'RV64IM' cpu core.

![image](https://github.com/user-attachments/assets/f190a6bb-42e4-4773-af56-b16bc77a75e3)

This is the simple C program performing floating point addition, multiplication and division.

![image](https://github.com/user-attachments/assets/2f3312d8-18eb-4b74-87ed-8bda0f0b7b80)

This is the instruction set of the above code. F-> single precision, D->Double precision.

![image](https://github.com/user-attachments/assets/684d777f-039e-47fb-ad5f-da850ff9a823)

If a cpu core executes integer, multiplication and floating operations, it is called as 'RV63IMFD' cpu core.

![image](https://github.com/user-attachments/assets/ae9dfa45-9964-4532-9f08-6b7fbb035e64)

In the below codes, some data transfer happening between the memory and the stack pointer.

![image](https://github.com/user-attachments/assets/2ff36c7b-1b18-4aaf-974b-255d793c673e)

Also we will be looking into 64 bit representation of the signed and unsigned integer and lets start with this. 

RV-D1SK2 - Labwork for RISC-V software toolchain  
RV_D1SK2_L1_C Program To Compute Sum From 1 to N  

![image](https://github.com/user-attachments/assets/29ca2079-d98f-448f-978e-0da78f3adfdd)

RV_D1SK2_L2_RISCV GCC compile And Disassemble

We will try to see the assemble code of the C program that we wrote. When we type this command, it will give a bunch of assembly codes.

![image](https://github.com/user-attachments/assets/e329df34-09c3-4b0d-83e3-e3a7ba58bb06)

So, we will change the code to show less

![image](https://github.com/user-attachments/assets/28a14faf-032a-492a-973d-bee81cf51084)

![image](https://github.com/user-attachments/assets/dd530696-8be5-46ce-b30e-35e5ad1db2a8)

There are many things shown. But, we are interested in the 'main' section, so type '/main' and click 'n'. Here, the address of the 'main' is 10184(in video) and there are 15 instructions inside the 'main' when we use the option '-o1' in the command. If we wish to count the instructions without counting one by one, subtract 101c0 and 10184 and divide the resultant by 4. Because, If we look into the instructions, it increment by 4.

![image](https://github.com/user-attachments/assets/6f43dcf5-2c03-4903-a0c5-5eedee9f19fa)

Now we are running the same command by replacing '-o1' by '-ofast'. Now the number of instructions will be higher or lesser.

RV_D1SK2_L3_Spike Simulation And Debug

We use './a.out' to get the output in 'c'. Now we will see what command to use to get the output in riscv. The command is 'spike pk sum1ton.o'. Now let us debug it using the command 'spike -d pk sum1ton.o'.   
pc->program counter  
We want our program to run till above the main and after that we will debug manually. To run till above the main we use the command 'until pc 0 address_of_main'. In this case(in video) it is, 'until pc 0 100b0'.  To find the contents of 'a2', we use the command 'reg 0 a2'. If we press enter, next instruction will run. And again if we run 'reg 0 a2', it gets modified. 'lui' means load upper intermediate which means, the data present in the right side of the instruction is loaded to the left side register from 12 to 31 bits.

![image](https://github.com/user-attachments/assets/dd47723d-9bd3-4cad-828d-5c64144aa7c0)

![image](https://github.com/user-attachments/assets/dd5c650a-7f45-4cdc-a996-b9c304bbaf08)

Here we are interested to know what is the value of 'sp' before running that instruction. So we quit it run from the beginning.

![image](https://github.com/user-attachments/assets/04b3d308-cc9b-4133-9d6e-e3ffb4edca13)

When we do that, 10 is subtracted from the value as shown below.

![image](https://github.com/user-attachments/assets/d3304945-53f6-4cdf-8a47-6403cc83f5ae)

What does 'addi' will do?. it will add the source register and 'imm' and store it in the destination register.

![image](https://github.com/user-attachments/assets/6ac0a0e3-e2af-4341-8be1-3d59ac38dd98)

My work
![image](https://github.com/user-attachments/assets/ef5783f0-6ef2-4415-9fa1-ae767c4fe23c)

RV-D1SK3 - Integer number representation  
RV_D1SK3_L1_64-bit Number System For Unsigned Numbers  

![image](https://github.com/user-attachments/assets/5ace8c4f-987b-41b7-9992-2e8ff73cad9e)

4 bytes forms a word. 8 bytes(2 words) forms a double word. 32-bit data is a word, 64-bit data is a double word. These are about the unsigned positive numbers.

![image](https://github.com/user-attachments/assets/fb60d272-76db-439e-a029-df08b7e76e8f)

![image](https://github.com/user-attachments/assets/28b268f3-f6de-4183-b861-d60a5452de41)

![image](https://github.com/user-attachments/assets/e5cc2c21-0a2e-4a12-aa7a-77b2b78242d9)

![image](https://github.com/user-attachments/assets/3a16e415-e844-44c7-a870-fbc974d92d5c)

![image](https://github.com/user-attachments/assets/3b4052ca-b736-4038-a4de-80eb3c2cd704)

RV_D1SK3_L2_64-bit Number System For Signed Numbers

![image](https://github.com/user-attachments/assets/6f54cfb2-2ce0-49e2-ac0d-9974e801b862)

![image](https://github.com/user-attachments/assets/67771e46-f575-46b0-811a-04aa318cf176)

![image](https://github.com/user-attachments/assets/52065919-48d4-4843-b004-30a76ee1351c)

From this we observe that, the MSBs which have 0s are positive numbers and which have 1s are negative numbers. If we have 1 at the MSB, again we can do the inverse and add 1 to get the original number. These are called signed numbers.

![image](https://github.com/user-attachments/assets/17d0defc-fce1-4ca7-909b-bb12f19c1b6a)

![image](https://github.com/user-attachments/assets/2b5307d0-0e23-4880-92e8-86e6b9320ded)

Now let us see the range of positive and negative that can be represented using rv64 hardware. The number of positive numbers that can be represented is,

![image](https://github.com/user-attachments/assets/ed17cc57-b35a-4ef3-a100-cc7d55417b1d)

![image](https://github.com/user-attachments/assets/808bda60-1f1a-4cfc-afa2-ed10606ffb1f)

These are the important notes with respect to the integers.

![image](https://github.com/user-attachments/assets/eadd3e93-e53f-4687-b672-c22bf569c399)

Instructions which operate on these kind of numbers are called Base integer instructions.

![image](https://github.com/user-attachments/assets/64cc35e5-8c58-410f-ad5c-23c3bf14bc99)

RV_D1SK3_L3_Lab For Signed And Unsigned Numbers

![image](https://github.com/user-attachments/assets/bf80b185-55d7-4f04-b28c-91120924278b)

My works
![image](https://github.com/user-attachments/assets/dd3744b3-cabf-4021-b01f-e4bf43ec3523)

![image](https://github.com/user-attachments/assets/efb65317-8c10-4031-9c43-8deb9c3c6404)

![image](https://github.com/user-attachments/assets/8c215125-f33c-46c2-b360-ea4de0ba8892)

![image](https://github.com/user-attachments/assets/e2b95c7d-d0e5-4ee8-a2eb-e40e41b052cb)

![image](https://github.com/user-attachments/assets/cd5f8eca-862d-4e90-9bec-6aeb06ffe873)

![image](https://github.com/user-attachments/assets/c093310f-f7de-4c91-8629-091a691ee8c5)

RV Day 2 - Introduction to ABI and basic verification flow  
RV-D2SK1 - Application Binary interface (ABI)  
RV_D2SK1_L1_Introduction To Application Binary Interface  

![image](https://github.com/user-attachments/assets/0505fcd3-6d1d-4e58-a478-01941ea9a6de)

![image](https://github.com/user-attachments/assets/60a853d1-da9a-4a8e-94df-49d38c153859)

If we want to present this architecture of the building to the user, the interface is appearance. Right now, the details such as plumbing are not required for the users. 

![image](https://github.com/user-attachments/assets/11e41e1c-4b46-447e-aab2-43255dd13c7b)

Similarly, in case of the computer, the interface is apperance and functionality. The details such as processors and other things are not highly required at the very beginning.

![image](https://github.com/user-attachments/assets/4598561d-7ebc-4400-a446-4ed907034e6c)

Similarly, If we want the email application program to run on the hardware, there are multiple layers inbetween and one of them is ABI. Java or C or other languages are used to build this application program. In the process of reaching the hardware, the applcation program will access the operation system through the standard libraries. The interface between the OS and the machine language is ISA(can be riscv or any other thing). This particular ISA is accessible to the operating system and to the user directly and they are called user and system ISA and user ISA. In this case the user is the Application programmer(the person who program email).  
There is also a way for the application program to access some of the hardware resources of the this OS directly, and the way it does is through the system call, which means the application programmer can directly access the registers of the riscv architecture via system calls. This interface is called ABI(also called system call interface).

![image](https://github.com/user-attachments/assets/3521f32c-d22a-456d-aea7-506d6a4eb292)

 The application programmer can access the hardware resources via registers.

 ![image](https://github.com/user-attachments/assets/c7cccb2d-9c65-40d7-a92c-b3f06347a8cb)

In riscv we have 32 registers and the width of the register is defined by a keyword called XLEN-1. Now we will get questions like, Why we need 32 registers and why 64 bits?

![image](https://github.com/user-attachments/assets/6f913e56-8f73-438f-b328-28c3fd3cafc4)

RV_D2SK1_L2_Memory Allocation For Double Words

Why there is only 32 registers?.  Now let us consider the 64 bit registers. There are 2 ways to load this 64 bit data to the registers. One is, directly we can load the data into the register. Else we can load the data in the memory and from the memory we can load it into the register.   
Let us see how to load this data to the memory and it is shown below. First byte from the LSB is stored in the below register and the other bytes follows it. This structure of the memory system is called as 'little-endian' memory addressing system and RISCV belongs to this category. There is also another memory addressing system called 'big-endian', where the Most significant Byte will be stored in the below register and the other bytes follow it. 'little-endian' memory addressing system is the reverse of 'big-endian'.

![image](https://github.com/user-attachments/assets/04845b6b-7538-4535-b9ae-9ca3d4a119e8)

The address of the below shown entire double word is m[0], the address of next double word that we load will be m[8] and so on. So, it is a multiple of 8.

![image](https://github.com/user-attachments/assets/9c65f168-97b6-42c6-823f-3104218906db)

Lets see an example of an array which holds 3 double word. And the 3rd double word is shown below, which has the LSB at m[16] and MSB at m[23]. In this case, how will we load the double word in the register?. For that, we need some basic ISA commands and will look into it.

![image](https://github.com/user-attachments/assets/0613fc61-bcb6-455f-8eff-6db9132e3f41)

RV_D2SK1_L3_Load, Add And Store Instructions With Example

Our objective is to store the below mentioned data in any one of the registers, lets take x8. If we want to access this data from the memory, we need the first address of that particular memory. So, we store the base address of this entire memory in one register(x23). Lets keep it simple by having the base address as 0. '16(x23)' means, 16 will loaded into the contents of x23 register, which means, the base address 0 is replaced by 16. 'ld' means load double word. This is how the 64-bit data will be loaded into the x8 register. 

![image](https://github.com/user-attachments/assets/261485a6-3000-432d-940a-db94ab5a08c9)

Now let us see how this command is represented inside the computer. All the instructions in the riscv are 32 bit though it is 64 bit for the registers. The bits 0 to 6 and 12 to 14 forms the opcode of the 'ld'. Opcode is a code which instructs the computer to use 'ld'. Bits 15 to 19 are used to represent the rs1. Based on the combination of 5 bits we will get the value 23(in this case). Bits 7 to 11 is used to represent rd which is 8(01000) in this case. 16 will be loaded to the bits 20 to 31.

![image](https://github.com/user-attachments/assets/6310597b-ca7e-4a05-b63e-1856f7ee8712)

Lets see another command. If we want to add the double word with the contents of x24, we need to use 'add' command.

![image](https://github.com/user-attachments/assets/8a34bf54-5881-49b5-94df-34ee21418f92)

The way we instruct the computer to execute this command is shown below. Here, opcode, funct3 and funct7 are used to form the opcode of 'add' instruction.

![image](https://github.com/user-attachments/assets/a6ad0881-9966-4c22-a45d-5689225f7f9e)

Now lets see the another command to store the data from the register to the memory and it can be done using 'sd' store doubleword command. Here, the memory locations 16 to 23 are already occupied, so lets see the free locations and store data. Since we have only 32 registers, we have to load and store the data to the memory, because memory is the place where we have space to store. 'data register rs2' is the register which stores data.

![image](https://github.com/user-attachments/assets/994c7955-6dd9-4913-9fd4-ffff60dafb2a)

Here the opcode and func3 are used to execute the 'sd'command. the offset'imm' will be split and stored in immediate[11:5] and immediate[5:0].

![image](https://github.com/user-attachments/assets/d0ab665e-67d2-49cf-959c-47eda1cf46bf)

RV_D2SK1_L4_Concluding 32-registers And Their Respective ABI Names

All the instructions that we saw will operate on integers(signed or unsigned). These instructions are called base integer instructions. Any cpu that use this 47(total) base integer instructions are called RV64I. There are multiple classifications inside the base integer instructions. The instructions which act only on registers are called R-type instructions Eg: 'add'.

![image](https://github.com/user-attachments/assets/2250f20c-c0db-4a5c-9ed7-958354e01c40)

The instructions which operate on registers and an immediate are called I-type registers Eg: 'ld'.

![image](https://github.com/user-attachments/assets/d33a3608-bf79-4d8e-9b08-34932c19a111)

The insturctions which operate on source register and immediate are called S-type registers and are used for store purpose Eg: 'sd'

![image](https://github.com/user-attachments/assets/b66b4328-155d-4584-b646-3932359d9423)

If we look into all the cases, we represent the registers using 5 bits. So, maximum we can have **2^5=32 registers**.

![image](https://github.com/user-attachments/assets/2a09c1c8-a31c-4937-9d6f-a62bf3252c11)

For each registers, an ABI name will be given through which the ABI will access the internal registers of the riscv cpu core using some system call functions.

![image](https://github.com/user-attachments/assets/4e791a2e-efad-4fdb-b13a-fca2508f1b6d)

![image](https://github.com/user-attachments/assets/7ddebe59-1895-429a-a9f0-fc8352525994)


RV-D2SK2 - Lab work using ABI function calls  
RV_D2SK2_L1_Study New Algorithm For Sum 1 to N Using ASM  

Now, using the C program we are going to make some function calls to the assembly language program in the riscv and do some computations and send the final result to the C program. The arguments will be passed to ASM using the a0 and a1 registers and returned to C program using a0 register.

![image](https://github.com/user-attachments/assets/8f96e466-53b8-4b6b-8b6a-0d1a0a391b8d)

We can use any register between a0 and a7. We initialize the registers a4 and a3 to 0. We store the count 10, which came from a1, to the register a2.

![image](https://github.com/user-attachments/assets/c951d918-dc87-4a0d-9fc6-7e67119ee350)

RV_D2SK2_L2_Review ASM Function Call

Now we have to write 2 codes, one in C(.c) and its ASM(.S).

![image](https://github.com/user-attachments/assets/2084c9ea-d621-4a2d-a865-b8b50180b5f6)

![image](https://github.com/user-attachments/assets/0d59362f-5747-4b89-a9cb-5881f61e475c)

![image](https://github.com/user-attachments/assets/5a70eed0-6ee8-4786-8931-8dbff60e4387)

RV_D2SK2_L3_Simulate New C Program With Function Call

![image](https://github.com/user-attachments/assets/f23430fa-9a3c-476d-96a9-ba79777d71a3)

RV-D2SK3 - Basic verification flow using iverilog  
RV_D2SK3_L1_Lab To Run C-Program On RISC-V CPU  

Till we did the simulation. Next we will see how to run the same c program on a riscv cpu. We load the hex file of the c program to memory. We read the memory through the riscv cpu. The cpu will process the hex file and give the desired output.

![image](https://github.com/user-attachments/assets/eaef3b28-96e3-4459-b1bb-a74c4754fcc4)

The below shown is the riscv cpu that was written in verilog and testbench is also available which is shown below. Here is shown the way to read the hex file into the memory.

![image](https://github.com/user-attachments/assets/6045c197-b9d9-4c99-bae2-5531ab5f8a37)

Now let us see the standard scripts on how to create the hex files. It can found using the command 'rv32im.sh'. Here the scripts to convert to hex files, load it to the memory of the riscv, those steps are given. Finally we will get the hex files. Then we use a tool called iverilog and it will take the picorv32.v and testbench.v as the inputs and testbench.vvp file as the output.

![image](https://github.com/user-attachments/assets/4ce0947b-93fa-4edb-b3db-deca37b9aeef)

Then we run run the entire script using the command shown below and generate the hex file.

![image](https://github.com/user-attachments/assets/9ee08d58-c7bc-432f-9fef-5ce583701655)

Here is the hex file which is machine understandable.

![image](https://github.com/user-attachments/assets/561e7d53-4b97-4bd4-96c4-8ab896ed26bd)

This bitstream is loaded into the firmware.hex and firmware32.hex

![image](https://github.com/user-attachments/assets/121e6320-c0e3-40c0-ad3a-2df97ea4e90b)

![image](https://github.com/user-attachments/assets/075ec7b6-0c6f-4833-b605-6e7993a5d158)

It is loaded into the memory through the testbench.v.

![image](https://github.com/user-attachments/assets/cf9ae97e-e365-4e06-a069-cac0542e7809)

Finally we get the expected output which is highlighted below.

![image](https://github.com/user-attachments/assets/93af5da4-7c12-4a70-b2f4-1ef5be7c34a1)

![image](https://github.com/user-attachments/assets/a2113735-6c17-44e5-bdd8-45dd8c169e69)

My works
![image](https://github.com/user-attachments/assets/17b80e30-4422-45b0-8b36-54ea89a2ddf2)

picorv32.v
![image](https://github.com/user-attachments/assets/6d19107e-6cbf-4940-834b-0789285be78f)

testbench.v
![image](https://github.com/user-attachments/assets/13c26c7e-a102-4fe2-b171-952cbeda7e88)

rv32im.sh
![image](https://github.com/user-attachments/assets/db951af5-0818-4f9e-be3f-5d6eb45a95b7)

![image](https://github.com/user-attachments/assets/2eefbbbe-9f14-4b32-ac22-71a5c470898b)

firmware.hex
![image](https://github.com/user-attachments/assets/42cbe7a5-2a3e-439d-8a26-f19f834a3a0d)

firmware32.hex
![image](https://github.com/user-attachments/assets/c3dee93c-2875-47bb-a297-6aea6c05b7a1)

RV Day 3 - Digital Logic with TL-Verilog and Makerchip  
RV-D3SK1 - Combinational logic in TL-Verilog using Makerchip  
RV_D3SK1_L0_Welcome  

![image](https://github.com/user-attachments/assets/583b8fd0-9945-45c7-b707-dee639fcf39f)

TL(Transaction level) verilog is a language extension to verilog.

![image](https://github.com/user-attachments/assets/5cfc4d2f-603c-4fad-b945-9f0832a01e89)

![image](https://github.com/user-attachments/assets/2977b581-06b5-4a54-a7a3-389371b0bc12)

![image](https://github.com/user-attachments/assets/528757f0-c41e-40f2-8a45-a5100fe0ae6c)


RV_D3SK1_L1_Introduction To Logic Gates  

![image](https://github.com/user-attachments/assets/db579e31-5b7b-4336-999b-13fd8ad011e0)

![image](https://github.com/user-attachments/assets/93cbfaa3-1e0d-464a-a264-b5df26446b63)

![image](https://github.com/user-attachments/assets/f0b11fc9-6d40-4bbe-9cb8-6e0b7e4024c0)

![image](https://github.com/user-attachments/assets/ed53b95f-64bb-47c2-89da-b80d4bd9eb07)

These are the different notations for the gates and we will be focusing on the verilog notation.

![image](https://github.com/user-attachments/assets/1d5995f0-8910-42da-834c-01474d68582f)

RV_D3SK1_L2_Basic Mux Implementation And Introduction To Makerchip

The below shown is the ternary operator.

![image](https://github.com/user-attachments/assets/228ccea5-125c-48f2-9f66-674ace1ba51b)

![image](https://github.com/user-attachments/assets/8cc9c257-7929-4fdf-8a37-093b715faeb2)

RV_D3SK1_L3_Labs For Combinational Logic

![image](https://github.com/user-attachments/assets/4335a59c-e991-4baa-8bfe-0a7a3448547d)

My screenshot
![image](https://github.com/user-attachments/assets/677e5b2e-4310-4d13-b51e-ea0d07ae8c8d)

![image](https://github.com/user-attachments/assets/050dc6df-9e83-4764-80bc-9600b7563738)

Inverter 
![image](https://github.com/user-attachments/assets/4bb1ab04-1940-496d-ac23-d257b06d8923)

2-input AND gate
![image](https://github.com/user-attachments/assets/13408781-07be-43fc-b009-e0fd37f62947)

![image](https://github.com/user-attachments/assets/65a2fa62-4825-4c20-bd83-a54f78928237)

2 to 1 mux
![image](https://github.com/user-attachments/assets/62741aa8-8eda-4b7a-9995-3e24fda6f990)

![image](https://github.com/user-attachments/assets/86038b54-13fd-4621-b8e8-75d559ee36cc)

My work
![image](https://github.com/user-attachments/assets/689955ea-00bb-45b3-9037-29e1fd513c0b)

RV-D3SK2 - Sequential logic  
RV_D3SK2_L1_Introduction To Sequential Logic And Counter Lab  

![image](https://github.com/user-attachments/assets/aceefa97-96e1-4cd2-89ec-9e5471c63cac)

![image](https://github.com/user-attachments/assets/10c53800-8e8f-4c01-83fa-74451c971a81)

![image](https://github.com/user-attachments/assets/da79e022-277a-404c-94dc-367e6da8795e)

![image](https://github.com/user-attachments/assets/a538cb3a-db27-446e-bd3e-2fc0cba0a8a1)

My fibnacci series
![image](https://github.com/user-attachments/assets/defb5df2-0dba-4bf8-86d6-bb3fde258efe)

RV_D3SK2_L2_Sequential Calculator Lab

![image](https://github.com/user-attachments/assets/6be9c0fc-cd7c-444e-9c38-3267a25cd1c0)

![image](https://github.com/user-attachments/assets/926245cb-3950-4a7e-b3c2-4e1397fa3fa2)

RV-D3SK3 - Pipelined logic
RV_D3SK3_L1_Pipelined Logic And Re-Timing

![image](https://github.com/user-attachments/assets/944e010a-2443-48b7-b0ff-b57d90607685)

![image](https://github.com/user-attachments/assets/8b141a0a-5ee0-47d4-8c29-96ad3951fb38)

![image](https://github.com/user-attachments/assets/8427d262-62ef-48d4-9893-0441bca30f4f)

The same code is given in both system verilog and TL verilog. We can observe the code reduction here.

![image](https://github.com/user-attachments/assets/b3e5d2b9-479b-4978-8c66-27856bfb8a26)

Suppose we have to send the signals from one end of the die to other end, we can use pipelines like this. Here we have done Retiming and it looks pretty simple.

![image](https://github.com/user-attachments/assets/6e044f79-47b0-4895-af5c-dd871cdc4c8e)

Below code is shown for retiming in SV which seems complex than TL.

![image](https://github.com/user-attachments/assets/582a01ee-fd0d-43a4-897d-ee2486290f2e)

My work
![image](https://github.com/user-attachments/assets/a4a4c8d5-5f2b-4cb8-b668-6112ac0e18eb)
![image](https://github.com/user-attachments/assets/31723a5f-25c0-41ac-9520-f15135f1a6ab)

RV_D3SK3_L2_Pipeline Logic Advantages And Demo In Platform

By using pipelining, we can use the high frequency clock.

![image](https://github.com/user-attachments/assets/cde5a8b4-fed8-4001-be3a-41f1d0839008)

If we look into the unpiplined form, we take the example, for aa the value is 9 and for bb, the value is c and for cc, the value if 0f, which are in hexadecimal form and obtained at the same clock pulse.

![image](https://github.com/user-attachments/assets/04ab811d-b37b-4b7a-bb5b-634794a5528c)

Now let us see the pipelined version, here, at the same clock pulse, aa is 9 and bb is c. But the output cc=0f is assigned after 2 clock pulses.

![image](https://github.com/user-attachments/assets/d2fc0adc-426f-4bac-a51d-d3066d6c4ad7)

RV_D3SK3_L3_Lab On Error Conditions Within Computation Pipeline

![image](https://github.com/user-attachments/assets/43371772-5f8b-4505-b021-b3503dde213b)

![image](https://github.com/user-attachments/assets/578f1103-1a01-401e-9853-bb8b622e3361)

![image](https://github.com/user-attachments/assets/36d913b5-2a2b-4bd9-982c-ed52bc0b6f2e)

My work
![image](https://github.com/user-attachments/assets/ea70fb0c-b13d-4c76-8ff7-80ed1103c97f)

RV_D3SK3_L4_Lab On 2-Cycle Calculator

![image](https://github.com/user-attachments/assets/1d2a08a0-d402-4b19-b7bd-dfe39ffcd385)

![image](https://github.com/user-attachments/assets/9ecb2d23-95fd-49f7-9c4e-5bce03fa8362)

My work
![image](https://github.com/user-attachments/assets/67dd85ef-dbe6-4a14-869f-58872488f9c8)

RV-D3SK4 - Validity  
RV_D3SK4_L1_Introduction To Validity And Its Advantages  

Validity concept is not exist in RTL languages. Here, '?' means 'when', so '?$valid' means, when valid.

![image](https://github.com/user-attachments/assets/c7457a78-e3fd-4c13-a500-2fc7e2378c60)

![image](https://github.com/user-attachments/assets/0b5f9ca9-68e0-4d59-8a65-005de93bdf6b)

RV_D3SK4_L2_Lab On Validity And Valid When Condition

When the new distance is not valid, the previous distance will be holded. When the new distance is valid, it will get added to the existing distance.

![image](https://github.com/user-attachments/assets/7b65ac51-0568-4577-8abf-dac17d6d7d90)

![image](https://github.com/user-attachments/assets/2150fffc-f47c-4ab1-aea2-bd6b2a04ab59)

RV_D3SK4_L3_Lab To Compute Total Distance

![image](https://github.com/user-attachments/assets/210ab804-b546-45e6-ae55-340e47bfe037)

![image](https://github.com/user-attachments/assets/5a49158a-8ce2-4061-9b8f-a6ea04b2b4a4)

RV_D3SK4_L4_Lab on 2-cycle Calculator with Validity

![image](https://github.com/user-attachments/assets/66d18b60-cb00-4d63-a938-6b52c388cdc0)

My work
![image](https://github.com/user-attachments/assets/a5dfbf71-c5f9-4c3d-bc53-f427365b339a)

RV_D3SK4_L5_Calulator Single Value Memory Lab

![image](https://github.com/user-attachments/assets/66005591-b4cd-44bd-8a37-387e2384b409)

RV Day 3 Wrap-up  
(Bonus) RV_D3SK5_L1_Introduction To Hierarchy Concept  

![image](https://github.com/user-attachments/assets/e238322d-12b5-40a2-bd40-107bdacd9227)

![image](https://github.com/user-attachments/assets/fb901476-6e7e-45dd-b7f7-ee37e4d8ec08)

![image](https://github.com/user-attachments/assets/3c632bf1-7c92-428c-9960-592be1e4f627)

RV Day 4 - Basic RISC-V CPU micro-architecture  
RV-D4SK1 - Introduction to Simple RISC-V Micro-architecture  
RV_D4SK1_L1_Micro-architecture of Single Cycle RISC-V CPU  

The below shown is the micro architecture for the riscv implementation. The program counter is our pointer and it is pointed into the instruction memory into the instruction that we going to execute. The output of the instruction memory is the instruction. First we decode the instruction using decoder for finding what that instruction does. The adder present here compute the next pc. The addes uses the incremented pc value and the immediate offset from the decoder. Most instructions are arithmatic instructions operating on source registers. So, we have two source registers RFRD as shown in the below diagram. Here ALU is the calculator that we coded already. We also have memory Dmem, which stores the data or load the data. For storing the data, we get the source address and the immediate offset added up. The store data will write data to memory.

![image](https://github.com/user-attachments/assets/573c9c59-5dc4-4d2d-a357-01a82f2f37bf)

RV_D4SK1_L2_Starting Point Code for RISC-V Labs Part-1  

![image](https://github.com/user-attachments/assets/fb94a70c-2a53-41a3-9f71-59e9c31367c9)

RV_D4SK1_L3_Starting Point Code for RISC-V Labs Part-2

![image](https://github.com/user-attachments/assets/c4be2923-123b-4ae2-9b08-09867e75b0e2)

![image](https://github.com/user-attachments/assets/26b63ef1-16bf-441c-90b0-2661ace7fda9)

![image](https://github.com/user-attachments/assets/90247bd6-092d-419f-beba-914d483f039a)

RV-D4SK2 - Fetch and decode  
RV_D4SK2_L1_Implementation Plan and Lab for PC  

We will implement the cpu as mentioned in the below diagram.

![image](https://github.com/user-attachments/assets/2390c907-ee85-4b7f-ab9d-d84e8c6b57a3)

My work
![image](https://github.com/user-attachments/assets/18a48b1a-5e6d-46d4-942c-2832146e037a)

RV_D4SK2_L2_Lab For Instruction Fetch Logic

![image](https://github.com/user-attachments/assets/edceaafe-109a-48ae-82af-243c279d7cc8)

![image](https://github.com/user-attachments/assets/24caa7da-5b23-4db3-82c6-48ce92bd13dd)

RV_D4SK2_L3_Lab For RV Instruction Types IRSBJU Decode Logic

![image](https://github.com/user-attachments/assets/11346074-437a-4589-a3db-0318bd5cceb2)

My work
![image](https://github.com/user-attachments/assets/e0cd909a-6d45-4ed1-a416-0ebad896ae56)

RV_D4SK2_L4_Lab For Instruction Immediate Decode Logic For RV-ISBUJ

Now we will see from where the immediate value will be taken for different instructions.

![image](https://github.com/user-attachments/assets/617c3b5f-0c04-4a52-a064-ece07330057c)

My work
![image](https://github.com/user-attachments/assets/61596b96-500f-42c0-a35c-e9cd58a9fbf8)

RV_D4SK2_L5_Lab To Decode other Fields of Instructions For RV-ISBUJ

![image](https://github.com/user-attachments/assets/9079c6f8-9ac8-4e90-8d0b-2cae88951f3b)

My work
![image](https://github.com/user-attachments/assets/051be781-289c-41ed-8b60-e93d06c03abd)

RV_D4SK2_L6_Lab To Decode Instruction Field Based on Instr Type RV-ISBUJ

![image](https://github.com/user-attachments/assets/0f1a7a26-e05b-4207-88f6-09150e347c28)

My work
![image](https://github.com/user-attachments/assets/efff7143-d80a-4540-b6a8-5970abc9311a)

RV_D4SK2_L7_Lab To Decode Individual Instruction

The code "`BOGUS_USE" is used to say the computer that "it is ok, if the other signals present are not used", which is used used to avoid warings in log. It is the SV macro.  
Now we are using the instructions that are highly required for our purpose and ignoring other instructions now.

![image](https://github.com/user-attachments/assets/e6bb4561-827f-48ca-b44c-39f3dba3c4c0)

My work
![image](https://github.com/user-attachments/assets/af23be79-9385-408d-91ec-dceda9622006)



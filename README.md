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

RV_D3SK3_L4_Lab On 2-Cycle Calculator

![image](https://github.com/user-attachments/assets/1d2a08a0-d402-4b19-b7bd-dfe39ffcd385)

![image](https://github.com/user-attachments/assets/9ecb2d23-95fd-49f7-9c4e-5bce03fa8362)

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

RV_D3SK4_L5_Calulator Single Value Memory Lab

![image](https://github.com/user-attachments/assets/66005591-b4cd-44bd-8a37-387e2384b409)

RV Day 3 Wrap-up  
(Bonus) RV_D3SK5_L1_Introduction To Hierarchy Concept  

![image](https://github.com/user-attachments/assets/e238322d-12b5-40a2-bd40-107bdacd9227)

![image](https://github.com/user-attachments/assets/fb901476-6e7e-45dd-b7f7-ee37e4d8ec08)

![image](https://github.com/user-attachments/assets/3c632bf1-7c92-428c-9960-592be1e4f627)


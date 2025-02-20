![image](https://github.com/user-attachments/assets/c6b23727-d031-4095-a919-5ef617094ffb)![image](https://github.com/user-attachments/assets/5f8a6bbf-8dbb-44d1-8138-a8bf7776725c)# NASSCOM-RISC-V-based-MYTH-program

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


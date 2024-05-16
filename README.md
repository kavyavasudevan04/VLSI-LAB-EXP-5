## SIMULATION AND IMPLEMENTATION OF FINITE STATE MACHINE

## AIM:
To simulate and synthesis finite state machine using Xilinx ISE.

## APPARATUS REQUIRED: 
VIVADO 2023.2

# PROCEDURE:
STEP:1 Launch the Vivado 2023.2 software.<br>
 STEP:2 Click on “create project ” from the starting page of vivado.<br>
 STEP:3 Choose the design entry method:RTL(verilog/VHDL).<br>
 STEP:4 Crete design source and give name to it and click finish.<br>
 STEP:5 Write the verilog code and check the syntax.<br>
 STEP:6 Click “run simulation” in the navigator window and click “Run behavioral simulation”.<br>
 STEP:7 Verify the output in the simulation window.<br>

## Logic Diagram :

![image](https://github.com/navaneethans/VLSI-LAB-EXP-5/assets/6987778/34ec5d63-2b3b-4511-81ef-99f4572d5869)


## VERILOG CODE:
```
module finitestate(clk,rst,x,y);
input clk,rst,x;
output y;
reg [2:1]present,next;
parameter s0=2'b00,s1=2'b01,s2=2'b10,s3=2'b11;
always@(x,present)
case (present)
s0:if (x)
next=s1;
else
next=s0;
s1:if(x)
next=s1;
else
next=s2;
s2:if(x)
next=s3;
else
next=s0;
s3:if (x)
next=s1;
else
next=s2;
endcase
always@(negedge rst,posedge clk)
if (rst)
present=s0;
else
present=next;
assign y=(present==s3);
endmodule
```

## OUTPUT:
![image](https://github.com/SwarnaMallikaPL/VLSI-LAB-EXP-5/assets/160829667/9c48b7d8-076e-43e9-bc60-f93b112b44eb)


## RESULT:
&emsp;&emsp;Thus the simulation and implementation of Finite State MOORE Machine is done and the outputs are verified successfully.




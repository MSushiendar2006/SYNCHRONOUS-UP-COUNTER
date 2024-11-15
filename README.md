### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**
```
1.Setup Environment: Open Quartus Prime and create a new project. Name it appropriately and include the required libraries.
2.Code Implementation: Write and implement the Verilog code for the 4-bit synchronous up counter in Quartus Prime. Ensure that inputs and outputs are properly declared.
3.Compile the Code: Save the code and run the compilation process to check for any syntax or logical errors.
4.Generate RTL Diagram: Once the code compiles successfully, generate the RTL (Register Transfer Level) schematic to visually confirm the logic.
5.Simulate the Design: Use the simulation tool in Quartus Prime to generate and observe the timing diagram for the up counter to verify the correctness of the operation.
6.Analyze Output: Verify that the simulation output matches the expected truth table and ensures that the 4-bit counter increments properly with each clock pulse.
```

**PROGRAM**
```
Developed by:SUSHIENDAR M
RegisterNumber:212223040217
module exp11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```


## RTL LOGIC UP COUNTER:
![image](https://github.com/user-attachments/assets/6c49ba55-6a6f-49fc-867a-03b0dc1c0f0a)



## TIMING DIAGRAM FOR IP COUNTER:
![image](https://github.com/user-attachments/assets/5bc48eac-1d71-444d-9010-ee43b178b5cc)


## TRUTH TABLE:
![WhatsApp Image 2024-11-15 at 09 22 43_7de32a30](https://github.com/user-attachments/assets/911aa427-b543-43e5-89e1-c277a67349cc)


## RESULTS:
The 4-bit synchronous up counter was successfully implemented, compiled, and simulated. The RTL schematic, timing diagram, and truth table confirm that the counter works as expected, counting from 0 to 15.

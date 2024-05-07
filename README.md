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

1.Initialize the shift register to a known state (e.g., all zeros).

2.Input a bit serially into the shift register.

3.Shift the contents of the register one position to the right (or left).

4.Output the shifted bit from the last stage of the register.

5.Repeat steps 2-4 for each bit you want to input and shift.

**PROGRAM**

Program for flipflops and verify its truth table in quartus using Verilog programming. 

Developed by:MARINO SARISHA T RegisterNumber:212223240084
```
module exp11(out,clk,rstn);
input clk,rstn;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(!rstn)
     out<=0;
   else 
     out <= out+1;
end
endmodule
```
**RTL LOGIC UP COUNTER**
![Screenshot 2024-05-07 141805](https://github.com/Sarishatheiveegan/SYNCHRONOUS-UP-COUNTER/assets/144979465/74f44cac-7610-4737-8530-2534ff1d7d46)

**TIMING DIAGRAM FOR IP COUNTER**
![Screenshot 2024-05-07 141841](https://github.com/Sarishatheiveegan/SYNCHRONOUS-UP-COUNTER/assets/144979465/ef1d3481-8b23-422f-9f8c-353bd5c68124)

**TRUTH TABLE**
![Screenshot 2024-05-07 141823](https://github.com/Sarishatheiveegan/SYNCHRONOUS-UP-COUNTER/assets/144979465/dad5161b-b07a-468c-96f8-52403fce6548)

**RESULTS**
Thus the program executed successfully.

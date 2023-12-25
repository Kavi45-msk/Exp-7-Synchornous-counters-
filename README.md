# NAME: KAVI M S
# REFERENCE NUMBER: 23013458

# Exp-6-Synchornous-counters - up counter and down counter 
### AIM: To implement 4 bit up and down counters and validate  functionality.
### HARDWARE REQUIRED:  – PC, Cyclone II , USB flasher
### SOFTWARE REQUIRED:   Quartus prime
### THEORY 
# PROCEDURE
1.Create a new project in Quartus2 software . 
2.Name the project as uc for upcounter and dc for down counter.
3.Create a new verilog hdl file in the project file.
4.Name the module declare as dc and uc for down counter and upcounter. 
5.Within the module declare input and output variables.
6.Create a loop using if-else with condition parameter as reset.
7.End the loop. 
8.End the module

## UP COUNTER 
The counter is a digital sequential circuit and here it is a 4 bit counter, which simply means it can count from 0 to 15 and vice versa based upon the direction of counting (up/down). 

The counter (“count“) value will be evaluated at every positive (rising) edge of the clock (“clk“) cycle.
The Counter will be set to Zero when “reset” input is at logic high.The counter will be loaded with “data” input when the “load” signal is at logic high. Otherwise, it will count up or down.The counter will count up when the “up_down” signal is logic high, otherwise count down

Since we know that binary count sequences follow a pattern of octave (factor of 2) frequency division, and that J-K flip-flop multivibrators set up for the “toggle” mode are capable of performing this type of frequency division, we can envision a circuit made up of several J-K flip-flops, cascaded to produce four bits of output.
The main problem facing us is to determine how to connect these flip-flops together so that they toggle at the right times to produce the proper binary sequence.Examine the following binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1:
Binary count sequence, paying attention to patterns preceding the “toggling” of a bit between 0 and 1.

Note that each bit in this four-bit sequence toggles when the bit before it (the bit having a lesser significance, or place-weight), toggles in a particular direction: from 1 to 0.

Starting with four J-K flip-flops connected in such a way to always be in the “toggle” mode, we need to determine how to connect the clock inputs in such a way so that each succeeding bit toggles when the bit before it transitions from 1 to 0.

The Q outputs of each flip-flop will serve as the respective binary bits of the final, four-bit count:

Four-bit “Up” Counter
![image](https://user-images.githubusercontent.com/36288975/169644758-b2f4339d-9532-40c5-af40-8f4f8c942e2c.png)

# PROGRAM
```
module uc(clk, A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
A[2]=(((A[0])&(A[1]))^A[2]);
A[1]=(A[0])^A[1];
A[0]=A[0]^1;
end
endmodule
```

# RTL LOGIC FOR UP COUNTER

![292272771-496bb623-d669-4a79-99e4-5341616678cc](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/562108ae-6457-4d5e-9a10-1ba50269e12f)

# TRUTH TABLE
![292272854-4c0d7e64-63b8-470f-a5fd-6fd98807cbee](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/5843d2dd-ab8c-47e9-a752-52be3e656e81)

# TIMING DIAGRAM FOR UP COUNTER
![292272952-66671293-cfc2-4f8d-8fe3-ce8daed9eeeb](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/cda3ebc3-e182-47bb-aa52-b06b0e112857)

## DOWN COUNTER 
As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.4-bit Count Down Counter
![image](https://user-images.githubusercontent.com/36288975/169644844-1a14e123-7228-4ed8-81a9-eb937dff4ac8.png)

# PROGRAM 
```
module dc(clk,A);
input clk;
output reg [2:0]A;
always @(posedge clk)
begin
A[2]=(((~A[0])&(~A[1]))^A[2]);
A[1]=(~A[0])^A[1];
A[0]=1^A[0];
end
endmodule 
```

# RTL LOGIC DOWN COUNTER  
![292273158-4f806ce8-8ad7-4e2b-a7f2-552e41d7b967](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/6f5f423d-d4c7-423d-80c3-c62a7bbbf439)

# TRUTH TABLE 
![292273123-85fc4456-147c-483b-af07-c9fc684dc021](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/7c22c226-8184-4139-88e1-1b4e098379f3)

# TIMING DIAGRAM FOR DOWN COUNTER

![292273088-a9eb3ee3-1e47-4f8b-9abe-186fa4e7a088](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/8f07cdb5-c2bb-452f-b111-3b528e167b7b)

# RESULT
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

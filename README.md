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

The Q outputs of each flip-flop will serve as the respective binary bits of the final.

# PROGRAM
```
module up_counter(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=(q1&q2)^q3;
q2=q1^q2;
q1=1^q1;
end 
endmodule
```

# RTL LOGIC FOR UP COUNTER
![up](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/42e688c9-0f09-4855-aa94-999ef57fbd7c)


# TRUTH TABLE
![Screenshot 2023-12-27 202548](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/61101a6c-3bc6-4673-8f28-a6cc96261e20)


# TIMING DIAGRAM FOR UP COUNTER
![time](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/503e5497-1348-4cfe-8cb9-f85522c71464)


## DOWN COUNTER 
As well as counting “up” from zero and increasing or incrementing to some preset value, it is sometimes necessary to count “down” from a predetermined value to zero allowing us to produce an output that activates when the zero count or some other pre-set value is reached.

This type of counter is normally referred to as a Down Counter, (CTD). In a binary or BCD down counter, the count decreases by one for each external clock pulse from some preset value. Special dual purpose IC’s such as the TTL 74LS193 or CMOS CD4510 are 4-bit binary Up or Down counters which have an additional input pin to select either the up or down count mode.


# PROGRAM 
```
module COUNTER(clk,q1,q2,q3);
input clk;
output reg q1,q2,q3;
always@(posedge clk)
begin
q3=((~q2)&(~q1))^q3;
q2=(~q1)^q2;
q1=1^q1;
end
endmodule
```

# RTL LOGIC DOWN COUNTER  
![down](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/86302d1a-9941-44f5-b0c5-b4a4d197801c)

# TRUTH TABLE 
![Screenshot 2023-12-27 202534](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/f1f16bd2-e699-431f-b573-37a9d7058932)


# TIMING DIAGRAM FOR DOWN COUNTER
![Screenshot 2023-12-27 140354](https://github.com/Kavi45-msk/Exp-7-Synchornous-counters-/assets/147457752/2eebdbcf-f101-471e-a1b2-24a7d524a12f)

# RESULT
Thus synchornous counters up counter and down counter circuit are studied and the truth table for different logic gates are verified.

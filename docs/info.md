<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
This project is a 3-bit adder/subtractor, a single circuit that can perform two different arithmetic operations. The key to its dual functionality lies in the XOR gates and a control input, which we'll call K.
Addition Mode: When the control input K is set to 0, the XOR gates act as simple buffers. The inputs from the B operand (B2, B1, B0) pass through the XOR gates unchanged. The carry-in (Cin) for the first full adder is also set to 0. The circuit then behaves like a standard ripple-carry adder, adding the two 3-bit binary numbers, A and B (A+B). The carry bit from each full adder "ripples" to the next, just like how you carry a 1 when adding numbers on paper.
Subtraction Mode: When the control input K is set to 1, the XOR gates invert the inputs from the B operand. This effectively generates the one's complement of the B number. Simultaneously, the carry-in (Cin) is set to 1. This additional 1, combined with the one's complement of B, performs the two's complement of B. The circuit then calculates A+(−B), which is the same as A−B.
## How to test
To test the project, you need to provide 3-bit binary inputs for A and B and set the control line K.
Set up the Inputs: Use switches or buttons to set the values for the two 3-bit numbers:
A-inputs: A2, A1, A0
B-inputs: B2, B1, B0
Set the Control: Use another switch to control the operation:
K = 0: Puts the circuit in addition mode.
K = 1: Puts the circuit in subtraction mode.
Observe the Outputs: Use LEDs to display the results:
Sum/Difference: LEDs for S2, S1, S0.
Final Carry/Borrow: An LED for the final carry-out.


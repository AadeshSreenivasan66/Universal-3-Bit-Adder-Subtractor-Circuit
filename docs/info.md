<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
The 3-bit Adder/Subtractor can perform both addition and subtraction on two 3-bit inputs A and B, depending on the value of the selection input k.

Addition Mode (k = 0)
Each bit of B is XORed with k. When k = 0, the XOR output equals B. The three full adders then compute A + B using the XOR outputs as input, with the initial carry-in of the least significant bit set to 0.

Subtraction Mode (k = 1)
When k = 1, the XOR gates invert each bit of B, producing B'. The initial carry-in of the LSB full adder is set to 1. This effectively computes A + B' + 1, which is the two’s complement subtraction (A - B). The full adders handle the bitwise addition and generate the final result.

This design efficiently allows both operations using the same hardware, with XOR gates acting as conditional inverters and full adders performing the arithmetic.

## How to test
1)Addition Test:
Set k = 0.
Provide test inputs, such as A = 101 (5) and B = 011 (3).
The circuit should output 1000 (8).
Verify that other addition cases, including carry-over scenarios, work correctly.

2)Subtraction Test:
Set k = 1
Provide test inputs, such as A = 101 (5) and B = 011 (3).
The output should be 0010 (2).
Test additional cases where subtraction results in zero or a negative number, ensuring proper two’s complement behavior.

3)Boundary Tests:
Subtract a larger number from a smaller one, such as A = 010 (2) and B = 101 (5), and check if the result is correct using two’s complement representation.
Add two numbers where the result exceeds 3 bits and verify how carry-out is handled.

4)Consistency Checks:
Run a series of addition and subtraction operations and cross-check with manual calculations or simulation tools to ensure accuracy.

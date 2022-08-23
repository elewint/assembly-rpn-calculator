# COMP 40 hw08: Assembly RPN Calculator
Eli Intriligator and Colby Cho

Acknowledgements:
	Consulted the TAs during office hours for multiple parts of this assignment.

In this assignment, we programmed a reverse polish notation (RPN) calculator in the
assembly language of the UM virtual machine built for HW6.

## What has been correctly implemented:
To our knowledge, everything has been correctly implemented. We consistently
pass the diff test against the reference for any number of random inputs up to 1 million.

## Departures from the recommended calling convention:
- `r1` holds input during the waiting state (as is illustrated in sample code on the spec)
- `r3` holds our value stack pointer

## Print module implementation:
The print module uses tail-end recursion to print the most significant n - 1 digits
followed by the least significant digit of an n digit number.

## RPN calculator value stack:
The value stack is a stack with space for one million entries, where r3 points to
the top of the stack and the label end_valstack points to the bottom of the value stack.

## Sections created across .ums files:
`.section init` - Contains setup code, including code to set up the stack, code to initialize
				jump tables, and code to call main when setup is complete.
`.section rodata` - Contains jump tables.
`.section data` - Contains a preallocated call stack and value stack.
`.section text` - Contains procedure definitions, including the definition of main.

---

Hours spent analyzing the assignment: 2
Hours spent writing assembly code: 17
Hours spent debugging the calculator: 8
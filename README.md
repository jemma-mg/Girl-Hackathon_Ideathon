#  StuckAt_Found

StuckAt_Found is designed to find a test case that detects the stuck at fault in the circuit and the expected value of output to confirm the fault.

## Problem Statement
- Manufactured chips may have structural faults at certain places/nodes, which must be tested before being delivered to end users.
- The task is to design an algorithm and write its code to identify the input vector required to identify the fault at a given node in a given circuit.
- In a case, there would only be a single fault in the design.
- The algorithm should be efficient, robust and able to identify faults quickly.

#### Inputs
Available inputs are -
1. Circuit file (format provided below)
2. Fault node location
3. Fault type
   a. SA0 : stuck-at-0, a fault where node is not able to attain value 1, irrespective of inputs
   b. SA1 : stuck-at-1, a fault where node is not able to attain value 0, irrespective of inputs
   
#### Outputs
- The code should print a vector for inputs to test the fault, and the expected value of output to confirm the fault.
- The output should be printed to the following file in run directory - output.txt

#### Circuit Format
1. The circuit will have 4 inputs - A, B, C and D. All of which are boolean type (only 0 and 1 are valid inputs)
2. The circuit’s output will always be Z which is also a boolean.
3. The circuit will be built using the following operations -
   a. AND ( & ) gate
   b. OR ( | ) gate
   c. NOT ( ~ ) gate
   d. XOR ( ^ ) gate
4. The circuit would purely be a combinational logic.
5. All internal nodes in the circuit would be named as : "net_<alphanumeric string>"
6. Each input ( A / B / C / D ) would be utilized only once in the circuit.

## Algorithm
1. Start
2. Read the input files
3. Identify the node with fault and assign the complement value, i.e, for SA0 assign value at node as 1 and vice versa.
4. Propogate this complement value to output
5. Identify the input vectors to obtain the complemented output.
6. Write the input vector and expected value of output to confirm the fault to output file.
7. Stop

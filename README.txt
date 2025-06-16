📌 Project Title
Basic Assembly-Level Processor Implementation in Logisim

📚 Description
This project simulates a basic assembly-level processor using Logisim. The processor is built to execute a custom instruction set including LDA, ADD, STA, ISZ, BUN, and two custom instructions: MUL and DIV, used for multiplication and division respectively. The program performs arithmetic operations over a set of variables (A, B, C, and i) with a specific iteration loop and stores the result in memory. The behavior follows a simple algorithm:


int A, B, C, i;
for(i = 0; i < 3; i++) {
    C += A / B;
    A += A * B;
}
At the end of execution (after 3 iterations), for the input values:

A = 16

B = 2

C = 0
the expected outputs are:

C = 104

A = 432

B = 2

🖥️ System Specifications
Language/Platform: Logisim (Digital Logic Simulator)

Instruction Set Supported:

LDA: Load accumulator

ADD: Add memory to accumulator

STA: Store accumulator

ISZ: Increment and skip if zero

BUN: Branch unconditionally

MUL: Multiply (Custom, replaces BSA opcode)

DIV: Divide (Custom, replaces AND opcode)

🔧 Custom Instructions
MUL addr: Performs AC ← AC * MEM[addr] (Implemented using BSA opcode)

DIV addr: Performs AC ← AC / MEM[addr] (Implemented using AND opcode)

🧠 Architecture Highlights
Instruction Cycle: Standard fetch-decode-execute cycle (T0, T1, T2,...)

Control Unit: Custom micro-operations developed using control signals per time step

Arithmetic Unit: Supports multiplication and division using modified ALU

Memory: Editable ROM with hardcoded machine instructions

📁 Files Included
project.circ: Logisim circuit file of the CPU and memory setup

memory.txt: Memory initialization file with instruction machine code

report.pdf: Description of each instruction, timing signals (T0, T1, …), and hardware implementation

README.md: This file

groupX.zip: The full project in zipped format

✅ How to Run
Open project.circ in Logisim.

Load memory.txt into the ROM component (right-click → Load Image).

Run the circuit step-by-step using the clock button or run continuously.

Observe results in memory locations for A, B, and C.

🔄 Notes
Flip-flops are added to CLR signals for synchronous reset behavior.

Tunnel wires are used for clean circuit design.

Memory is persistent via external .txt file.

Interrupts are not implemented.

HALT is a placeholder; execution ends when counter exceeds program.


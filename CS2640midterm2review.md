# CS2640 - Midterm 2 Review

## Instruction Formats, Instruction Fetching, Execution Cycles
Three Instruction Formats:
- R
	```
	  6bit   5bit   5bit   5bit   5bit   6bit
	|  op  |  rs  |  rt  |  rd  |  sh  | func |		add	$t0, $t0, $t1
	```
- I
	```
	  6bit   5bit   5bit     16bit
	|  op  |  rs  |  rt  |    imm    |		addiu	$t0, $t0, 1
	```
- J
	```
	  6bit           26bits
	|  op  |          addr          |		jal	proc
	```


## Basic System Software Components

### Operating System

### Compiler

### Assembler

### Linker

### Loader

### Interpreter

## Instruction Set Architectures
- Encoding/Decoding

## Addressing Modes
- Type of Machines, Memory Accesses

## Assembly Instructions
- I/O
- Arithmetic
- Branching and Control Structuring
- Memory Accesses (Load and Store)
- Logical Operations
- Shift

## SPIM

## Dynamic Memory Allocation via the Heap
- syscall 9

## C-Strings - Zero Terminated String
- asciiz, .space, syscall 8, strlen, strcpy, malloc

## Constructing:

### if/else
### while
### switch

### Arrays
- Creating on:
	- In data segment
	- On heap
	- On stack segment
- Accessing
	- Linear access

		`
		base address + 4 = next index for array [CHANGE TO + 1 FOR BYTE]
		`
	- 2-D Arrays
## MIPS Procedure
- Call/return - jal proc/jr $ra
- Parameters passing via a-registers
- Use of the stack via the $sp register
- Leaf/non-leaf procedure
- Use of the s-register
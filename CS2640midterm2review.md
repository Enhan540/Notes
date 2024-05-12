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
### Fetch Cycle
- Step 1: Fetch
	- Uses PC, IR
	- Gets next instruction from PC, puts instruction into IR, and increments PC to the next instruction
		- MAR <- PC
		- MR (Memory Read from given address)
			- Data now available for MDR to get off of bus
		- IR <- MDR
- Step 2: Decode
	- IR (MDR, MAR possible)
	- Figures out what to do
- Step 3: Execute
	- Uses all GPR (General Purpose Registers), ALU, AC, IR, PC (if statements modify)

## Basic System Software Components

### Operating System
- book definition = supervising program that manages the resources of a computer for the benefit of the programs that run on that computer
- Interfaces between a user's program and the hardware and provides a variety of servies and supervisory functions.
- controls the sharing of and interaction among various computer units as they execute application programs
- assign computer resources to individual application programs
	- memory
	- disk space
	- move data
	- handle I/O



### Compiler
- book defintion = program that translates high-level language statements into the assembly language statements
- compiles high-level language program into a sequence of machine instructions
- may not be designed for a specific processor; however, a high-quality compiler is usually designed for, and with, a specific processor

### Assembler
- book definition = program that translates a symbolic version of instructions into the binary version

### Linker
- Systems program that combines independently assembled machine language programs and resolves all undefined labels into an executable.

### Loader
- systems program that places an object program in main memory so that it is ready to execute

### Interpreter
- program that sumulates an instruction set architecture
	- ex: Java Virtual Machine

## Instruction Set Architectures
- Encoding
	- Determine the type of instruction and opCode
	- Write the instruction into bits following the instruction's format
	- Translate everything into hex
	> addiu	$t0, $t1, 1
	> 
	> &nbsp;
	> 
	> addiu follows the I instruction format and has an opCode of 9
	> 
	> &nbsp;
	> 
	> I format: 
	> &nbsp;
	> 
	>   6bit   5bit   5bit     16bit
	> &nbsp;
	> 
	> |  op  |  rs  |  rt  |    imm    |
	> &nbsp;
	> 
	> opCode = 9 -> 1001
	> &nbsp;
	> 
	> addiu		rd, rs, imm
	> &nbsp;
	> 
	> rs = $t1 = 9 -> 1001
	> &nbsp;
	> 
	> rd = $t0 = 8 -> 1000
	> &nbsp;
	> 
	> imm = 1 -> 0...01
	> 
	> &nbsp;
	> 
	> Encoding: 001001 | 01001 | 01000 | 0000000000000001 |
	> 
	> &nbsp;
	> 
	> In Hex: 0010 | 0101 | 1001 | 0100 | 0000 | 0000 | 0000 | 0001 | = 25980001
- Decoding
	- Check the opCode (in hex) and the function code (if there is one) to identify the instruction
		- Do so by changing the hex code into binary to see the first 6 bits
	- Then figure out what registers are being used

## Addressing Modes
- Type of Machines: different machines use varying number of address registers, memory registers, or both in the instructions

- Memory Accesses
	- Calculate the number of memory accesses in portion of code:
		- Data
			- Add one for each time memory is read or written
			- LD	R1, A
				- 1 memory read: A to Register 1
		- Instruction
			- At least one since the instruction must be grabbed
			- If there are any memory mentioned, add one since it is an address
			- LD	R1, A
				- 1 instruction + 1 memory address = 2

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
	- Uses $a0 as a parameter for how many bytes to allocate
		- Must be a multiple of 4
	- Returns base address of dynamic memory array in $v0
	- ex:
		```
		#Assuming number of bytes is in $a0
		addiu	$sp, $sp, -4
		lw	$a0, ($sp)
		addi	$a0, $a0, 3
		srl	$a0, $a0, 2
		sll	$a0, $a0, 2
		li	$v0, 9
		syscall
		lw	$a0, ($sp)
		addiu	$sp, $sp, 4
		#B.A. in $v0
		```


## C-Strings - Zero Terminated String
- asciiz, .space, syscall 8, strlen, strcpy, malloc
```
#Data Segment
	.data
LINELEN = 40
NUMOFLINES = 10
inbuf:	.space	LINELEN
larray:	.word	0:NUMOFLINES
	.text
main:	
	#Display prompt to ask for lines to copy.
	#Reads a cstring from the user of length 40, including the '\0' character
	la	$a0, inbuf
	li	$a1, LINELEN
	li	$v0, 8
	syscall

	#Code to move to next line if length reached max.
	jal	cstrlen
	blt	$v0, 40, endif
	li	$a0, '\n'
	li	$v0, 11
	syscall
endif:
	la	$a0, inbuf
	lb	$t2, ($a0)
while:	

cstrlen:
	li	$v0, 0		#Sets up len counter.
	addiu	$sp, $sp, -8
	sw	$a0, ($sp)
	sw	$t0, 4($sp)
	lb	$t0, ($a0)
while1:	beqz	$t0, endw1
	addi	$v0, $v0, 1
	addiu	$a0, $a0, 1
	lb	$t0, ($a0)
	b	while1
endw1:	addiu	$a0, $a0, -1
	lb	$t0, ($a0)
if1:	beq	$t0, '\n', endif1
	addi	$t0, $t0, 1
endif1:	lw	$a0, ($sp)
	lw	$t0, 4($sp)
	addiu	$sp, $sp, 8

cstrdup:
	#Assuming inbuf is in $a0
	addiu	$sp, $sp, -16
	sw	$a0, ($sp)
	sw	$ra, 4($sp)
	sw	$t0, 8($sp)
	sw	$t1, 12($sp)

	jal	cstrlen
	addi	$a0, $v0, 1
	jal	malloc

	lw	$a0, ($sp)
	addiu	$sp, $sp, 4

	move	$t0, $a0
	move	$t1, $v0	#BA of dynamic memory still in $v0 to be returned

while2:	lb	$t2, ($t0)
	sb	$t2, ($t1)
	beqz	$t2, endw2
	addi	$t0, $t0, 1
	addi	$t1, $t1, 1
	b	while2
endw2:
	lw	$ra, ($sp)
	lw	$t0, 4($sp)
	lw	$t1, 8($sp)

malloc:
	#Assuming number of bytes is in $a0
	addiu	$sp, $sp, -4
	lw	$a0, ($sp)
	addi	$a0, $a0, 3
	srl	$a0, $a0, 2
	sll	$a0, $a0, 2
	li	$v0, 9
	syscall
	lw	$a0, ($sp)
	addiu	$sp, $sp, 4
	#B.A. in $v0
```

## Constructing:

### if/else
### while
### switch

### Arrays
- Creating on:
	- In data segment
		```
			.data
		array	.word	0:20
		array2	.word	1,2,3,4,5
		```
	- On heap
		```
		li	$a0, $t0	#Assume $t0 is number of bytes and is a multiple of 4
		li	$v0, 9
		syscall
		```
	- On stack segment
		```
		addiu	$sp, $sp, -$t0	#Assume $t0 is number of bytes and is a multiple of 4
		```
- Accessing
	- Linear access
		`
		base address + 4 = next index for array [CHANGE TO + 1 FOR BYTE]
		`
	- 2-D Arrays
		- create a matrix of numOfRow*numOfCol
		- matrix[row][col]
		- calculating effective offset:
			- matrix[t0][t1]
			- offset = (t0 * numOfCol * t1) * 4

## MIPS Procedure
- Call/return - jal proc/jr $ra
- Parameters passing via a-registers
- Use of the stack via the $sp register
- Leaf/non-leaf procedure
- Use of the s-register
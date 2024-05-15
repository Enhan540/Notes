# CS2640 Final Review

## Topics
1. Number Systems
2. Data Representation
3. Integer and Floating Point Representation
    - Integer and floating arithmetic
4. Computer Structure and Basic Components and Its Functions
5. Basic System Software Components (Operating Systems, Compiler, Assembler, Linker, Loader, and Interpreter)
6. Instructrion Formats and Instruction Fetching and Execution Cycles
7. Instruction set architectures (ISA)
    - Encoding/Decoding
8. Addressing Modes
9. Assembly Instructions
    - I/O, arithmetic, branch/control structure, memory accesses(load/store), logical operations, shift
10. Procedures
11. Strings, Records, and Arrays (1/2D)
12. Using Stack in Nested and Recursive Functions
13. Exceptions, interrupts, I/O Interfacing and Communication
    - Memory-mapped I/O
14. SPIM

## Number Systems
### Decimals
- Base 10:
    - Digits = 0 - 9
- Positional Notation:
    > 1234 = 1 x 10<sup>4</sup> + 2 x 10<sup>3</sup> + 3 x 10<sup>2</sup> + 4 x 10<sup>1</sup>
### Binary
- Base 2:
    - Digits: 0, 1
        - A.K.A. bit - binary digit
- Groups of bitsbyte
    - byte - group of 8 consecutive bits; smallest addressable unit of information
    - nibble - 4 bits
    - word - 2 bytes
### Octal
- Base 8
    - Digits: 0 - 7
    - can be represented using 3 bits
        - ex: 10 101 010<sub>2</sub> = 252<sub>8</sub>
    
### Hexadecimal
- Base 16:
    - Digits: 0 - 9, A, B, C, D, E, F
    - can be represented using four bits (nibble/half byte)
### 2's Complement
- A method to denote negative numbers
    - switch all the bits of the number (1's complement)
    - switch all bits of the number and adds 1 (2's complement)
- When using 2's complement, must specify number of bits
    - One bit is used to signify the sign of the number (MSBit)
#### Sign Extension
- When extending a number, copy the MSbit
    - ex: when working with a negative number
        - 1110 -> 1111 1110
### Binary Addition/Subtraction
- adding the binary numbers together
- subtraction = adding the 2's complement
### Endianness
- Big-endian, byte with largest significance is stored first
- Little-endian, opposite of big-endian

## Computer Structure and Basic Components + Functions
### Main Components
#### CPU
- CPU + Memory together = System on a chip
##### Basic Functional Components
- Control Unit
    - brain of CPU; controlls all operations of the CPU; sequences instructions
- Arithmetic and Logic Unit
    - does the arithmetic and logical operations
- Registers
    - stores data, instructions
- Program Counter
    - used for program execution cycle; stores the address to the next instruction
- Instruction Register
    - used for program execution cycle; contains current instruction
#### Main Memory
- holds instructions and data
- **von Neumann Architecture (Princeton)**
    - a.k.a. **Store-program computer concept**
#### Secondary Memory
#### Input Devices
#### Output Devices
#### Data Buses
- All components are connected by buses
    - 3 buses:
        - Address
        - Bus
        - Control

## Basic System Software Components
- Operating System
    - large program used to control the sharing of and interaction among various computer units as they execute application programs
- Compiler
    - turns high-level language into assembly language
- Assembler
    - turns assembly language into machine language
- Linker
    - combine objects into an executable
- Loader
    - loads the executable into memory and starts execution
- Interpreter
    - a computer program that can directly execute instructions written in a programming or scripting language without requiring them to have been compiled into machine language

## Instruction Set Architecture (ISA)
#### Definition
- abstract model of a computer
    - everything a machine language programmer needs to know in order to program a computer

### Instruction Formats and Instruction Fetching/Execution Cycles
#### Instruction Fetch Cycle
1. Fetch instructions
    - PC points to memory with next instruction, which IR takes and PC increments to next instruction
2. Decode Instruction
    - figure out what operations to be done and addressing mode(s)
3. Locate Operands
    - could be in memory or in register addresses
4. Fetch Operands
    - if in memory, it is necessary to do a memory read
5. Execute Operation by ALU
6. Store Results
    - either in memory location or register
7. Start again from Step #1
##### Fetch
- PC, IR (MAR, MDR)
##### Decode
- IR
##### Execute
- GPR, ALU, AC (All registers)
- REGS (IR, PC, MAR, MDR)
### Machine Instructions
- opcode field
    - specificies operation
- address fields
    - either memory address or register address
- mode field
    - specifies the way the address field is to be interpreted
### One, Two, Three-Address Machines
- Address fields of an instruction may consist of one, two, or three memory/register addresses
### Computing Number of Memory Accesses in 3-Register Address Machines
- each instruction is one memory read
- each memory address being used is one memory address in instruction and data read
## Procedures
### Register Usage
$a0 - $a3 = parameter passing
- If more parameters are needed, make room on the stack for the first four parameters, then add the other necessary parameters onto the stack ($sp)

$v0 - $v1- return registers

Procedures are marked by labels in front of the first line of that procedure
> label1:&emsp;addiu&emsp;$sp, $sp, -4
- Use the "jal" instruction to "call" the procedure, putting the procedure's label after "jal"
    - jalr instruction: can be used to jump to a procedure when the address of the procedure is in a register
- "jr $ra" instruction returns to the main method/code where the procedure was called
    - $ra has the return location (may need to be saved if the procedure is non-leaf, or there is a procedure call inside the procedure)
## Strings, Records, and Arrays (1/2D)

## Exceptions, interrupts, I/O Interfacing and Communication
**Exception** - event that requires a special handling by the CPU and initiates a change in the normal flow of program execution
- Breakpoints, arithmetic overflow, traps, and interrupts are all classified as exceptions
**Interrupt** - signal coming from I/O devices outside the CPU
- Interrupt is generated when I/O device needs the service of the CPU
- ISR (Interrupt Service Routine) - processes the interrupts from I/O devices and provides the requested services
    - a.k.a. trap handler
### Coprocessor Zero
Method to interrupt currently running programs
- contains number of specialized registers that can be accessed at the assembly language level for exception handling
    - SPIM's Displayed Registers
        - EPC: Coprocessor Register 14 (Exception Program Counter)
        - Cause: Coprocessor Register 13
        - BadVAddress: Coprocessor Register 8
        - Status: Coprocessor Register 12
    - New instructions
        - mfc0: move from coprocessor 0
            > mfco &emsp; $k0, $13&emsp;#$k0 has contents of Cause register
        - mtc0: move to coprocessor 0

#### Enabling Keyboard Interrupt
Receiver Control - 0xffff0000
- Interrupt bit - 2nd to last bit
- Ready bit - last bit

Receiver Data - 0xffff0004

Transmitter Control - 0xffff0008
- Interrupt bit - 2nd to last bit
- Ready bit - last bit

Transmitter Data - 0xffff000c

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
### Instruction Fetch Cycle
#### Fetch
- PC, IR
- Gets next instruction
#### Decode
- IR
#### Execute
- GPR, ALU, AC (All registers)

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
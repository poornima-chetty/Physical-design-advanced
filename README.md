# Physical-design-advanced
VLSI PHYSICAL DESIGN FOR ASIC                                                                            
**INTRODUCTION TO RISC V BASIC KEYWORDS**

**INSTRUCTION SET ARCHITECTURE:**

**An Instruction Set Architecture (ISA)** is a set of instructions that a computer's central processing unit (CPU) can execute. It defines the interface between the hardware and software of a computer system, allowing software programs to communicate with and control the underlying hardware.

**RISC V**
RISC-V is an open-source Instruction Set Architecture (ISA) designed to be simple, extensible, and versatile. Unlike many proprietary ISAs, RISC-V is developed collaboratively by the RISC-V Foundation and a wide community of contributors. The primary goals of RISC-V are to provide a foundation for a wide range of computing devices and applications, foster innovation in computer architecture, and encourage open collaboration in the industry.


**FROM APPS TO HARDWARE**
**APPS**:Application software is developed to cater to specific user needs and is typically distributed through various channels, including app stores, direct downloads from websites, or software packages included with hardware devices



**System software:** System software serves as an intermediary between hardware and application software, providing a stable and controlled environment for applications to run. It ensures resource allocation, memory management, process scheduling, and overall system stability. Without system software, computers would not be able to function effectively and run the applications that users rely on.

**Operating System:** The operating system is a fundamental piece of software that manages hardware resources and provides various services for both users and application programs. It controls tasks such as memory management, process scheduling, file system management, and user interface interaction. Examples of operating systems include Microsoft Windows, macOS, Linux, and Android.

**Compiler:** A compiler is a type of software tool that translates high-level programming code written by developers into assembly-level language.

**assembler***An assembler is a software tool that translates assembly language code into machine code or binary code that can be directly executed by a computer's processor.

**RTL:** RTL serves as an abstraction level in the design process that represents the behavior of a digital circuit in terms of registers and the operations that transfer data between them.

**Hardware:** Hardware refers to the physical components of a computer system or any electronic device. It encompasses all the tangible parts that make up a computing or electronic device and enable it to perform various tasks.
**Detail Description of Course Content**
**Pseudo Instructions:** Pseudo-instructions are used to simplify programming, improve code readability, and reduce the number of explicit instructions a programmer needs to write. They are especially useful for common programming patterns that involve multiple instructions. Ex: li, mv.

**Base Integer Instructions:** The term "base integer instructions" refers to the fundamental set of instructions that form the foundation for performing basic arithmetic, logical, and data movement operations. Ex: add, sub, and, or, xor, sll.

**Multiply Extension Intructions:** The RISC-V architecture includes a set of multiply and multiply-accumulate (MAC) extension instructions that enhance the instruction set to perform efficient multiplication and multiplication-accumulate operations. Ex: mul, mulh, mulhu, mulhsu.

**Single and Double Precision Floating Point Extension:** The RISC-V architecture includes floating-point extensions that provide support for both single-precision (32-bit) and double-precision (64-bit) floating-point arithmetic operations. These extensions are often referred to as the "F" and "D" extensions, respectively. Floating-point arithmetic is essential for handling real numbers with fractional parts and for performing accurate calculations involving decimal values.

**Application Binary Interface:** ABI stands for "Application Binary Interface." It is a set of rules and conventions that govern how software components interact with each other at the binary level. The ABI defines various aspects of program execution, including how function calls are made, how parameters are passed and returned, how memory is allocated and managed, and more.
**memory allocation pointer:**
Memory allocation refers to the process of assigning and managing memory segments for various data structures, variables, and objects used by a program. It involves allocating memory space from the system's memory pool and releasing it when it is no longer needed to prevent memory leaks.
The stack pointer is a register used by a program to keep track of the current position of the program's execution on the call stack

****Labwork for RISCV Toolchain
C Program
We wrote a C program for calculating the sum from 1 to n using a text editor,**
**
![sumton1c](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/46b743b2-83f3-41da-bf59-c6f4519171a6)
OUTPUT:

![output](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ab539ac0-0f18-4c67-9347-b741dd4dcdbd)
**RISCV GCC Compiler and Dissemble**
Using the riscv gcc compiler, we compiled the C program.

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

Using ls -ltr sum1ton.c, we can check that the object file is created.

To get the dissembled ALP code for the C program,

riscv64-unknown-elf-objdump -d sum1ton.o | less .

In order to view the main section, type /main.
![main](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/a431b5fe-f4c9-41d3-8945-f3b1f9d4c430)




![spike](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/722b2d6c-ca87-4b38-a5e8-e3297fe0c290)






**Spike Simulation and Debug**
spike pk sum1ton.o is used to check whether the instructions produced are right to give the correct output.



![spike](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/e37af776-ae7d![reg](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/a0d88b02-d12e-460c-8454-f6aa3dadcc79)
-414c-b008-ebeddc0e881e)

spike -d pk sum1ton.c is used for debugging


![spiked](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/12b8a1ca-9618-42ca-b257-4f306a8d0808)
The contents of the registers can also be viewed.


![reg](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/acf94fb5-4f1d-4f60-b660-a5fc802d73f7)

**Integer Number Representation****

**Unsigned numbers**:An unsigned number contains just zero or positive values, whereas a signed number has both positive and negative numbers along with the value zero.
**Signed numbers**:The term signed numbers refers to positive and negative numbers. If no sign is shown, the number automatically is considered positive.
**LAB WORK
 Write a C program that shows the maximum and minimum values of 64bit unsigned numbers.**


 code:
![unsignedcode](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/29fe00ab-5464-4533-9611-861071e3e3a1)

output:


![unsigned](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/4ad6224d-119a-487c-b44d-e54c86e7b10d)

**
****write a C program that shows the maximum and minimum values of 64bit signed numbers.
******
code:


![signed](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/226b2baa-e677-4681-a60c-c76ad7d997dc)
output:

![signedo](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/87301e9f-34c8-481c-b74a-afcda8a2f11e)


**DAY 2

Application Binary Interface**
**Introduction to ABI**
An Application Binary Interface (ABI) is a set of rules and conventions that define how binary code interfaces between different components of a computer system, such as software libraries, operating systems, and user applications. The ABI encompasses details about data types, calling conventions, memory layout, and system call interfaces, among other things. It plays a crucial role in ensuring that software components developed by different parties can interact seamlessly and run on the same hardware or software platform.
![new](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/e02ad039-d1a9-44de-b5e0-05a75ca911ef)




Memmory Allocation for Double Words
64-bit number (or any multi-byte value) can be loaded into memory in little-endian or big-endian. It involves understanding the byte order and arranging the bytes accordingly

Little-Endian: In little-endian representation, you store the least significant byte (LSB) at the lowest memory address and the most significant byte (MSB) at the highest memory address.
Big-Endian: In big-endian representation, you store the most significant byte (MSB) at the lowest memory address and the least significant byte (LSB) at the highest memory address.




**Load, Add and Store Instructions**
Load, Add, and Store instructions are fundamental operations in computer architecture and assembly programming. They are often used to manipulate data within a computer's memory and registers.

Load Instructions: Load instructions are used to transfer data from memory to registers. They allow you to fetch data from a specified memory address and place it into a register for further processing.


**Example ld x6, 8(x5)**



ld is the load double-word instruction.
x6 is the destination register.
8(x5) is the memory address pointed to by register x5 (base address + offset).
Store Instructions: Store instructions are used to write data from registers into memory.They store values from registers into memory addresses


**Example sd x8, 8(x9)**



sd is the store double-word instruction.
x8 is the source register.
8(x9) is the memory address pointed to by register x9 (base address + offset).
Add Instructions: Add instructions are used to perform addition operations on registers. They add the values of two source registers and store the result in a destination register.

****Example add x9, x10, x11
**
**

add is the add instruction.
x9 is the destination register.
x10 and x11 are the source registers.

**REGISTERS AND THEIR ABI NAMES**
The names of registers in an ABI (Application Binary Interface) can vary depending on the architecture and platform  working with. Different computer architectures have their own sets of registers with specific names and purposes
![ABI](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/75914b41-9e34-4b39-b98d-89bdbf1d38d5)


**Labwork using ABI Function Calls**

![ASM](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/d9e02993-efa3-432e-95a7-6eaecb29deb9)
When calling an assembly function from C code:

WE need to follow the calling convention of your platform. This includes passing arguments either through registers or the stack, preserving registers as needed, and following other platform-specific rules.
When using inline assembly, We need to specify input and output operands, which tell the compiler which registers or memory locations are used for inputs and where the output is stored.
During execution:

The assembly instructions we've provided are executed by the CPU just like any other machine code.
The assembly code can interact with C variables and perform operations that might be challenging or impossible to express using only C code.
**Review ASM Function Calls**

**c program code**

![asmcode](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/b92bdc90-d484-4bf2-b1ea-ee2677242f9f)
**assembly file**
![assembly](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/2c796ce7-af38-4cf8-9ceb-401e330bfa90)

**Simulate C Program using Function Call**

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o asm.o asm.c assemble.s
this command creates an object file asm.o

spike pk asm.o
after compilation
[ou](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/271ccd26-66c3-4bef-9506-9df3e2cb2e39)




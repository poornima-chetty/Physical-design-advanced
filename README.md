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

![new](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/0f6a596f-5b2b-4f0e-96c0-0b3191f4b81b)



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
![ou](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3d755a64-6053-4a03-b396-aeac7d1f5d1a)

riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o asm.o asm.c assemble.s
this command creates an object file asm.o

spike pk asm.o
after compilation
![ou](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3d755a64-6053-4a03-b396-aeac7d1f5d1a)



**Day-1-Introduction to Verilog RTL design and Synthesis
Introduction to Verilog RTL design and Synthesis
Introduction to Yosys synthesizer





**

A simulator is a design used to check the design
**RTL DESIGN** is used to check for adherenvce to the spec by simulating the design
iverilog is used in this cOurse.
**IVERILOG**Icarus Verilog is an implementation of the Verilog hardware description language compiler that generates netlists in the desired format (EDIF).

**TEST BENCH: **a code module that describes the stimulus to a logic design and checks whether the design's outputs match its specification.

**HOW SIMULATOR WORKS!**
SIMULATOR LOOKS FOR THE CHANGES ON THE INPUT SIGNALS.
THE OUTPUT IS EVALUATED BASED ON THE INPUT.
IF NO CHANGE IN THE INPUT , NO CHANGE IN THE OUTPUT AS WELL.
**IVERILOG DESIGN FLOW**
![IVERILOG](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/82574966-31a2-46d2-841f-d4e4a91c8f4b)

**Labs using iVerilog and GTKwave**
step 1:
mkdir vsd
step 2:
 cd vsd
 step 3:
 git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
Creates a folder called sky130RTLDesignAndSynthesisWorkshop in the vsd directory.

[Screenshot from 2023-08-27 18-54-07](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/d945e733-4612-444b-b02e-e552e0f71d10)
my_lib : contains all the library files

lib : contains sky130 standard cell library used for our synthesis

verilog_model : contains all the standard cell verilog modules of the standard cells contained in the .lib

verilog_files : contains all the verilog source files and testbench files which are required for labs
i**Verilog GTKwave Part-1**
 1.cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

we have loaded the source code along with the testbench code into the iverilog simulator

2.iverilog good_mux.v tb_good_mux.v

We can see that an output file a.out has been created.

3../a.out
![kk](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/d25c7adb-c580-47f6-a738-3cd385dbb950)


The output of the iverilog, a vcd file, is created which is loaded into the simualtor gtkwave.

gtkwave tb_good_mux.vcd

[kk](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/d25c7adb-c580-47f6-a738-3cd385dbb950)

![ooo](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/47f1af36-b526-4193-8965-1fcde9126c7a)
**iVerilog GTKwave Part-2**
**In order to view the contents in the files,

gvim tb_good_mux.v -o good_mux.v

t**b_good_mux.v **
module good_mux (input i0 , input i1 , input sel , output reg y);
always @ (*)
begin
	if(sel)
		y <= i1;
	else 
		y <= i0;
end
endmodule

tb_good_mux.v
timescale 1ns / 1ps
module tb_good_mux;
	// Inputs
	reg i0,i1,sel;
	// Outputs
	wire y;

        // Instantiate the Unit Under Test (UUT)
	good_mux uut (
		.sel(sel),
		.i0(i0),
		.i1(i1),
		.y(y)
	);

	initial begin
	$dumpfile("tb_good_mux.vcd");
	$dumpvars(0,tb_good_mux);
	// Initialize Inputs
	sel = 0;
	i0 = 0;
	i1 = 0;
	#300 $finish;
	end

always #75 sel = ~sel;
always #10 i0 = ~i0;
always #55 i1 = ~i1;
endmodule
**
**
**Introduction to Yosys and Logic Synthesis**

**Introduction to Yosys
Synthesizer**

It is a tool used for converting RTL design code to netlist.
Here, the synthesizer used is Yosys.
Yosys

It is an open-source framework for Verilog RTL synthesis and formal verification.
Yosys provides a collection of tools and algorithms that enable designers to transform high-level RTL (Register Transfer Level) descriptions of digital circuits into optimized gate-level representations suitable for physical implementation on hardware.
![SETU P](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ff505c0c-acec-4144-a4f9-c048d33ed27e)

**Netlist along with the tesbench is fed to the iverilog simulator.**
The vcd file generated is fed to the gtkwave simulator.
The output on the simulator must be same as the output observed during RTL simulation.
Same RTL testbench can be used as the primary inputs and primary outputs remain same between the RTL design and synthesised netlist.

![WWW](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/b8f2a3ac-db29-428d-bd2c-a4ad941b191b)
****Introduction to Logic Synthesis**
**
**** **LOGIC SYNTHESIS***ynthesis is the process of converting a high-level description of design (Verilog/VHDL) into an optimized gate-level representation. Logic synthesis uses a standard cell library which have simple cells, such as basic logic gates like AND, OR, and NOR, or macro cells, such as adder, muxes, memory, and flip-flops.

**.LIB**
 Once your RTL design is complete, you use a synthesis tool (like Yosys) to convert your RTL into a gate-level netlist using the standard cells from the .lib file. The .lib file contains information about the delay, power, and other characteristics of each standard cell.
 
 **Why different flavors of gate?**

In order to make a circuit faster, the clock frequency should be high.
For that, the time period of the clock should be as low as possible.

In a sequential circuit, clock period depends on:
Clock to Q of flip-flop A.
Propagation delay of combinational circuit.
Setup time of flip-flop B.

**Fast Cells:**

Fast cells, also known as "high-performance cells" or "critical-path cells," are designed to operate at higher clock frequencies. They are optimized for speed and are used in the critical paths of a design where timing is most critical.

**Slow Cells:**

Slow cells, also referred to as "low-power cells" or "non-critical-path cells," are designed for low power consumption. They prioritize energy efficiency over speed.

**Selection of the Cells**

We have to guide the Synthesizer to choose the flavour of cells that is optimum for implementation of logic circuit.
More use of faster cells leads to bad circuit in terms of power and area and also hold time violations.
More use of slower cells leads to sluggish circuits amd may not meet the performance needs.
Hence the guidance is offered to the synthesiser in the form of constraints.


**Labs using Yosys and Sky130 PDKs**
To invoke yosys

1.cd
2.cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
3.Type yosys
![YOSYCS](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/7854be46-c93e-462d-9474-febab4ab73ef)
**To read the library**

1. read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

To read the design

2.read_verilog good_mux.v

To syntheis the module

 synth -top good_mux
 
![read](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/bf3371ed-16c4-4f9b-a894-6dd5709ce9ae)
**To generate the netlist**

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib


![netlist](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/c2b458e6-7f45-4be9-8d51-a3a41976ce76)


It gives a report of what cells are used and the number of input and output signals.
**To write the netlist**

write_verilog good_mux_netlist.v

!gvim good_mux_netlist.v

**To view a simplified code**


 write_verilog -noattr good_mux_netlist.v!

!gvim good_mux_netlist.v

![vimvim](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/c5d2ab30-f6ac-42a7-b3be-592a459615ac)

![pic](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/2e1bcba0-40df-4a1d-bbd9-8243ccbf6980)

****Day 4**
**Introduction to Timing Dot Libs**

**To view the contents in the .lib


![png](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/64f198a9-5011-4255-bdcd-ccc076f52591)

The first line in the file library ("sky130_fd_sc_hd__tt_025C_1v80") ** :
tt : indicates variations due to process and here it indicates Typical Process.
025C : indicates the variations due to temperatures where the silicon will be used.
1v80 : indicates the variations due to the voltage levels where the silicon will be incorporated.
It also displays the units of various parameters.



![cell](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/9b19cc97-9839-427e-be43-e223f1b1e094)


It gives the features of the cells

To enable line number :se nu

To view all the cells :g//

To view any instance :/instance

Since there are 5 inputs, for all the 32 possible combinations, it gives the delay, power and all the other parameters for each cell.
![BATTERY](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/f64d485d-f0fe-41c0-8193-fda7814648ba)

**Hierarchical vs Flat Synthesis
**
Hierarchical Synthesis Hierarchical synthesis is an approach in digital design and logic synthesis where complex designs are broken down into smaller, more manageable modules or sub-circuits, and each module is synthesized individually. These synthesized modules are then integrated back into the overall design hierarchy. This approach helps manage the complexity of large designs and allows designers to work on different parts of the design independently.
The file we used in this lab is multiple_modules.v

cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
gvim multiple_modules.v
![POO](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/be53fbb0-448d-4a7e-8c09-cc4188c5a5a9)

multiple_modules instantiates sub_module1 and sub_module2

Launch yosys

read the library file read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read the verilog file  read_verilog multiple_modules.v

synth -top multiple_modules to set it as top module
![loop](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/7b7d2964-ff47-41be-a01b-fdabbd85223c)

![synth](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/0a4b3d86-818e-4dcf-a577-30864954fbfb)



****Flattened Synthesis ****Flattened synthesis is the opposite of hierarchical synthesis. Instead of maintaining the hierarchical structure of the design during synthesis, flattened synthesis combines all modules and sub-modules into a single, flat representation. This means that the entire design is synthesized as a single unit, without preserving the modular organization present in the original high-level description.

**Launch yosys**
read the library file read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read the verilog file  read_verilog multiple_modules.v
synth -top multiple_modules to set it as top module
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
flatten to write out a flattened netlist

write_verilog -noattr multiple_modules_flat.v
!gvim multiple_modules_flat.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/a36f6f0c-ca2e-4354-b8c5-8d68c164670d)

******Various Flop Coding Styles and Optimization
Why do we need a Flop?**
A flip-flop (often abbreviated as "flop") is a fundamental building block in digital circuit design.
It's a type of sequential logic element that stores binary information (0 or 1) and can change its output based on clock signals and input values.
In a combinational circuit, the output changes after the propagation delay of the circuit once inputs are changed.
During the propagation of data, if there are different paths with different propagation delays, then a glitch might occur.
There will be multiple glitches for multiple combinational circuits.
Hence, we need flops to store the data from the combinational circuits.
When a flop is used, the output of combinational circuit is stored in it and it is propagated only at the posedge or negedge of the clock so that the next combinational circuit gets a glitch free input thereby stabilising the output.
We use control pins like set and reset to initialise the flops.
They can be synchronous and asynchronous.

**D Flip-Flop with Asynchronous Reset**

When the reset is high, the output of the flip-flop is forced to 0, irrespective of the clock signal.
Else, on the positive edge of the clock, the stored value is updated at the output.
gvim dff_asyncres_syncres.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/a219faad-eaea-48a3-9ac5-8e99b9c7486c)
**
**D Flip_Flop with Asynchronous Set
**
When the set is high, the output of the flip-flop is forced to 1, irrespective of the clock signal.
Else, on positive edge of the clock, the stored value is updated at the output.
gvim dff_async_set.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/f79a717d-8283-422d-9721-fca3fe359fb3)

D Flip-Flop with Synchronous Reset

When the reset is high on the positive edge of the clock, the output of the flip-flop is forced to 0.

Else, on the positive edge of the clock, the stored value is updated at the output.

gvim dff_syncres.v

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3cc94521-04b9-494b-b63d-753996c9aaee)

D Flip-Flop with Asynchronous Reset and Synchronous Reset

When the asynchronous resest is high, the output is forced to 0.
When the synchronous reset is high at the positive edge of the clock, the output is forced to 0.
Else, on the positive edge of the clock, the stored value is updated at the output.
Here, it is a combination of both synchronous and asynchronous reset DFF.
gvim dff_asyncres_syncres.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/b6d591ed-54c0-4157-bc7a-cab9d9629581)

**Lab Flop Synthesis Simulations

**D Flip-Flop with Asynchronous Reset
**
Simulation
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_asyncres.v tb_dff_asyncres.v
./a.out
gtkwave tb_dff_asyncres.vcd
![aync](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/b27cca36-33cf-46ef-8363-cdec42df17b0)
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/b2092cfa-882e-49ee-8a90-90d42a78a815)
**Synthesis**
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files

yosys

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog dff_asyncres.v

synth -top dff_asyncres

dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/5e87419a-0ecd-4b9d-b94e-0aaeaaf8c6e9)


**D Flip_Flop with Asynchronous Set
**
**Simulation**
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_async_set.v tb_dff_async_set.v
./a.out
gtkwave tb_dff_async_set.vcd
![rak](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/855a6aba-d516-4b37-942d-d185b66d66b6)
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3037d41d-e20f-4ba2-96a4-6c576864ef89)
**Synthesis**
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_async_set.v
synth -top dff_async_set
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/26ae8907-a501-4bb5-aba9-894846eb4b26)
**D Flip-Flop with Synchronous Reset
**
**Simulation
**
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
iverilog dff_syncres.v tb_dff_syncres.v
./a.out
gtkwave tb_dff_syncres.vcd


![poo](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/234c17d9-4386-4d9b-a178-92adb2dad991)

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ea22557f-9b3e-497a-b102-397d691fe646)
**Synthesis
**
cd vsd/sky130RTLDesignAndSynthesisWorkshop/verilog_files
yosys
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog dff_syncres.v
synth -top dff_syncres
dfflibmap -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib 
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/a19e84bb-fe9c-416a-a1db-36a787c95572)

**Interesting Optimisations**



![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/6ef09884-5a12-45d0-a0ac-cab0490461d7)
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog mult_2.v
synth -top mul2
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/32ae145e-7a53-46d3-814a-fc2d7c30d025)
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/466ed62d-64ae-4a8d-b1cd-c8169637042e)
write_verilog -noattr mul2_netlist.v
!gvim mul2_netlist.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/554405f0-2991-4cfa-a91b-febaac610771)
gvim mult_8.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/e5c10d7b-f6ac-4e06-8b8c-828d830119c9)
read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib  

read_verilog mult_8.v

synth -top mult8

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ba0a0d9b-cbcb-412c-8a37-b1aff6a6cfad)
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/e8ef3281-0672-474b-a933-42c7a71fb32b)

write_verilog -noattr mult8_netlist.v
!gvim mult8_netlist.v
![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3202f463-31c4-4c52-97c1-1ac4030b49ca)


Day 5
Introduction to Optimisations
Combinational Optimisation
Combinational logic refers to logic circuits where the outputs depend only on the current inputs and not on any previous states.
Combinational optimization is a field of study in computer science and operations research that focuses on finding the best possible solution from a finite set of options for problems that involve discrete variables and have no inherent notion of time.
Optimising the combinational logic circuit is squeezing the logic to get the most optimized digital design so that the circuit finally is area and power efficient.
Techniques for Optimisations:
Constant propagation is an optimization technique used in compiler design and digital circuit synthesis to improve the efficiency of code and circuit implementations by replacing variables or expressions with their constant values where applicable.
Boolean logic optimization, also known as logic minimization or Boolean function simplification, is a process in digital design that aims to simplify Boolean expressions or logic circuits by reducing the number of terms, literals, and gates required to implement a given logical function.
Sequential Logic Optimisations
Sequential logic optimizations involve improving the efficiency, performance, and resource utilization of digital circuits that include memory elements like flip-flops and latches.
Optimizing sequential logic is crucial in ensuring that digital circuits meet timing requirements, consume minimal power, and occupy the least possible area while maintaining correct functionality.
Optimisation methods:
Sequential constant propagation, also known as constant propagation across sequential elements, is an optimization technique used in digital design to identify and propagate constant values through sequential logic elements like flip-flops and registers. This technique aims to replace variable values with their known constant values at various stages of the logic circuit, optimizing the design for better performance and resource utilization.
State optimization, also known as state minimization or state reduction, is an optimization technique used in digital design to reduce the number of states in finite state machines (FSMs) while preserving the original functionality.
Sequential logic cloning, also known as retiming-based cloning or register cloning, is a technique used in digital design to improve the performance of a circuit by duplicating or cloning existing registers (flip-flops) and introducing additional pipeline stages. This technique aims to balance the critical paths within a circuit and reduce its overall clock period, leading to improved timing performance and better overall efficiency.
Retiming is an optimization technique used in digital design to improve the performance of a circuit by repositioning registers (flip-flops) along its paths to balance the timing and reduce the critical path delay. The primary goal of retiming is to achieve a shorter clock period without changing the functionality of the circuit.





**Combinational Logic Optimisations**
opt_check
```gvim opt_check.v```


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/9a76ad63-3014-47d3-a1f3-be9fe878da7c)


```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```

```read_verilog opt_check.v```

```synth -top opt_check```

```opt_clean -purge```

```abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```

show



![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/11da5b62-9e08-463d-b540-4750c77bb390)


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/275b6622-d8d1-43cd-9f34-7ce09a57b86f)

opt_check2
gvim opt_check2.v


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/e39c1449-0d84-428e-b79b-a700efc9f273)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

read_verilog opt_check2.v

synth -top opt_check2

opt_clean -purge

abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib

show

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/4d8918e6-4ef1-4e5f-b6f4-889a65fb5549)


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/3119c0d5-34bf-4b56-a9a6-102e6b7b0438)
opt_check3
```gvim opt_check3.v```

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ee4a2c63-825b-484b-820e-1f85c9c64fd5)


```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
```read_verilog opt_check3.v```
```synth -top opt_check3```
```opt_clean -purge```
``abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
show


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/74ba69ca-248c-46f9-8c8d-8bbe120c4ac5)




![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/bb34d708-109c-44b6-befd-2b50fb6ae8ee)


opt_check4
gvim opt_check4.v

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/c6ca01dd-f2ff-4676-ab16-e8dff95a26ed)

read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
read_verilog opt_check4.v
synth -top opt_check4
opt_clean -purge
abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib
show



![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/460fef59-7410-4572-a70b-53ee8197dd0a)



![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/7841fb35-5955-479a-9abc-ac72ae6873c1)


multiple_module_opt
```gvim multiple_module_opt.v```

![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/ce65f147-9ce4-4e33-9ec9-41343369855a)


```read_liberty -lib ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
```read_verilog multiple_module_opt.v```
```synth -top multiple_module_opt```
```opt_clean -purge
``abc -liberty ../lib/sky130_fd_sc_hd__tt_025C_1v80.lib```
show


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/525c86aa-2ed3-48d9-99ce-7b8eaa41e35c)


![image](https://github.com/poornima-chetty/Physical-design-advanced/assets/142583396/88aa2bb0-3066-4e71-aa8b-196056418c09)










.







**













..












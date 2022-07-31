# processors

## architecture

A stored-program computer stores data and instructions in the same way.
The VNA implements a stored-program computer.
VNA: CPU = CU + ALU
In the VNA, the CPU, memory and IO are connected to/via the bus.

flex-container:✫sm_tmp_xpihn7q.png✫
In the (modern revisions of) von neumann architecture, the three buses are the ⟮control bus⟯, the ⟮address bus⟯, and the ⟮data bus⟯
Stored-program computers can present a security risk due to the fact that data can contain maliscious instructions.

The harvard architecture separates instructions and data (= does not store them in the same way/treat them differently)
Modern processors are claimed to be stored-program computers (specifically VNA), but since they separate data and instructions to a certain extent, they may be considered modified Harvard architecture to a certain extent.

## electronics

### integrated ＆ discrete circuits

IC = integrated circuit
an integrated circuit is a set of electronic circuit on a piece of semiconductor material.
A chip is the piece of semiconductor material on which an integrated circuit is realized.
Today, the chip is almost always made using silicon.
The opposite of an integrated circuit is a discrete circuit.
A discrete circuit is a 'traditional' circuit, i.e. a circuit made up of different parts.
ICs are orders of magnitude faster, smaller, less power hungry, etc. than discrete circuits.

### processors

A processor is any circuit that performs operations.
A processor core is a self-contained processing unit.
A processor can potentially consist of multiple processor cores.
A microprocessor is a processor implemented on an IC.
Almost all modern processors are microprorcessors.

A SoC is a IC that doesn't just include the CPU, but also other components, such as the GPU, memory, radio modems, etc.
As time has been progressing, more and more things have been moving onto the SoC.
moore's law is the observation that the number of transistors in a IC doubles ⟮every two years⟯

## CPU

CPU = central processing unit

CPU is often used in three different senses: The whole unit executing instructions, potentially consisting of multiple CPU cores, a CPU core, or even the whole SOC, potentially containing the GPU, modems, etc.
to differentiate, I will call CPUs in the sense of a self-contained processing unit CPU/processor cores.
to differentiate, I will never call SOCs CPUs (if I can avoid it.).
to differentiate, I will call the main processor, potentially consisting of multiple CPU cores, a CPU.
A multi-core processor is when the chip contains multiple CPU cores.

### registers

A processor generally has between 10-100 registers.
There are many different kinds of registers:
register|contains
General Purpose Registers|mostly whatever you like
Register: Stack Pointer|stack pointer
address register|memory addresses
data register|binary data
accumulator|intermediary results of a calculation
status/flag register|status flags for the outcome of operations

status register = flag register

The flag/status register might hold flags such as 
zero flag|ALU calculation was zero
overflow flag|ALU calculation resulted in result larger than word size
sign flag|ALU calculation resulted in negative number

Program counter (PC) is also called Instruction Pinter (IP)
The Instruction Pointer/Program counter is a register that contains the memory address of the next instruction.
The instruction Register contains the current machine language instruction (opcode + operands)

Instead of a single accumulator, modern processors generally have many registers that can be used as accumulators.

### ALU

ALU  Arithmetic logic unit
https://upload.wikimedia.org/wikipedia/commons/0/0f/ALU_block.gif
the ALU is a combinational logic circuit.
The ALU performs arithmetic and bitwise operations.
A basic ALU takes two imputs and returns an output, generally all of the word size of the encapsulating CPU.
A basic ALU, besides its two inputs and an output, has a status flag input and output as well as an opcode input.

#### Adders

An adder is a logic circuit (I think?) that chains logic gate to perform addition.
Adders are used within the ALU.
A half-adder adds two binary digits and outputs a sum and a carry.
A full adder is like a half-adder, but also takes a carry-in.
A half and a full-adder ouptuts an output of size 2 bit.
Chaining full adders allow us to do arbitrary large binary addition.

### CU

CU  Control Unit

## machine code ＆ instruction set

Assembly language is largely syntactic sugar for machine code.
Machine code consists of machine language instructions.
Machine code and thus machine language instructions are what run directly on the processor, at least in the classical model.
In fact, by now, there is often a layer below machine code known as microcode.
opcode is short for operation code
Within a machine language, an instruction is defined by an opcode.
Within a machine language, an instruction consists of the opcode it is defined by, plus zero or more operands.
An instruction set architecture defines the instruction set plus a bunch of other processor features (such as registers, addressing, I/O) (however, the two terms are often also used interchangably)
The instruction set is the set of operations a processor supports, which bit sequences represent which  machine language instructions, and how the arguments are organized.
Depending on the instruction set, machine langauge instructions may all be the same length or not.
In a general sense, a word is the fundamental unit used by a processor of a given ISA ≈ how many bits a PU may address at once.
The length of a word is the word size.
In general, most registers are word-sized, as are memory cells.
The largest possible memory address is also word-sized (since otherwise, how would you address them) .
what is 32 bit in a 32-bit processor and 64 bit in a 64-bit processor is the size of memory addresses and thus the ⟮the word size⟯

A Load-store architecture is a type of instruction set architecture which only has instructions that either do ALU operation ⟮access (load/store) memory⟯, never at the same time.
For a load-store architecture, all things being operated on must be in registers.

The machine code of a program depends on the ISA, but also on other things about the computer (e.g. OS)

arch with no args prints the current ISA family
the arch command can be made to run programs on other ISA families via arguments.

### Instruction-level parallelism

Instruction-level parallelism is the parallel execution of instructions of a single thread (thus it is different from concurrency).
In general, the goal of instruction-level parallelism is to keep all of the processor busy
fors of instruction-level parallelism include Instruction pipelining, Out-of-order execution + register renaming, speculative execution + branch prediction.
Instruction pipelining attempts to keep every part of the processor busy with some instruction by dividing incoming instructions into a series of sequential steps (the eponymous "pipeline") performed by different processor units with different parts of instructions processed in parallel.
Out-of-order execution executes instructions as resources are available, rather than the order in the program, if this is possible.
register renaming is a technique that abstracts logical registers from physical registers.
Register renaming allows us to eliminate false data dependencies coming from write after read dependencies, enabling more out-of-order execution.
If compilers did not reuse registers, register renaming would not be necessary, however this is often difficult in practice.
speculative execution is executing instructions before we know if they will be needed
speculative execution is worthwhile if the cost of waiting until we know if the instructions will be needed to be executed is higher than the cost of speculatively executing.
speculative execution is most commonly referred to in the case of instuction pipelining, but may also be performed in many higher-level tasks.
speculative execution (in processors) is most often performed in the case of control flow, where branch prediction is often used to try and guess which branch is most likely.

#### RISC instruciton pipelining

Instruction fetch › Instruction decode and register fetch › Execute › Memory access › Register write back 

### Hazards

In processors, a hazard is when the next instruction cannot execute in the following cycle, or doing so would lead to an error.
Data dependence is when an instruction depends on the data of the preceeding statement.
Data hazards ocur when instructions exhibit data dependence modify data in different stages of a pipeline, potentially leading to race conditions.
Three type of data hazards:
read after write, write after read, write after write.
read after write is a true dependency: it cannot be resolved.
write after write is an output dependency: it can be resolved by just anulling the first write.
write after read is an anti-dependency, it can be solved by register renaming.

### RISC CISC

RISC  Reduced instruction set computer
CISC  Complex instruction set computer

The design goals of RISC and CISC are different: while CISC tries to use as few lines of assembly as possible and thus uses more complex, featureful instructions that take multiple clock cycles, RISC uses simple instructions that only take a single clock cycle to be quick.

#### CISC

x86 is a family of instruction set architectures
x86 are the most common type of CISC architectures.
x86 architectures with 64-bit word size are called x86_64
x86_64 may also be called AMD64 or Intel 64
the architecture is called x86 b/c the first processor with it was the Intel 8086.
CISC is the dominant architecture on desktop/laptops as of 2020, though it is slowly changing

#### RISC

ARM is a family of instruction set architectures
ARM ISAs are the most common type of RISC arcchitectures.
While PowerPC was also a RISC ISA and was widely used in all sorts of products, RISC largely became mobile/embedded-only in the mid 2000s until 2021, with apple's switch to ARM RISC processors and their use in in e.g. the worlds most powerfull supercomputer 富岳.
RISC chips generally have far lower power consumption than CISC chips.
Most but not all RISC ISAs, including ARM and RISC-V, are also load-store ISAs.
CPI = clocks/cycles per instruction
In general, a RISC ISA has 1 CPI, with fixed-length instructions.
⟮RISC-V⟯ is a ⟮RISC⟯ instruction set architecture that is ⟮open source⟯.

## cache

processor caches are used to speed up memory access, which is especially important since processor memory is orders of magnitude slower than processing speed.
The cache levels that are common as of 2021 are L1, L2 and L3 cache, with L4 cache slowly becoming more common.
L1 cache is the fastest cache level, and it goes downwards from there
Multi-level caches are caches that are composed of different cache levels.
The organization of multi-level caches into faster/slower cache levels is known as the cache hierarchy.
processor finds memory location in cache   cache hit
processor does not find memory location in cache   cache miss
When a cache miss occurs, the processor generally needs to wait while the data is being fetched
the ⟮Cache replacement policy⟯ is the policy that decides what to 'evict' on having to add something new to the cache on a cache miss

## clocking

A clock signal ⟮coordinates/synchronizes the circuits⟯ the circuits of the thing it's governing.
A clock signal is usually a square wave with a high and low state.
In relation to the clock signal's square wave the circuits activate on ⟮on one (or both) of the (vertical-ish) edges⟯, depending on the implementation
⟮A synchronous circuit⟯ is a circuit where the changes are synchronized by a clock signal.
processors are (made of) synchronous circuits
DDR  Double data rate
⟮DDR (double data rate)⟯ is the technology that activates the circuit. both on the rising and the falling edge of the clock signal

## assembler

Why don't we just write programs in machine code/assembler?  extremely mühselig and error-prone
Today, assembler/machine code is almost always generated by compilers/interpreters/etc.

## scheduling

scheduling is the action of assigning resources to perform tasks.
In the context of processors, scheduling is the assigment of processor cores to execute threads.

## chipset


flex-container:✫sm_chipset.svg✫
The chipset is responsible for data flow between the processor, memory and other components
In the past, the northbridge and southbridge made up the chipset.
The northbridge controlled/connected the faster components such as the CPU, memory, PCIe.
the southbridge controlled/connected IO, PCI/AGP.
When they still existed northbridge and the southbridge were connected.
Over time, more and more of especially northbridge chipset functions moved onto the SoC, and so the chipset is as of 2020 generally just one chip. 
Slowly, even the functions of the one chip left of the chipset are moving onto the SoC itself.
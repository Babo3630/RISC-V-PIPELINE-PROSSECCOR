
# RISC-V 5-Stage Pipelined Processor 

This project implements a **basic 5-stage pipelined RISC-V processor** using Verilog/SystemVerilog. The design is intended **purely for learning and experimentation**, helping students understand how pipelining increases instruction throughput compared to a single-cycle CPU.

⚠️ **Important:** This processor does **not** implement hazard detection or forwarding. To ensure correct execution, only **independent instructions** should be executed back-to-back.


## Project Highlights

* **Classic 5-Stage Pipeline Architecture**
* Supports the **RV32I base integer instruction set**
* Simple and readable HDL code for educational use
* Clear separation of pipeline stages using pipeline registers
* Ideal for understanding pipeline behavior, timing, and instruction overlap
* Written in **Verilog / SystemVerilog**
* No data, control, or structural hazard handling (by design)

---

## Pipeline Stages Overview

The processor follows the standard 5-stage RISC pipeline:

1. **IF – Instruction Fetch**
   Fetches the instruction from instruction memory using the program counter.

2. **ID – Instruction Decode**
   Decodes the instruction and reads operands from the register file.

3. **EX – Execute**
   Performs arithmetic/logic operations or calculates effective memory addresses.

4. **MEM – Memory Access**
   Handles load and store operations with data memory.

5. **WB – Write Back**
   Writes the final result back to the register file.

---

## Pipeline Execution Model

* Multiple instructions are active in the pipeline simultaneously.
* Each instruction advances one stage per clock cycle.
* Pipeline registers store intermediate data and control signals.
* Once the pipeline is full, the processor can complete **one instruction per cycle**, provided there are no dependencies.

### Pipeline Flow

```
IF → ID → EX → MEM → WB
```

---

## Supported Instruction Set

### Integer (R-Type) Instructions

* `ADD`, `SUB`, `AND`, `OR`, `XOR`
* `SLL`, `SRL`, `SRA`
* `SLT`, `SLTU`

### Immediate (I-Type) Instructions

* `ADDI`, `ANDI`, `ORI`, `XORI`
* `SLTI`, `SLTIU`
* `SLLI`, `SRLI`, `SRAI`

### Load & Store Instructions

* Loads: `LB`, `LH`, `LW`, `LBU`, `LHU`
* Stores: `SB`, `SH`, `SW`

### Branch Instructions

* `BEQ`, `BNE`
* `BLT`, `BGE`
* `BLTU`, `BGEU`

### Jump Instructions

* `JAL`, `JALR`

### CSR Instructions

* `CSRRW`, `CSRRS`, `CSRRC`
* `CSRRWI`, `CSRRSI`, `CSRRCI`

⚠️ **Instruction dependencies are not resolved automatically.** Avoid consecutive instructions that rely on previous results.

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Moizadlh/RISCV_PiplinedArchitecture.git
```

### 2. Open the Project

* Open the folder in **Visual Studio Code**
* Install a **SystemVerilog extension** for better syntax highlighting

### 3. Compile the Design

Use any HDL simulator such as:

* ModelSim
* Vivado
* QuestaSim
* Icarus Verilog (if supported)

Compile all Verilog/SystemVerilog source files.

### 4. Run the Simulation

* Execute the provided testbench
* Observe how instructions progress through each pipeline stage

### 5. View Waveforms

* Open generated waveform files in **GTKWave**
* Track signals such as:

  * Program Counter
  * Pipeline registers
  * ALU outputs
  * Memory access signals

---

## Learning Experiments You Can Try

* Execute independent ALU instructions to observe full pipeline utilization
* Analyze load and store behavior across pipeline stages
* Study branch and jump execution timing
* Modify the design to add:

  * Forwarding logic
  * Hazard detection
  * Pipeline stalling

---

## Educational Purpose

This project is **not optimized for performance or correctness in real workloads**. Its primary goal is to help learners:

* Understand pipelined CPU architecture
* Visualize instruction overlap
* Explore pipeline timing and control signals
* Build a foundation for advanced topics like hazard handling and superscalar designs



* Make it **shorter and more professional**
* Convert it into **LaTeX-style academic wording**
* Add **images/ASCII pipeline diagrams**
* Rewrite it for **resume / portfolio presentation**


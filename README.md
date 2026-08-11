# 🖥️ Computer Architecture — 32-Bit ARM & SAP-1

### RTL Design • SystemVerilog • Processor Architecture • Digital Design • Verification • Logisim

A computer architecture project implementing a **32-bit ARM-style processor in SystemVerilog** and simulating the **SAP-1 architecture in Logisim**, with a focus on RTL design, datapath and control logic, instruction execution, and functional verification.

---

## 🌟 Project Overview

This project explores **processor architecture, RTL design, and functional verification** through two complementary processor implementations:

- 🧠 32-bit ARM-style single-cycle CPU using SystemVerilog
- ⚡ SAP-1 processor architecture using Logisim
- 🔧 RTL datapath and control-unit design
- 🧪 Simulation and functional verification
- 💻 Assembly-based instruction testing
- 📊 Circuit-level and waveform analysis

The project demonstrates the process of translating processor architecture into **digital hardware, RTL modules, datapaths, control logic, and verified instruction execution**.

---

## 🎯 Project Objectives

- Design and implement a 32-bit ARM-style CPU using SystemVerilog.
- Develop processor datapath and control logic using RTL design principles.
- Simulate and verify processor functionality through test programs.
- Design and analyze the SAP-1 architecture using Logisim.
- Validate instruction execution and data movement at the circuit level.
- Understand the interaction between registers, ALU, memory, buses, and control logic.

---

## 🧠 32-Bit ARM Processor

The ARM processor was implemented as a **32-bit single-cycle CPU using SystemVerilog** and organized using RTL design principles.

### Architecture

```text
                 ┌─────────────────────┐
                 │   Instruction Mem   │
                 └──────────┬──────────┘
                            │
                            ▼
                   ┌────────────────┐
                   │ Instruction    │
                   │ Decode         │
                   └───────┬────────┘
                           │
            ┌──────────────┼──────────────┐
            ▼              ▼              ▼
      ┌──────────┐   ┌──────────┐   ┌──────────┐
      │ Register │   │ Control  │   │ Immediate│
      │   File   │   │   Unit   │   │  Logic   │
      └────┬─────┘   └──────────┘   └────┬─────┘
           │                              │
           └──────────────┬───────────────┘
                          ▼
                    ┌──────────┐
                    │   ALU    │
                    └────┬─────┘
                         │
                         ▼
                   ┌──────────┐
                   │  Memory  │
                   └────┬─────┘
                        │
                        ▼
                    Write Back
```

### ⚙️ ARM Processor Components

| Component | Function |
|---|---|
| Program Counter | Tracks instruction address |
| Instruction Memory | Stores processor instructions |
| Register File | Stores general-purpose registers |
| ALU | Performs arithmetic and logical operations |
| Control Unit | Generates processor control signals |
| Immediate Logic | Processes immediate operands |
| Data Memory | Handles memory operations |
| Multiplexers | Controls datapath selection |
| Write-Back Logic | Updates destination registers |

### 🔄 Instruction Execution

The processor follows the instruction execution flow:

```text
Instruction Fetch
       │
       ▼
Instruction Decode
       │
       ▼
Register Read
       │
       ▼
Execute / ALU
       │
       ▼
Memory Access
       │
       ▼
Write Back
```

### 🧪 ARM Verification

The processor was verified through simulation and instruction-level testing.

```text
              Assembly Program
                     │
                     ▼
              Instruction Data
                     │
                     ▼
              ARM Processor RTL
                     │
                     ▼
                  Simulation
                     │
                     ▼
              Waveform Analysis
                     │
                     ▼
             Functional Verification
```

Verification focused on:

- Instruction execution
- Register operations
- ALU functionality
- Control signals
- Datapath behavior
- Memory operations
- Program-counter updates
- Instruction flow

Assembly test programs were developed and executed to validate processor functionality and expected results.

---

## ⚡ SAP-1 Processor

The project also implements the **SAP-1 (Simple-As-Possible Computer)** architecture using Logisim.

SAP-1 provides a simplified processor model for understanding fundamental CPU components and their interactions.

### Main Components

- Program Counter
- Memory
- Instruction Register
- Control Unit
- Accumulator
- B Register
- ALU
- Output Register
- Common Bus

### 🏗 SAP-1 Architecture

```text
                    ┌──────────────┐
                    │    Memory    │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │ Instruction  │
                    │   Register   │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │   Control    │
                    │    Unit      │
                    └──────┬───────┘
                           │
                           ▼
                    ┌──────────────┐
                    │     Bus      │
                    └──────┬───────┘
                           │
             ┌─────────────┼─────────────┐
             ▼             ▼             ▼
        ┌─────────┐   ┌─────────┐   ┌─────────┐
        │   A     │   │   B     │   │   PC    │
        │ Register│   │ Register│   │ Register│
        └────┬────┘   └────┬────┘   └─────────┘
             │             │
             └──────┬──────┘
                    ▼
                ┌───────┐
                │  ALU  │
                └───┬───┘
                    │
                    ▼
                ┌───────┐
                │  OUT  │
                └───────┘
```

### 🧪 SAP-1 Simulation & Verification

The SAP-1 architecture was simulated in Logisim to validate:

- Instruction fetching
- Instruction decoding
- Register transfers
- ALU operations
- Control signals
- Memory access
- Program-counter updates
- Instruction execution sequence

Circuit-level analysis was used to trace data movement and validate processor behavior.

---

## 🔬 Verification Approach

Both processor implementations were validated through simulation and functional testing.

```text
                 Test Program
                      │
                      ▼
              Instruction Fetch
                      │
                      ▼
               Instruction Decode
                      │
                      ▼
                Datapath Control
                      │
                      ▼
                  ALU / Memory
                      │
                      ▼
                Register Update
                      │
                      ▼
                Expected Result
                      │
                      ▼
                 Verification
```

---

## 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Hardware Description Language | SystemVerilog |
| Digital Design | RTL Design |
| Processor Architecture | ARM, SAP-1 |
| Simulation | SystemVerilog Simulator, Logisim |
| Verification | Functional Simulation, Test Programs |
| Programming | Assembly |
| Architecture | Datapath, Control Unit, ALU, Registers, Memory |
| Analysis | Waveform and Circuit-Level Analysis |

# 🖥️ Computer Architecture — 32-Bit ARM & SAP-1

[![SystemVerilog](https://img.shields.io/badge/Language-SystemVerilog-blue.svg?style=for-the-badge&logo=IEEE)](https://en.wikipedia.org/wiki/SystemVerilog)
[![Logisim](https://img.shields.io/badge/Tool-Logisim-red.svg?style=for-the-badge)](http://www.cburch.com/logisim/)
[![Architecture](https://img.shields.io/badge/Architecture-ARM32%20%7C%20SAP--1-orange.svg?style=for-the-badge)](#)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

> **RTL Design • SystemVerilog • Processor Architecture • Digital Design • Verification • Logisim**

A comprehensive computer architecture project implementing a **32-bit ARM processor** in SystemVerilog RTL and simulating the **SAP-1 (Simple-As-Possible) processor** architecture in Logisim. This repository focuses on RTL design, processor datapaths, control units, assembly execution, and functional simulation verification.

---

## 📋 Table of Contents

- [🌟 Overview](#-overview)
- [🎯 Project Objectives](#-project-objectives)
- [🧠 32-Bit ARM Processor (SystemVerilog RTL)](#-32-bit-arm-processor-systemverilog-rtl)
  - [Core Architecture & Datapath](#core-architecture--datapath)
  - [Component Breakdown](#component-breakdown)
  - [Instruction Execution Flow](#instruction-execution-flow)
  - [RTL Verification & Waveforms](#rtl-verification--waveforms)
- [⚡ SAP-1 Architecture (Logisim Simulation)](#-sap-1-architecture-logisim-simulation)
  - [Block Diagram](#block-diagram)
  - [Simulation & Operations](#simulation--operations)
- [🔬 Verification Approach](#-verification-approach)
- [🛠️ Technology Stack](#️-technology-stack)
- [📁 Repository Structure](#-repository-structure)
- [🚀 How to Run & Simulate](#-how-to-run--simulate)
- [📜 License](#-license)

---

## 🌟 Overview

This project explores **processor architecture and RTL implementation** through two complementary designs:

* 🧠 **32-Bit ARM Processor**: A single-cycle / pipelined ARM-style core implemented from scratch in **SystemVerilog RTL**.
* ⚡ **SAP-1 Processor**: Designed and simulated at the gate/module level in **Logisim** to study fundamental CPU mechanics.
* 🔧 **RTL Datapath & Control**: Implementation of registers, ALU, decode units, immediate generation, and control buses.
* 🧪 **Functional Verification**: Waveform analysis, instruction testbenches, and assembly program execution.

---

## 🎯 Project Objectives

* Design a functional 32-bit ARM-style processor using SystemVerilog.
* Implement hardware datapaths, multiplexers, immediate extensions, and control logic using clean RTL principles.
* Verify instruction execution (Data Processing, Memory Access, Branching) through test benches and simulation software.
* Study fundamental CPU microarchitecture using Malvino's SAP-1 architecture in Logisim.
* Analyze signal transitions, flag registers, ALU operations, and memory timing across instructions.

---

## 🧠 32-Bit ARM Processor (SystemVerilog RTL)

### Core Architecture & Datapath

```text
                  ┌─────────────────────┐
                  │   Instruction Mem   │
                  └──────────┬──────────┘
                             │
                             ▼
                    ┌────────────────┐
                    │   Instruction  │
                    │    Decode      │
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


### Instruction Execution Flow:
┌──────────────────┐
 │ Instruction Fetch│ ──► Fetch machine code from Instruction Memory at [PC]
 └────────┬─────────┘
          ▼
 ┌──────────────────┐
 │ Instruction Decode│──► Decode Opcode, Condition, Register fields (Rn, Rm, Rd)
 └────────┬─────────┘
          ▼
 ┌──────────────────┐
 │  Register Read   │ ──► Read operands from Register File; generate Immediate values
 └────────┬─────────┘
          ▼
 ┌──────────────────┐
 │  Execute / ALU   │ ──► ALU calculates result or computes effective memory address
 └────────┬─────────┘
          ▼
 ┌──────────────────┐
 │  Memory Access   │ ──► Read/Write to Data RAM (LDR / STR) if applicable
 └────────┬─────────┘
          ▼
 ┌──────────────────┐
 │    Write Back    │ ──► Write ALU result or loaded data back to destination register



##Verification approach 
┌──────────────┐      ┌─────────────────┐      ┌──────────────────┐
│ Assembly     │ ───► │ RTL / Circuit   │ ───► │ State Monitor    │
│ Test Vector  │      │ Execution       │      │ (Registers/Mem)  │
└──────────────┘      └─────────────────┘      └────────┬─────────┘
                                                        │
                                                        ▼
┌──────────────┐                               ┌──────────────────┐
│ PASS / FAIL  │ ◄──────────────────────────── │ Compare with     │
│ Report       │                               │ Expected Values  │
└──────────────┘                               └──────────────────┘
 └──────────────────┘

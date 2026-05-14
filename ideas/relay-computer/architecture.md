# Relay Computer Architecture

The relay computer is a deterministic, electromechanical computing system designed for long‑term civic use, local repair, and generational continuity. Its architecture emphasizes mechanical transparency, audible/visible state changes, and complete maintainability using workshop‑level tools.

This document provides a high‑level overview of the machine’s structure, subsystems, and design principles.

---

## 📐 Design Goals

The relay computer is built around five architectural priorities:

- **Legibility** — every operation is visible, audible, and inspectable  
- **Determinism** — no hidden state, no probabilistic behavior  
- **Local Manufacturability** — all parts can be built or repaired in small workshops  
- **Salvage Compatibility** — components can be sourced from non‑industrial environments  
- **Civic Reliability** — the machine must be trusted by non‑experts  

These goals shape every subsystem described below.

---

## 🧱 Core Subsystems

The relay computer consists of the following major components:

### 1. Control Unit
Implements the instruction cycle:

- READ  
- DECODE  
- COMPUTE  
- WRITE  
- COMMIT  

The control unit is entirely relay‑driven, with visible state indicators and audible transitions. Timing is governed by a mechanical escapement or low‑frequency drive motor.

### 2. Arithmetic Logic Unit (ALU)
A mechanical‑relay hybrid subsystem performing:

- addition  
- subtraction  
- comparison  
- threshold checks  

The ALU uses differential gearing or equivalent mechanical summing elements where appropriate, preserving transparency and reducing relay count.

### 3. Register Bank
A set of electromechanical registers storing intermediate values. Each register:

- is relay‑latched  
- has visible mechanical indicators  
- can be manually inspected or cleared  
- is addressable via plugboard routing  

### 4. Tape Reader
A 12‑row punched‑tape reader providing:

- instruction encoding  
- operand selection  
- branch labels  
- error detection via misalignment sensing  

The tape path is fully accessible for cleaning and inspection.

### 5. Plugboard
Defines the machine’s configuration for a given job:

- register routing  
- ALU operand selection  
- output formatting  
- branch label mapping  

The plugboard is the primary interface for programmers.

### 6. Output Unit
A mechanical printer or typewheel assembly producing:

- numeric results  
- state summaries  
- error codes  
- audit‑friendly output  

Output is designed to be legible, durable, and archivable.

---

## 🔄 Instruction Cycle Overview

The relay computer executes instructions in a deterministic sequence:

1. **READ** — sense the next 12‑row tape segment  
2. **DECODE** — interpret opcode and operands  
3. **COMPUTE** — perform ALU or control operation  
4. **WRITE** — store results or update state  
5. **COMMIT** — finalize changes atomically  

This cycle is driven by a mechanical tick (1–10 Hz depending on power source).

---

## 🧭 Architectural Constraints

To ensure long‑term maintainability and civic trust, the architecture forbids:

- sealed components  
- solid‑state electronics  
- microcontrollers  
- hidden memory  
- self‑modifying code  
- high‑precision machining beyond workshop capability  

All logic must be visible, audible, and mechanically inspectable.

---

## 🔌 Power Model

The relay computer is designed for:

- hand‑crank operation  
- pedal operation  
- small DC generators  
- micro‑grids  
- solar‑buffered low‑voltage systems  

Typical power envelope:

- **Peak:** 15–30 W  
- **Average:** 3–10 W (1.5–6 W with efficiency upgrades)  
- **Idle:** near zero  

---

## 🛠 Maintainability

The architecture is intentionally modular:

- relay banks are removable  
- tape path is fully accessible  
- ALU gears can be cleaned and inspected  
- plugboard wiring is documented and replaceable  
- registers can be manually reset  

Maintenance doctrine is defined in `mechanics-logbook.md`.

---

## 🧩 Extensibility

The architecture supports optional, backward‑compatible enhancements:

- latching relays  
- high‑resistance coils  
- permanent‑magnet biasing  
- LED‑based optical indicators  
- duty‑cycle‑optimized logic patterns  

These are documented in `idea-cards/`.

---

## 🎯 Purpose

This architecture is not a historical reconstruction.  
It is a blueprint for **sovereign, community‑owned computation** — a machine that can be built, understood, repaired, and trusted for generations.


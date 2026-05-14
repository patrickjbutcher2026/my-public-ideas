# Conceptual Blueprints and Subsystem Schematics

This document provides high‑level conceptual blueprints for the relay computer. These are not construction drawings — they are architectural diagrams expressed in words, intended to guide workshop fabrication, subsystem layout, and operator understanding.

The goal is clarity, not precision. Every subsystem is designed to be buildable with hand tools, salvageable components, and local workshop capability.

---

## Purpose of the Blueprints

These blueprints exist to:

- define subsystem boundaries  
- show how components interact  
- guide physical layout  
- support maintenance and repair  
- ensure long‑term reproducibility  

They are intentionally descriptive rather than prescriptive.

---

## System Overview

The relay computer consists of five major assemblies:

1. Control Unit  
2. Arithmetic Logic Unit (ALU)  
3. Register Bank  
4. Tape Reader  
5. Plugboard and Routing Panel  
6. Output Unit  

Each assembly is modular and removable.

---

## Control Unit Blueprint

The control unit orchestrates the five‑phase instruction cycle:

- READ  
- DECODE  
- COMPUTE  
- WRITE  
- COMMIT  

### Physical Layout

- A relay bank arranged in rows of 8–12 relays  
- Timing relays grouped near the escapement or motor governor  
- Indicator lamps or flags mounted above each relay row  
- Wiring looms routed along wooden or metal rails  

### Key Components

- Step‑advance relay  
- Decode matrix  
- Phase‑sequencing relays  
- Branch evaluation relays  

The control unit is the “clockwork brain” of the machine.

---

## ALU Blueprint

The ALU performs addition, subtraction, comparison, and threshold checks.

### Physical Layout

- A mechanical summing element (gear differential or lever‑based adder)  
- Relay‑driven input selectors  
- Output latch mounted adjacent to the summing mechanism  
- Visible mechanical motion for operator inspection  

### ALU Stages

1. Operand selection  
2. Mechanical summing  
3. Relay‑based sign detection  
4. Output latching  

The ALU is intentionally slow but perfectly transparent.

---

## Register Bank Blueprint

The register bank stores intermediate values.

### Physical Layout

- Four to eight registers arranged in a horizontal row  
- Each register composed of a relay latch pair  
- Mechanical or LED indicators showing bit state  
- Manual reset levers accessible from the front panel  

### Register Structure

Each register includes:

- Input latch  
- Output latch  
- Pre‑commit latch  
- Indicator element  

The separation of latches ensures atomic COMMIT behavior.

---

## Tape Reader Blueprint

The tape reader is the primary input device.

### Physical Layout

- 12‑pin sensing array  
- Sprocket wheel driven by escapement or low‑RPM motor  
- Tape guides with wide tolerances  
- Access panel for cleaning and inspection  

### Tape Path

1. Entry guide  
2. Sprocket engagement  
3. Sensing array  
4. Exit guide  
5. Take‑up spool (optional)  

The tape reader is designed for reliability over precision.

---

## Plugboard Blueprint

The plugboard defines job‑specific routing.

### Physical Layout

- Grid of sockets arranged in a rectangular matrix  
- Patch cords with durable insulation  
- Routing diagram mounted above or beside the board  
- Labels for registers, ALU inputs, outputs, and branch labels  

### Functions

- Operand routing  
- Register selection  
- Output formatting  
- Branch label mapping  

The plugboard is the programmer’s primary interface.

---

## Output Unit Blueprint

The output unit produces durable, auditable results.

### Physical Layout

- Mechanical printer or typewheel  
- Relay‑driven character selection  
- Paper feed mechanism  
- Output tray or spool  

### Output Types

- Numeric results  
- State summaries  
- Error codes  
- Audit logs  

The output unit is designed for clarity and archival stability.

---

## Wiring and Looms

Wiring is organized into:

- horizontal looms for subsystem connections  
- vertical looms for power distribution  
- color‑coded signal paths  
- removable harnesses for relay banks  

Wiring must be accessible, inspectable, and replaceable.

---

## Frame and Mounting

The machine is mounted on:

- a wooden or metal frame  
- vibration‑damped feet  
- removable side panels  
- hinged front access  

The frame is part of the machine’s maintainability.

---

## Expansion Points

The architecture supports:

- additional registers  
- extended ALU modes  
- auxiliary tape readers  
- secondary output devices  
- diagnostic panels  

Expansion must preserve visibility and determinism.

---

## Summary

These conceptual blueprints define the physical and logical structure of the relay computer. They ensure the machine remains:

- buildable  
- maintainable  
- inspectable  
- reproducible  

The blueprints are not final drawings — they are a foundation for workshop interpretation and community adaptation.

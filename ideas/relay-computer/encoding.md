# Instruction Encoding (12‑Row Tape Format)

The relay computer uses a fixed 12‑row punched‑tape format for all instructions.  
This encoding is designed for:

- mechanical legibility  
- low error rates  
- easy manual inspection  
- compatibility with simple sensing‑pin arrays  
- deterministic decoding  

This document defines the row layout, bit meanings, opcode structure, operand selection, and branch encoding.

---

## 🎯 Design Principles

The encoding follows five core principles:

- **Fixed width** — every instruction occupies exactly one 12‑row frame  
- **Visible semantics** — operators can read tape by eye  
- **Mechanical tolerance** — wide row spacing reduces misreads  
- **Simple decoding** — relay logic can interpret rows directly  
- **Auditability** — instructions can be verified without tools  

---

## 🧱 12‑Row Layout Overview

Each instruction frame consists of 12 horizontal rows sensed simultaneously:

<pre>
Row  1 — Opcode bit 0
Row  2 — Opcode bit 1
Row  3 — Opcode bit 2
Row  4 — Opcode bit 3
Row  5 — Source register (2 bits)
Row  6 — Destination register (2 bits)
Row  7 — ALU mode / flags
Row  8 — Branch condition bit 0
Row  9 — Branch condition bit 1
Row 10 — Branch label bit 0
Row 11 — Branch label bit 1
Row 12 — Parity / error check
</pre>

Rows are grouped by function to simplify relay decoding.

---

## 🔢 Opcode Encoding (Rows 1–4)

The relay computer uses a 4‑bit opcode, allowing up to 16 instructions.

| Opcode | Meaning | Notes |
|--------|---------|-------|
| 0000 | NOP | No operation |
| 0001 | LOAD | Load register from tape constant or memory source |
| 0010 | STORE | Write register to output or memory |
| 0011 | ADD | ALU addition |
| 0100 | SUB | ALU subtraction |
| 0101 | CMP | Comparison / threshold check |
| 0110 | BR | Conditional branch |
| 0111 | HALT | Stop execution |
| 1000–1111 | Reserved | For future expansion |

Opcodes are intentionally sparse to reduce decoding complexity.

---

## 🧮 Register Selection (Rows 5–6)

Each register selector uses 2 bits:

<pre>
00 — R0
01 — R1
10 — R2
11 — R3
</pre>

- Row 5: Source register  
- Row 6: Destination register  

This allows simple plugboard routing and visible register activity.

---

## ⚙️ ALU Mode & Flags (Row 7)

Row 7 modifies ALU behavior:

- 0 — Normal mode  
- 1 — Flagged mode (saturating add, absolute value, compare‑only, etc.)

Flag semantics are defined in `architecture.md` and `commit-model.md`.

---

## 🔀 Branch Conditions (Rows 8–9)

Branches use a 2‑bit condition code:

| Bits | Condition |
|------|-----------|
| 00 | Always |
| 01 | If zero |
| 10 | If negative |
| 11 | If positive |

Branch evaluation occurs after COMPUTE and before COMMIT.

---

## 🏷 Branch Labels (Rows 10–11)

Two bits encode up to four branch labels:

<pre>
00 — Label A
01 — Label B
10 — Label C
11 — Label D
</pre>

Labels correspond to physical tape offsets defined in the plugboard configuration.

---

## 🛡 Parity / Error Check (Row 12)

Row 12 provides a simple parity bit:

- 0 — even parity  
- 1 — odd parity  

This allows the tape reader to detect:

- misalignment  
- torn tape  
- double‑punch errors  
- missing punches  

If parity fails, the machine halts before COMMIT.

---

## 📏 Physical Tape Format

- 12 rows per frame  
- 3–4 mm row spacing  
- 1.5–2 mm hole diameter  
- sprocket holes centered between frames  
- wide margins for manual handling  

Optimized for:

- low‑precision workshop punching  
- long‑term storage  
- humidity tolerance  
- easy visual inspection  

---

## 🧭 Example Instruction (Annotated)

**ADD R1 → R2**

<pre>
Row  1: 0
Row  2: 0
Row  3: 1
Row  4: 1      (Opcode 0011 = ADD)

Row  5: 01     (Source = R1)
Row  6: 10     (Destination = R2)

Row  7: 0      (Normal ALU mode)

Row  8: 00     (Branch condition = Always)
Row  9: 00

Row 10: 00     (Label A)
Row 11: 00

Row 12: 1      (Parity)
</pre>

This instruction:

1. Reads R1  
2. Adds it to R2  
3. Writes result to R2  
4. Always continues to next frame  

---

## 🧩 Extensibility

The encoding supports future expansion:

- additional opcodes  
- extended ALU modes  
- multi‑frame instructions  
- larger register banks  
- multi‑bit branch labels  

All extensions must remain compatible with:

- 12‑row sensing  
- mechanical tolerances  
- visible decoding  
- deterministic commit boundaries  

---

## 🎯 Summary

The 12‑row encoding provides:

- simplicity  
- mechanical robustness  
- clear operator visibility  
- deterministic decoding  
- compatibility with low‑precision workshops  

It is the foundation of the relay computer’s instruction model.


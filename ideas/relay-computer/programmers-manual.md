# Programmer’s Manual

This manual describes how to operate the relay computer from a programmer’s perspective. It covers job structure, tape preparation, plugboard routing, debugging, and verification. The goal is to make programming a physical, legible, and auditable process.

The relay computer is not programmed through abstraction — it is programmed through **visible state**, **mechanical sequencing**, and **explicit operator intent**.

---

## Programming Philosophy

Programming this machine is guided by three principles:

- **Transparency** — every step of execution is visible or audible  
- **Determinism** — no hidden state, no silent failures  
- **Physical workflow** — programming is a craft, not a keystroke  

A program is a *job*, and a job is a combination of:

- punched tape  
- plugboard routing  
- operator procedure  
- expected output  

All four must be correct for the job to run reliably.

---

## Job Structure Overview

A complete job consists of:

1. A punched tape containing instructions  
2. A plugboard configuration defining routing  
3. A job sheet describing inputs and expected outputs  
4. A verification procedure  

Jobs are stored physically and can be re‑run years later with no ambiguity.

---

## Tape Preparation

Tape is prepared using a hand punch or workshop punch press.

### Tape Layout

A job tape typically includes:

- **Leader section** (20–40 blank frames)  
- **Program section** (instructions)  
- **Data section** (constants or structured input)  
- **Trailer section** (blank frames for safe stopping)  

### Punching Procedure

1. Mark row positions using a template  
2. Punch opcode rows first  
3. Punch register selectors  
4. Punch branch rows  
5. Punch parity last  
6. Inspect every frame visually  

### Verification

Operators verify tape by:

- holding it to light  
- checking row alignment  
- confirming parity pattern  
- comparing against job sheet  

---

## Plugboard Configuration

The plugboard defines:

- register routing  
- ALU operand selection  
- output formatting  
- branch label mapping  
- optional job‑specific wiring  

### Plugboard Cards

Each job includes a plugboard card showing:

- socket map  
- wire colors  
- routing diagram  
- expected register usage  

### Installing a Configuration

1. Clear previous wiring  
2. Install patch cords according to the card  
3. Tug‑test each cord  
4. Verify against the diagram  
5. Perform a dry‑run with no tape loaded  

---

## Writing a Program

Programming is done at the instruction level using the 12‑row encoding.

### Common Instruction Patterns

**Load constant**  
LOAD → Rn, constant in data section

**Add two registers**  
ADD Rsrc → Rdst

**Conditional branch**  
BR cond → Label

**Store result**  
STORE Rn → output unit

### Example: Sum of Two Numbers

1. LOAD R0 with first number  
2. LOAD R1 with second number  
3. ADD R0 → R1  
4. STORE R1  
5. HALT  

This program fits on fewer than 20 frames.

---

## Debugging Workflow

Debugging is a physical process.

### Step 1: Observe the Machine

- Listen for relay chatter  
- Watch register indicators  
- Observe tape advance  
- Check ALU gear motion  

### Step 2: Single‑Step Mode

Operators may advance the machine one tick at a time:

- READ  
- DECODE  
- COMPUTE  
- WRITE  
- COMMIT  

This reveals exactly where a job misbehaves.

### Step 3: Check Plugboard

Most errors originate from:

- swapped patch cords  
- loose sockets  
- incorrect routing  

### Step 4: Inspect Tape

Look for:

- mispunched rows  
- torn edges  
- parity mismatches  
- off‑by‑one frame shifts  

### Step 5: Consult Job Sheet

Verify:

- expected register values  
- branch conditions  
- output format  

---

## Output Verification

Output is produced on a mechanical printer or typewheel.

Verification includes:

- comparing printed values to expected results  
- checking for misaligned digits  
- confirming no skipped lines  
- ensuring output matches job sheet format  

For civic workflows, output is archived with:

- job sheet  
- tape  
- plugboard card  
- operator signature  

---

## Best Practices

- Keep programs simple and explicit  
- Use comments on job sheets to explain intent  
- Avoid unnecessary branches  
- Prefer straight‑line code when possible  
- Test subroutines independently  
- Always verify tape before running a job  

---

## Summary

Programming the relay computer is a physical, transparent, and deterministic craft. A programmer must understand:

- tape encoding  
- plugboard routing  
- instruction sequencing  
- debugging through observation  

This manual provides the foundation for writing reliable, auditable jobs that can be executed decades after they are created.

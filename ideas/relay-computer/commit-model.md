# Relay Computer Commit Model

The commit model defines how the relay computer transitions from one stable machine state to the next. It ensures that every instruction executes deterministically, visibly, and atomically, with no partial updates or hidden intermediate states.

This model is the foundation of the machine’s reliability and civic trustworthiness.

---

## 🎯 Purpose of the Commit Model

The commit model guarantees:

- **atomicity** — each instruction either completes fully or not at all  
- **determinism** — no race conditions, no ambiguous states  
- **auditability** — operators can observe each phase  
- **mechanical safety** — relays and gears settle before state changes  
- **error containment** — faults cannot propagate silently  

It is the electromechanical equivalent of a transaction boundary.

---

## 🕰 The Five-Phase Instruction Cycle

Every instruction passes through five distinct phases:

1. **READ**  
2. **DECODE**  
3. **COMPUTE**  
4. **WRITE**  
5. **COMMIT**

Each phase is separated by a mechanical tick (1–10 Hz), ensuring that relays settle and mechanical elements reach stable positions.

---

## 1. READ Phase

The tape reader advances one frame (12 rows).  
Sensing pins detect:

- opcode  
- operand selectors  
- branch labels  
- flags  
- formatting instructions  

If misalignment or unreadable tape is detected, the machine raises an error and halts before proceeding.

**Outputs of this phase:**  
A stable set of sensed signals representing the next instruction.

---

## 2. DECODE Phase

Relay logic interprets the sensed signals:

- selects ALU mode  
- selects registers  
- activates branch comparators  
- configures output paths  
- prepares the plugboard-defined routing  

No state is changed during DECODE.  
This phase only configures the machine for the upcoming operation.

**Outputs of this phase:**  
A fully configured control state.

---

## 3. COMPUTE Phase

The ALU performs the requested operation:

- addition  
- subtraction  
- comparison  
- threshold check  
- pass-through  

Mechanical and relay elements settle into their final positions.  
No register is updated yet — this prevents partial writes.

**Outputs of this phase:**  
A stable result held in the ALU output latch.

---

## 4. WRITE Phase

The result is routed (via the plugboard) to the destination register’s **pre‑commit latch**.

This latch is separate from the register’s **committed state**, ensuring:

- no partial updates  
- no mid-cycle corruption  
- no visible flicker in register indicators  

**Outputs of this phase:**  
A pending update stored in pre‑commit latches.

---

## 5. COMMIT Phase

All pre‑commit latches transfer their values to the actual registers **simultaneously**.

This is the atomic boundary.

During COMMIT:

- registers update  
- flags update  
- branch decisions finalize  
- output formatting locks in  
- the next tape advance is authorized  

If an error flag is raised at any point, COMMIT is suppressed and the machine halts safely.

**Outputs of this phase:**  
A new stable machine state.

---

## 🧩 Why Atomicity Matters

Atomic commits prevent:

- half-written registers  
- ambiguous branch conditions  
- cascading relay chatter  
- inconsistent ALU states  
- operator confusion  

This is essential for civic workflows where correctness and auditability matter more than speed.

---

## 🔒 Error Handling in the Commit Model

Errors detected in any phase cause:

- immediate suppression of COMMIT  
- freeze of all pre‑commit latches  
- activation of the error relay  
- halt of tape advance  
- illumination of the error indicator  

Common errors include:

- tape misalignment  
- invalid opcode  
- ALU stall  
- mechanical obstruction  
- branch out-of-range  

The machine never commits a faulty state.

---

## 🛠 Mechanical Timing

The commit model relies on a low-frequency mechanical clock:

- escapement wheel  
- flywheel governor  
- or low-RPM motor  

This ensures:

- relays have time to settle  
- gears reach stable positions  
- sensing pins fully engage  
- operators can observe each phase  

The machine trades speed for reliability and transparency.

---

## 🔄 Branching and Commit Boundaries

Branches are evaluated **after** COMPUTE but **before** COMMIT.

This ensures:

- branch decisions are based on stable ALU results  
- no mid-cycle jumps  
- no partial state transitions  
- branch routines always begin at a clean boundary  

Branch labels are resolved via the plugboard and tape layout.

---

## 🧭 Summary

The commit model ensures that the relay computer:

- executes instructions safely  
- maintains deterministic behavior  
- exposes all state transitions  
- prevents partial or corrupted updates  
- remains auditable by operators  

It is the architectural heart of the machine’s reliability.


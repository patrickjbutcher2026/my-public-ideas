# Idea Card: Duty‑Cycle Logic

This idea card explores the concept of *duty‑cycle logic* — a technique where relays are energized only during specific phases of the instruction cycle rather than held continuously. The goal is to reduce power consumption, extend relay lifespan, and enable more complex logic without increasing the power envelope.

Duty‑cycle logic is optional and experimental. It is not part of the baseline architecture.

---

## Concept Overview

Traditional relay logic keeps certain relays energized for long periods. Duty‑cycle logic instead:

- pulses relays only when needed  
- uses latches to hold state  
- synchronizes switching with the machine’s five‑phase cycle  
- reduces coil heating and mechanical fatigue  

This approach borrows ideas from early telephony and electromechanical switching systems.

---

## Benefits

### Reduced Power Consumption
Relays draw current only during switching, not while holding.

### Extended Relay Lifespan
Less heat → less oxidation → fewer failures.

### Higher Logic Density
More logic can be added without exceeding the power envelope.

### Improved Timing Predictability
Switching occurs at known, synchronized boundaries.

---

## Drawbacks

### Increased Complexity
Requires additional latches or timing relays.

### Tighter Timing Requirements
Pulse width must exceed relay pull‑in time.

### More Sensitive to Ripple
Noisy power can cause missed pulses.

### Harder to Debug
State is held indirectly rather than by continuously energized relays.

---

## Implementation Approaches

### Approach 1: Phase‑Synchronized Pulsing
Relays receive power only during a specific phase (e.g., DECODE or COMMIT).

**Characteristics**
- Simple to implement  
- Works well with existing timing relays  
- Good for register selection and routing logic  

**Limitations**
- Requires precise phase boundaries  

---

### Approach 2: Pulse‑Latch Combinations
A short pulse sets or clears a latch relay.

**Characteristics**
- Very low power  
- State is stable even with power fluctuations  
- Ideal for control logic  

**Limitations**
- Requires additional latching relays  

---

### Approach 3: Mechanical Hold, Electrical Pulse
A relay pulse triggers a mechanical latch or detent.

**Characteristics**
- Extremely low power  
- Mechanically visible  
- Very long‑term stable  

**Limitations**
- More fabrication effort  
- Slower switching  

---

## Example Use Cases

### Register Selection
Instead of holding a selector relay energized, pulse it once to set a latch.

### ALU Mode Selection
ADD, SUB, COMP modes can be latched mechanically or electrically.

### Branch Condition Flags
Flags can be set by pulse and cleared at COMMIT.

### Tape Reader Control
Pulse‑driven escapement or stepper mechanisms reduce continuous load.

---

## Experimental Notes

- Pulse width must exceed relay pull‑in time (typically 10–20 ms).  
- Pulse amplitude must remain within the 12 V envelope.  
- Mechanical latches must be inspected regularly for wear.  
- Duty‑cycle logic interacts strongly with ripple tolerance.  

This technique is best explored on a prototype subsystem before integrating into the main machine.

---

## Summary

Duty‑cycle logic offers a promising path toward:

- lower power consumption  
- reduced relay wear  
- higher logic density  
- more efficient control structures  

It is an experimental enhancement that expands the relay computer’s design space without altering the core architecture.

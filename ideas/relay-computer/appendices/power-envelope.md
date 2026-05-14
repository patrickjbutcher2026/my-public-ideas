# Power Envelope

This appendix defines the acceptable power sources, electrical limits, and stability requirements for the relay computer. The machine is designed to operate on low‑voltage DC power that can be supplied by civic infrastructure, small workshops, or human‑powered generators.

The power envelope prioritizes safety, resilience, and compatibility with non‑specialized environments.

---

## Nominal Operating Voltage

### Standard Voltage
12 V DC

### Acceptable Range
10–14 V DC

### Notes
- Below 10 V: relay pull‑in becomes unreliable  
- Above 14 V: coil heating accelerates wear  
- The system is tolerant of slow voltage drift  

---

## Current Requirements

### Idle Current
0.3–0.6 A  
(Depends on relay count and indicator load)

### Active Current
1–3 A during switching bursts

### Peak Current
Up to 4 A momentarily  
(High‑density relay banks switching simultaneously)

---

## Ripple and Noise Tolerance

### Maximum Ripple
0.5 V peak‑to‑peak

### Acceptable Noise Sources
- hand‑crank generators  
- pedal generators  
- small solar‑buffered systems  
- battery banks  

### Unacceptable Noise
- unfiltered switching supplies  
- automotive alternators without smoothing  
- AC ripple above tolerance  

Ripple beyond limits causes relay chatter and timing irregularities.

---

## Approved Power Sources

### Human‑Powered
- hand‑crank generator  
- pedal generator  
- flywheel‑buffered crank systems  

### Renewable
- solar panel → charge controller → 12 V battery  
- micro‑hydro DC output  

### Conventional
- 12 V sealed lead‑acid battery  
- 12 V LiFePO₄ battery  
- regulated DC bench supply  

### Notes
The machine is intentionally compatible with low‑tech and off‑grid power.

---

## Power Conditioning

### Recommended Components
- smoothing capacitor (4700–10000 µF)  
- inline fuse (3–5 A)  
- reverse‑polarity protection diode  
- optional LC filter for noisy sources  

### Fuse Placement
As close to the power source as possible.

### Grounding
Chassis grounding recommended for metal frames.

---

## Power Distribution

### Wiring
- 16–18 AWG for main rails  
- 20–24 AWG for relay banks  

### Bus Bars
- copper or brass strips  
- insulated mounting standoffs  

### Distribution Layout
- horizontal rails for subsystem feeds  
- vertical rails for return paths  
- color‑coded for clarity  

---

## Battery Operation

### Supported Chemistries
- lead‑acid  
- AGM  
- LiFePO₄  

### Runtime
A 12 V, 7 Ah battery typically powers the machine for:
- 2–4 hours of active use  
- 6–10 hours of intermittent use  

### Charging
Use a regulated charger appropriate to the chemistry.

---

## Human‑Powered Operation

The machine is designed to run from human effort.

### Hand‑Crank
- 20–40 W sustained  
- suitable for short jobs  

### Pedal Generator
- 50–120 W sustained  
- suitable for long jobs  

### Flywheel Buffer
- smooths crank irregularities  
- reduces ripple  
- improves relay timing stability  

---

## Safety Considerations

### Electrical Safety
- always fuse the positive rail  
- avoid exposed terminals  
- disconnect power before servicing  

### Thermal Safety
- relays warm during extended operation  
- ensure ventilation around relay banks  

### Mechanical Safety
- secure generators to prevent tipping  
- avoid loose clothing near crank systems  

---

## Monitoring and Logging

Operators should periodically record:

- supply voltage  
- ripple level  
- battery charge state  
- generator performance  

These values are logged in the mechanics logbook.

---

## Summary

The power envelope ensures the relay computer remains:

- safe  
- resilient  
- compatible with low‑tech power  
- stable under varying conditions  

This appendix defines the electrical foundation that supports reliable operation in civic, workshop, and off‑grid environments.

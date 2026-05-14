# Tolerances and Mechanical Envelope

This document defines the mechanical, electrical, and environmental tolerances required for reliable operation of the relay computer. These tolerances are intentionally broad, allowing construction and maintenance using workshop‑level tools and salvageable components.

The goal is not precision engineering — it is predictable behavior under imperfect conditions.

---

## Design Philosophy

The tolerances are shaped by three principles:

- Robustness over precision  
- Inspectability over miniaturization  
- Graceful degradation rather than silent failure  

These principles ensure the relay computer remains a civic tool rather than a fragile instrument.

---

## Relay Tolerances

Relays define the system’s timing, reliability, and power envelope.

### Coil Resistance  
Acceptable range: ±15% of nominal value

### Pull‑in Voltage  
Acceptable range: 8–14 V  
Below 8 V: unreliable actuation  
Above 14 V: coil heating and premature wear

### Release Voltage  
Target: < 4 V

### Mechanical Travel  
Armature movement must remain within ±0.3 mm of nominal.

### Contact Pressure  
Acceptable range: 20–40 g

---

## Gear and Shaft Tolerances

### Gear Backlash  
Acceptable range: 0.2–0.6 mm

### Shaft Runout  
Maximum: 0.4 mm

### Bearing Play  
Acceptable: visible but not sloppy

---

## Tape Reader Tolerances

### Row Spacing  
Nominal: 3–4 mm  
Acceptable drift: ±0.5 mm

### Hole Diameter  
Nominal: 1.5–2 mm  
Acceptable drift: ±0.3 mm

### Tape Thickness  
Acceptable: 0.1–0.4 mm

### Sensing Pin Alignment  
Pins must align within ±0.4 mm across the 12‑row array.

---

## Electrical Tolerances

### Supply Voltage  
Nominal: 12 V DC  
Acceptable range: 10–14 V

### Ripple  
Maximum: 0.5 V peak‑to‑peak

### Wiring Resistance  
Acceptable: up to 0.5 Ω per meter

---

## Environmental Envelope

### Temperature  
Operational: 0–40°C  
Storage: –10–50°C

### Humidity  
Operational: 10–80%  
Condensation must be avoided.

### Dust  
Moderate dust is acceptable with periodic cleaning.

---

## Drift and Maintenance

All tolerances assume regular maintenance:

- contact cleaning  
- lubrication of gears  
- inspection of tape path  
- relay alignment checks  
- coil resistance measurement  

Maintenance intervals are defined in the mechanics logbook.

---

## Graceful Degradation

The relay computer is designed to fail audibly and visibly when tolerances are exceeded:

- relay chatter  
- misaligned tape sensing  
- ALU stalls  
- timing irregularities  
- increased power draw  

These symptoms allow operators to intervene before data corruption occurs.

---

## Summary

The tolerances defined here ensure the relay computer remains:

- buildable in small workshops  
- maintainable by trained operators  
- resilient to drift and wear  
- predictable under imperfect conditions  

This tolerance envelope is a core part of the machine’s long‑term civic reliability.

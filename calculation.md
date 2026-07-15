# Two-Stage CMOS Operational Amplifier Design Calculations

## Design Specifications

| Parameter | Value |
|-----------|-------|
| V<sub>DD</sub> | +2.5 V |
| V<sub>SS</sub> | -2.5 V |
| Supply Voltage | 5 V |
| DC Gain (Target) | ≥ 80 dB |
| Unity Gain Bandwidth | 10 MHz |
| Phase Margin | 60° |
| Slew Rate | 10 V/µs |
| Load Capacitance (C<sub>L</sub>) | 10 pF |

---

# Technology Parameters

## NMOS

V<sub>TN</sub> = 0.7 V

K<sub>n</sub>′ = 500 µA/V²

λ<sub>n</sub> = 0.02 V<sup>-1</sup>

---

## PMOS

|V<sub>TP</sub>| = 0.7 V

K<sub>p</sub>′ = 250 µA/V²

λ<sub>p</sub> = 0.02 V<sup>-1</sup>

---

# Step 1: Compensation Capacitor

A commonly used design guideline is

**C<sub>C</sub> ≈ 0.3 C<sub>L</sub>**

C<sub>C</sub> = 0.3 × 10 pF

> **C<sub>C</sub> = 3 pF**

---

# Step 2: Tail Current

The slew rate is

**SR = I<sub>5</sub> / C<sub>C</sub>**

Therefore

I<sub>5</sub> = SR × C<sub>C</sub>

= 10 × 10⁶ × 3 × 10<sup>-12</sup>

> **I<sub>5</sub> = 30 µA**

---

# Step 3: Differential Pair Current

Current divides equally.

**I<sub>D1</sub> = I<sub>D2</sub> = I<sub>5</sub> / 2**

> **I<sub>D1</sub> = I<sub>D2</sub> = 15 µA**

---

# Step 4: Input Stage Transconductance

Unity Gain Bandwidth

**UGB = g<sub>m1</sub> / (2π C<sub>C</sub>)**

Therefore

g<sub>m1</sub> = 2π(10 MHz)(3 pF)

> **g<sub>m1</sub> = 188.5 µS**

---

# Step 5: Overdrive Voltage of M1

Using

**g<sub>m</sub> = 2I<sub>D</sub> / V<sub>OV</sub>**

Therefore

V<sub>OV1</sub> = 2I<sub>D</sub> / g<sub>m1</sub>

= 30 µA / 188.5 µS

> **V<sub>OV1</sub> = 0.159 V**

---

# Step 6: Aspect Ratio of M1 and M2

MOS saturation equation

**I<sub>D</sub> = ½ K<sub>n</sub>′ (W/L) V<sub>OV</sub>²**

Therefore

W/L = 2I<sub>D</sub> / (K<sub>n</sub>′ V<sub>OV</sub>²)

Substituting

W/L = 30 / [500(0.159)²]

> **W/L = 2.37**

---

# Step 7: Source Voltage of M1

V<sub>GS</sub> = V<sub>T</sub> + V<sub>OV</sub>

= 0.7 + 0.159

= 0.859 V

For

V<sub>CM</sub> = 0 V

V<sub>S</sub> = V<sub>CM</sub> − V<sub>GS</sub>

> **V<sub>S</sub> = -0.859 V**

---

# Step 8: PMOS Active Load (M3 & M4)

Current

I<sub>D</sub> = 15 µA

Choose

V<sub>OV</sub> = 0.2 V

W/L = 2I<sub>D</sub> / (K<sub>p</sub>′ V<sub>OV</sub>²)

= 30 / [250(0.2)²]

> **W/L = 3**

---

# Step 9: PMOS Gate Voltage

V<sub>SG</sub> = |V<sub>T</sub>| + V<sub>OV</sub>

= 0.7 + 0.2

= 0.9 V

Since

V<sub>S</sub> = 2.5 V

V<sub>G</sub> = 2.5 − 0.9

> **V<sub>G</sub> = 1.6 V**

---

# Step 10: Tail Current Source M5

Current

30 µA

Choose

V<sub>OV</sub> = 0.2 V

W/L = 60 / [500(0.2)²]

> **W/L = 3**

---

# Step 11: Bias Voltage of M5

V<sub>GS</sub> = 0.7 + 0.2

= 0.9 V

Since

V<sub>S</sub> = -2.5 V

V<sub>G</sub> = -2.5 + 0.9

> **V<sub>G</sub> = -1.6 V**

---

# Step 12: Second Stage Transconductance

For a phase margin of approximately 60°

**p<sub>2</sub> ≥ 2ω<sub>u</sub>**

Since

p<sub>2</sub> = g<sub>m6</sub> / (C<sub>C</sub> + C<sub>L</sub>)

and

ω<sub>u</sub> = g<sub>m1</sub> / C<sub>C</sub>

Therefore

g<sub>m6</sub> ≥ 2g<sub>m1</sub> [(C<sub>C</sub> + C<sub>L</sub>) / C<sub>C</sub>]

Substituting

C<sub>C</sub> = 3 pF

C<sub>L</sub> = 10 pF

g<sub>m6</sub> ≥ 8.67 g<sub>m1</sub>

Choose

> **g<sub>m6</sub> ≈ 9 g<sub>m1</sub>**

Therefore

> **g<sub>m6</sub> = 1.7 mS**

---

# Step 13: Current in Second Stage

Choose

> **I<sub>6</sub> = 70 µA**

---

# Step 14: Overdrive Voltage of M6

V<sub>OV6</sub> = 2I<sub>6</sub> / g<sub>m6</sub>

= 140 µA / 1.7 mS

> **V<sub>OV6</sub> = 82 mV**

---

# Step 15: Aspect Ratio of M6

W/L = 2I<sub>D</sub> / (K<sub>p</sub>′ V<sub>OV</sub>²)

= 140 / [250(0.082)²]

> **W/L ≈ 83**

---

# Step 16: Current Mirror M7

Choose

V<sub>OV</sub> = 0.2 V

Current

70 µA

W/L = 140 / [500(0.2)²]

> **W/L = 7**

---

# Step 17: Bias Transistor M8

Current

30 µA

V<sub>OV</sub> = 0.2 V

W/L = 60 / [500(0.2)²]

> **W/L = 3**

---

# Expected Performance

| Parameter | Expected |
|-----------|----------|
| DC Gain | 80–120 dB |
| Unity Gain Bandwidth | 10 MHz |
| Phase Margin | ≈60° |
| Slew Rate | 10 V/µs |
| Power Consumption | P = (V<sub>DD</sub> − V<sub>SS</sub>) I<sub>supply</sub> |
| Load Capacitance | 10 pF |
| Compensation Capacitor | 3 pF |

---

# Power Consumption

The total power consumed is

**P = (V<sub>DD</sub> − V<sub>SS</sub>) × I<sub>Supply</sub>**

For a measured supply current I<sub>Supply</sub>,

> **P = 5 × I<sub>Supply</sub>**

where I<sub>Supply</sub> is obtained from the LTspice DC operating point analysis.

---

# Simulation Summary

The designed two-stage CMOS operational amplifier is verified using:

- **DC Analysis**: Bias currents, node voltages, transistor saturation, and power consumption.
- **AC Analysis**: Open-loop gain, unity-gain bandwidth, and phase margin.
- **Transient Analysis**: Slew rate using a unity-gain voltage follower configuration.

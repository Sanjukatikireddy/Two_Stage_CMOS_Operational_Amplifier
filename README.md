# Two-Stage CMOS Operational Amplifier Design and Analysis

## Overview

This project presents the design and simulation of a two-stage CMOS operational amplifier using LTspice. The amplifier is designed using CMOS transistors with a PMOS differential active load, NMOS differential input pair, PMOS common-source second stage, and Miller compensation capacitor for frequency stability.

The objective is to design a stable, high-gain CMOS operational amplifier and evaluate its performance through DC, AC, and Transient analyses.

---

## Objectives

- Design a two-stage CMOS operational amplifier.
- Verify proper transistor biasing and saturation.
- Measure open-loop voltage gain.
- Determine unity-gain bandwidth (UGB).
- Evaluate phase margin for stability.
- Measure slew rate using transient response.
- Calculate power consumption.

---

## Design Specifications

| Parameter | Value |
|-----------|-------|
| Supply Voltage | ±2.5 V |
| Load Capacitance (CL) | 10 pF |
| Compensation Capacitor (Cc) | 3 pF |
| Unity-Gain Bandwidth | 10 MHz (Target) |
| Phase Margin | ≥60° |
| Slew Rate | 10 V/µs (Target) |

---

## Circuit Description

The operational amplifier consists of:

- NMOS differential input stage
- PMOS current mirror active load
- PMOS common-source second gain stage
- NMOS current source load
- NMOS current mirror bias network
- Miller compensation capacitor
- Load capacitor

---

# Simulation Methodology

## 1. DC Analysis

### Objective

- Verify correct biasing of the amplifier.
- Ensure all MOSFETs operate in saturation.
- Determine quiescent operating point.
- Calculate power consumption.

### Measurements

- Gate, drain, and source voltages
- Drain currents
- Operating region of each transistor
- Total supply current

### Power Consumption

\[
P=(V_{DD}-V_{SS})\times I_{Supply}
\]

---

## 2. AC Analysis

### Objective

Evaluate the small-signal frequency response.

### Parameters Measured

- Open-loop DC Gain
- Unity-Gain Bandwidth (UGB)
- Phase Margin

### Procedure

- Bias the amplifier at its operating point.
- Perform AC sweep analysis.
- Obtain Bode magnitude and phase plots.

### Results

- Open-loop Gain
- Unity-Gain Bandwidth
- Phase Margin

---

## 3. Transient Analysis

### Objective

Determine the large-signal response of the operational amplifier.

### Procedure

- Configure the amplifier as a unity-gain voltage follower.
- Apply a pulse input.
- Observe the output waveform.

### Parameter Measured

Slew Rate

\[
SR=\frac{\Delta V}{\Delta t}
\]

where

- ΔV = Change in output voltage
- Δt = Time taken during the linear region of transition

---

# Performance Parameters

- Open-loop Voltage Gain
- Unity-Gain Bandwidth
- Phase Margin
- Slew Rate
- Power Consumption

---

# Software Used

- LTspice XVII

---

# Applications

- Analog Integrated Circuits
- Signal Conditioning
- Data Acquisition Systems
- Sensor Interface Circuits
- Active Filters
- General Purpose Analog Signal Processing

---

## Conclusion

A two-stage CMOS operational amplifier was successfully designed and analyzed in LTspice. The circuit was evaluated using DC, AC, and transient analyses to verify proper biasing, open-loop gain, unity-gain bandwidth, phase margin, slew rate, and power consumption. The simulation results demonstrate the amplifier's stability and performance, making it suitable for low-power analog integrated circuit applications.

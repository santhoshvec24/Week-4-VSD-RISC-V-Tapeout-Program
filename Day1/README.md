# Day-1 Basics of NMOS Drain(id) Vs Drain-to-source Voltage(Vds)

A comprehensive guide to understanding CMOS transistor behavior, circuit analysis, and practical SPICE simulation using Sky130 technology.

---

## Introduction to Circuit Design & SPICE Simulations

**Why SPICE Simulations Are Important**
SPICE simulations are a vital tool for designing and analyzing electronic circuits before building physical prototypes. They allow engineers to:

- Predict circuit behavior accurately.
- Identify potential design flaws early.
- Optimize performance without costly or time-consuming hardware.

SPICE supports analog, digital, and mixed-signal circuits, providing insights into voltage, current, power, and signal behavior under different operating conditions.

---

## Overview

This workshop provides an introduction to CMOS transistor operation, SPICE simulation, and characterization of Sky130 devices.
CMOS design depends on NMOS and PMOS transistors operating together to form logic gates.
Understanding their electrical properties is the foundation for analyzing circuit behavior.
You will learn:
- How NMOS transistors respond to different Vgs and Vds conditions.
- How to simulate transistor behavior using SPICE.
- How delay and timing are measured and analyzed in real integrated circuits.

---

## Understanding the NMOS Transistor

An n-Channel MOSFET (NMOS) has four main parts:
**Source & Drain**: Two heavily doped n⁺ regions that let electrons flow when the transistor is on.
**Gate**: The control terminal, usually made of polycrystalline silicon, where the input voltage is applied to turn the device on or off.
**Gate Oxide**: A very thin insulating layer (SiO₂) between the gate and the substrate. It allows the gate to control the channel with an electric field, without any DC current flowing.
**Body (B)**: The p-type substrate that forms the base of the transistor. It affects the transistor’s threshold voltage and overall behavior.

---

## Why SPICE Is Important in Circuit Design

In modern VLSI and analog design, even small mistakes can become very costly once a chip is fabricated. Since manufacturing an IC is expensive, SPICE simulations are essential tools that help designers:
- Test circuits virtually before building hardware.
- Verify the functionality of individual components, like logic gates or amplifiers.
- Analyze performance parameters, including delay, power consumption, and gain.
- Catch design flaws early, saving both time and money.
- Optimize device sizes (W/L ratios) to achieve better performance and lower power usage.

In short, SPICE acts as a bridge between theoretical designs and real hardware, allowing engineers to ensure their circuits will work correctly before fabrication.

---

## Role of SPICE in Circuit Design

SPICE (Simulation Program with Integrated Circuit Emphasis) allows designers to **accurately model and analyze circuit behavior before fabrication**, helping reduce errors and optimize performance.

| Function             | Benefit                               |
|----------------------|--------------------------------------|
| Functional Verification | Ensures logic correctness             |
| Timing Analysis        | Measures propagation delays          |
| Power Estimation       | Calculates static and dynamic power  |
| Design Optimization    | Adjusts transistor sizing and topology |

---

## Delay Modeling and Analysis

### Understanding Delay in Digital Circuits

In digital circuits, delay refers to the time it takes for an output to respond after an input changes.

Accurate delay modeling is crucial to ensure that signals arrive at all parts of the chip at the right time, preventing setup and hold violations and ensuring reliable circuit operation.

--- 

## Threshold Voltage with Positive Substrate Bias

In an n-channel MOSFET, applying a positive voltage to the substrate (body) widens the depletion region. This means a higher gate voltage is needed to create strong inversion in the channel. As a result, the threshold voltage increases compared to the case with zero substrate bias. This phenomenon is known as the body effect.

**Some Important Terms**

**Strong Inversion:**
Strong inversion occurs when the gate voltage exceeds the threshold voltage. In this state, a large number of electrons accumulate under the gate oxide, forming a conducting n-channel. This allows significant current to flow from the source to the drain.

**Subthreshold Conduction:**
Subthreshold conduction happens when a MOSFET leaks a small current even if the gate voltage is below the threshold voltage. This is due to the movement of minority carriers across the channel. The current increases exponentially as the gate voltage approaches the threshold.


---

## Cell Delay Dependency
In digital timing analysis, cell delay is not a fixed number.
The delay of a logic cell depends mainly on two factors:

**Input Slew:** The rate at which the input signal changes (transition time).
Slower slews cause longer delays.
**Output Load:** The capacitive load driven by the output.
Larger loads require more time to charge/discharge, increasing delay.

---


**Output Capacitance Formula**

C_total(G1) = C_out(G1) + Σ C_in(connected gates) + Σ C_wire








### Installation

#### Clone the workshop repository:
```bash
git clone https://github.com/kunalg123/sky130CircuitDesignWorkshop.git
cd sky130CircuitDesignWorkshop
cd design
```
<img width="733" height="509" alt="image" src="https://github.com/user-attachments/assets/f1fef053-c169-4285-9be8-5e3ab3f2028c" />

**Install ngspice (open-source SPICE simulator):**
```bash
sudo apt-get update
sudo apt-get install ngspice
```

#### Running Your First Simulation
**Execute a SPICE Netlist:**
```bash
ngspice day1_nfet_idvds_L2_W5.spice
```
**Generate Plots and for Saving Waveform Data**
```bash
plot -vdd#branch
write output.raw
wrdata output.csv -vdd
quit
less output.csv

```
<img width="698" height="615" alt="Screenshot from 2025-10-17 19-40-47" src="https://github.com/user-attachments/assets/60579b30-e904-4373-b722-e74ef3f76af5" />

at design directory

```bash
vim day1_nfet_idvds_L2_W5.spice
```
<img width="895" height="727" alt="image" src="https://github.com/user-attachments/assets/7fb26dca-a288-4741-a8f9-bc9c423ec8d7" />



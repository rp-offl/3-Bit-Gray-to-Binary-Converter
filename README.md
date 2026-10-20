# 3-Bit-Gray-to-Binary-Converter

# Design of a 3-Bit Gray-to-Binary Converter

## Overview

This project involves the design and transistor-level implementation of a **3-bit Gray-to-Binary converter** using Cadence Virtuoso as part of the Digital VLSI Design coursework at IIIT Delhi.

Gray code is a binary numeral system in which two consecutive values differ by only one bit. It is commonly used in digital systems to minimize transition errors. This project implements the conversion from 3-bit Gray code to its corresponding binary representation using combinational logic and CMOS circuitry.

## Objectives

- Design the combinational logic for a 3-bit Gray-to-Binary converter.
- Implement the design using CMOS transistor-level schematics in Cadence Virtuoso.
- Develop the corresponding physical layout with attention to transistor sizing and diffusion sharing.
- Verify functional correctness using exhaustive testing of all 8 possible input combinations.
- Characterize propagation delay, dynamic power, and leakage across different process corners.

## Gray-to-Binary Conversion Logic

Let the 3-bit Gray code input be (G2 G1 G0) and the binary output be (B2 B1 B0).

The conversion follows these equations:

- (B2 = G2)
- (B1 = B2 ⊕ G1)
- (B0 = B1 ⊕ G0)

Here, ⊕ denotes the XOR operation.

The most significant binary bit is identical to the most significant Gray bit. Each subsequent binary bit is obtained by XORing the previous binary bit with the corresponding Gray bit.

## Truth Table

| Gray Input | Binary Output |
|:---:|:---:|
| 000 | 000 |
| 001 | 001 |
| 010 | 011 |
| 011 | 010 |
| 100 | 111 |
| 101 | 110 |
| 110 | 100 |
| 111 | 101 |

All eight input combinations are used to verify the correctness of the conversion logic.

## Tools and Technologies

- **Cadence Virtuoso** — schematic design and physical layout
- **CMOS transistor-level design** — implementation of combinational logic
- **SPICE-based simulation** — circuit verification and performance characterization

## Design and Verification Workflow

1. **Logic design:** Derive the Boolean equations and truth table for the converter.
2. **Schematic implementation:** Build the circuit using CMOS transistor-level logic.
3. **Functional verification:** Test all eight input combinations against the expected truth table.
4. **Physical layout:** Create the layout while considering transistor placement, diffusion sharing, routing, and parasitic capacitances.
5. **Post-layout analysis:** Evaluate circuit performance with parasitic effects included.
6. **Performance characterization:** Measure propagation delay, dynamic power, and leakage across the specified process corners.

## Performance Specifications

The design is evaluated against the following coursework requirements.

| Parameter | TT Corner | SS Corner | FF Corner |
|---|---|---|---|
| Maximum propagation delay | ≤ 250 ps | ≤ 400 ps | Characterize minimum delay |
| Rise/fall delay skew | ≤ 60 ps | — | — |
| Output load capacitance | 15 fF | 15 fF | 15 fF |

Propagation delays are measured from the 50% input transition point to the 50% output transition point.

### Power Requirements

Average dynamic power is evaluated at **100 MHz** under the TT process corner.

| Circuit | Maximum Dynamic Power |
|---|---:|
| Binary-to-Gray (B2G) | 25 µW |
| Gray-to-Binary (G2B) | 35 µW |

Leakage power is also characterized and reported.

*Note: The B2G specifications are included for reference if the complementary converter is also implemented as part of the coursework.*

## Current Status

**In Progress**

The project is being developed in Cadence Virtuoso. Schematic implementation, layout development, functional verification, and timing and power characterization are carried out as part of the design workflow.

Measured performance results will be added after simulation and verification are complete.

## Learning Outcomes

- Understanding Gray code and binary code conversion.
- Designing XOR-based combinational logic.
- Implementing CMOS circuits at the transistor level.
- Understanding physical layout considerations, including diffusion sharing and parasitic capacitance.
- Evaluating timing, power consumption, and process-corner variation in VLSI circuits.

## Author

Developed as part of the Digital VLSI Design coursework at IIIT Delhi.

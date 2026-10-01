# ECE298A: Design Proposal

**Team Members:** Ella Lewis, Qasim Ebsim  
**Date:** September 2026  

## **Proposal**
We propose a two-stage CMOS amplifier with a differential pair input, single-ended output, and a current mirror load.

## **Statement of Purpose**
The purpose of this 2-stage amplifier is to explore the world of signal amplification at the transistor level. Our goal is to maximize gain and bandwidth while maintaining stability with common-mode feedback (for differential input). 

We chose 2 stages to optimize gain and output swing. The first stage will focus on obtaining a high and stable gain, while the second stage will focus on adding to that gain and providing a high swing output. This is extremely challenging in a one-stage amplifier, hence the decision to utilize a two-stage architecture.

## **System Diagram**
*(Insert System Diagram Here)*

## **IO Pin Assignment Table (Tiny Tapeout Pins)**
| TT Pin Name | Amplifier Pin | Description |
| :--- | :--- | :--- |
| `ua[0]` | `V_inp` | Non-inverting analog input |
| `ua[1]` | `V_inn` | Inverting analog input |
| `ua[2]` | `V_out` | Single-ended analog output |
| `VAPWR` | `VDD_3V3` | 3.3V Analog Power Supply |
| `VGND` | `VSS` | Ground |

*(Note: The analog pins `ua[0]` through `ua[5]` are utilized for this design, and the project requires the 3.3V template to access `VAPWR`. No external bias voltage is required).*

## **Proposed Specifications**

Two-Stage CMOS Amplifier Configuration: Referring to Sedra & Smith 7th edition.

| Specification | Target Value |
| :--- | :--- |
| Open-Loop DC Gain | > 60 dB |
| Gain Bandwidth Product (GBW) | > 5 MHz |
| Phase Margin | > 60° |
| Power Consumption | < 2 mW |
| Slew Rate | > 5 V/µs |
| Operating Voltage | 3.3V |
| Transistor Count | 8 - 12 |

## **Timeline for Completion**
1. **Topology Selection:** Evaluate baseline architectures.
2. **Specification Requirements:** Establish operational targets based on process capabilities.
3. **Schematic Design, Sizing, & Simulation:** Initial circuit capture and verification. -> **Optimization**
4. **1st Run of Layout:** Physical design implementation. -> **Simulation** (Extraction)
5. **Sizing & Schematic Level Improvement:** Address parasitic impacts. -> **Simulation -> Optimization**
6. **Optimization of VLSI Layout:** Final DRC, LVS, and area cleanup.

## **Who Does What**
* **In Group:** Topology decision, specification requirements.
* **Qasim:** Initial Xschem design, component sizing, and SPICE simulation/optimization.
* **Ella:** Magic VLSI layout execution, physical design optimization, and post-layout extraction.

## **References**
* Sedra, A. S., & Smith, K. C. Microelectronic Circuits (7th edition).
* GlobalFoundries GF180MCU PDK Documentation: https://gf180mcu-pdk.readthedocs.io/en/latest/
* Tiny Tapeout Analog Design Specifications: https://tinytapeout.com/specs/analog/
* Ngspice Circuit Simulator Reference Manual: https://ngspice.sourceforge.io/docs/ngspice-manual.pdf

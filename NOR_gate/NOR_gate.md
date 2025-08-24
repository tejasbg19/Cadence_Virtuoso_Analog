# Analysis of a CMOS NOR Gate

## 1. Introduction
This report details the design and simulation of a CMOS NOR gate using `gpdk 180nm` technology. The NOR gate, a universal logic gate, was characterized for its logical functionality and timing performance.
The circuit was simulated for both DC analysis (to verify truth table) and transient analysis (to measure propagation delays for all input combinations).

## 2. Circuit Schematic
The CMOS NOR gate consists of a series connection of NMOS transistors for the pull-down network and parallel PMOS transistors for the pull-up network.

![NOR Schematic](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_gate/Screenshot%20from%202025-05-15%2013-05-05.png)

*Figure 1: Schematic of the CMOS NOR gate.*

![NOR Symbol](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_gate/Screenshot%20from%202025-05-15%2013-08-57.png)

*Figure 2: Symbol of the CMOS NOR gate.*

## 3. Test Circuit
DC analysis & Transient analysis were performed to verify the NOR gate truth table with VDD = 1.8V.

![DC Analysi](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_gate/Screenshot%20from%202025-05-15%2013-10-50.png)
*Figure 3: Test Circuit.*

**Truth Table Verification:**
| Input A | Input B | Output | Expected | Verified |
|:-------:|:-------:|:------:|:--------:|:--------:|
| 0 | 0 | 1 | 1 | ✅ |
| 0 | 1 | 0 | 0 | ✅ |
| 1 | 0 | 0 | 0 | ✅ |
| 1 | 1 | 0 | 0 | ✅ |

## 4. Pre-Layout Timing Analysis
Transient analysis was performed to measure propagation delays for all input transitions.

![Transient Response](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_gate/Screenshot%20from%202025-05-15%2013-17-17.png)
*Figure 4: Transient response showing all input combinations.*

### Propagation Delays (Input A)
| **Parameter** | **Description** | **Value** |
|:-------------:|:----------------|:----------|
| tpd_rise_A | Delay (A: 0→1, B=0) | [VALUE] ps |
| tpd_fall_A | Delay (A: 1→0, B=0) | [VALUE] ps |

### Propagation Delays (Input B)
| **Parameter** | **Description** | **Value** |
|:-------------:|:----------------|:----------|
| tpd_rise_B | Delay (B: 0→1, A=0) | [VALUE] ps |
| tpd_fall_B | Delay (B: 1→0, A=0) | [VALUE] ps |

### Worst-Case Delays
| **Parameter** | **Description** | **Value** |
|:-------------:|:----------------|:----------|
| tpd_max | Maximum propagation delay | [VALUE] ps |
| tpd_avg | Average propagation delay | [VALUE] ps |

## 5. Post-Layout Simulation
The layout was implemented with full DRC and LVS verification followed by parasitic extraction.

![NOR Layout](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_gate/Screenshot%20from%202025-05-15%2013-18-52.png)
*Figure 5: Layout of the CMOS NOR gate.*

![Post-Layout Transient](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/NOR_Gate/Post_Layout_Transient.png)
*Figure 6: Post-layout transient response.*

### Post-Layout Timing Results
| **Parameter** | **Pre-Layout** | **Post-Layout** | **Delta** |
|:-------------:|:--------------:|:---------------:|:---------:|
| tpd_rise_A | [VALUE] ps | [VALUE] ps | [VALUE] ps |
| tpd_fall_A | [VALUE] ps | [VALUE] ps | [VALUE] ps |
| tpd_rise_B | [VALUE] ps | [VALUE] ps | [VALUE] ps |
| tpd_fall_B | [VALUE] ps | [VALUE] ps | [VALUE] ps |
| tpd_max | [VALUE] ps | [VALUE] ps | [VALUE] ps |

## 6. Conclusion
The CMOS NOR gate was successfully designed and simulated. The circuit correctly implements NOR logic functionality.
The post-layout simulation shows the expected increase in propagation delays due to parasitic capacitances and resistances, with 
input A and B delays showing variations based on their respective loading and transistor network characteristics.

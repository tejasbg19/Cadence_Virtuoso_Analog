# Analysis of a CMOS Inverter

## 1. Introduction
This report details the design and simulation of a standard CMOS inverter using `gpdk 180nm` technology.
The inverter was characterized for its key digital performance metrics, including propagation delay & trip point. The circuit was simulated for transient response & DC response to extract timing parameters and trip point respectively.

## 2. Circuit Schematic
The CMOS inverter consists of a PMOS pull-up transistor and an NMOS pull-down transistor connected in series between VDD and GND,
the width of NMOS is 850nm & that of PMOS is 1.7um adhering to the standard 2:1 ratio.

![Schematic](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2012-28-53.png)

*Figure 1: Schematic of the CMOS inverter.*

![Symbol](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2012-30-08.png)

*Figure 2: Symbol of the CMOS inverter.*

## 3. Pre-Layout Simulation
Transient analysis & DC analysis performed with a pulse input to measure propagation delay with VDD = 1.8V and a load capacitor C=100f F.

![Testbench](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2012-30-32.png)

*Figure 3: Testbench for transient simulation.*

![Transient](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2012-36-09.png)

*Figure 4: Transient response showing input and output waveforms.*

| **Parameter** | **Description** | **Value** |
|:-------------:|:----------------|:----------|
| Technology | gpdk 180nm | Wn = 850n, Wp = 1.7u |
| tpd_rise | Propagation Delay (Rise) | 470.05 ps |
| tpd_fall | Propagation Delay (Fall) | 333.84 ps |
| tpd | Average Propagation Delay | 401.95 ps |

## 4. Post-Layout Simulation
The physical layout of the inverter was implemented in Virtuoso Layout XL by instantiating devices from the schematic.

![Layout](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2013-00-20.png)

*Figure 5: Layout of the CMOS inverter.*

Physical Verification namely DRC (Design Rule Check) & LVS (Layout vs Schematic) were performed using Assura. 
After verification, RC parasitic extraction was performed using Quantus and post layout simulation was performed.

![Post-Layout](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/Inverter/Screenshot%20from%202025-05-16%2014-50-23.png)

*Figure 6: Post-layout transient response.*

| **Parameter** | **Description** | **Value** |
|:-------------:|:----------------|:----------|
| Technology | gpdk 180nm | Wn = 850n, Wp = 1.7u |
| tpd_rise | Post-Layout Delay (Rise) | 473.27 ps |
| tpd_fall | Post-Layout Delay (Fall) | 335.72 ps |
| tpd | Post-Layout Average Delay | 404.49 ps |

## 5. Conclusion
The CMOS inverter was successfully designed and simulated. The comparison between pre-layout and post-layout results demonstrates the impact of parasitic elements on circuit performance.

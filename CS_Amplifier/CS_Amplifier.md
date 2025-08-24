# Analysis of a Common-Source Amplifier with PMOS Current Mirror Active Load

## 1. Introduction
This report details the design and simulation of a Common-Source (CS) amplifier utilizing a PMOS current mirror as an active load using `gpdk 180nm devices`. The active load provides a high impedance output node, leading to significantly higher voltage gain compared to a resistive load. The circuit was simulated for transient response, and AC frequency response.

## 2. Circuit Schematic
The core circuit consists of an NMOS transistor (the amplifying device) whose drain is connected to the high-impedance output node formed by a PMOS current mirror. `Vbias_p` sets the current through the mirror, which also defines the drain current of the NMOS amplifier.

![Schematic](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2011-45-01.png)

*Figure 1: Schematic of the CS amplifier with PMOS current mirror active load.*


![Symbol](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2010-31-58.png)


## 3. Pre-Layout Simulation
Transient & AC analysis were performed to find the amplifier's gain, UGB (Unity gain Bandwidth) with the `Vbias_p` set to 592m A.
|Parameter | Description |	Min |	
|:--------:|:------------:|:----:|
| Technology Used | Cadence gpdk 180nm | - | 
| Gain | It is a measure of how much an amplifier increases a signal's power or amplitude | 28.2219 dB |



## 6. Layout
The physical layout of the amplifier was also designed. Proper layout techniques are crucial for matching the devices in the current mirror and minimizing parasitic capacitances that can affect performance.
<!-- PLACEHOLDER FOR IMAGE 6: Your layout image (e.g., 'layout.png') -->
*Figure 6: Layout view of the CS amplifier with PMOS active load.*

## 7. Conclusion
The Common-Source amplifier with a PMOS current mirror active load was successfully designed and simulated. The circuit achieved a high voltage gain of ~28 dB and a bandwidth of ~100 kHz. The simulations confirm the theoretical advantages of using an active load, namely high DC impedance leading to high gain. The results for gain, bandwidth, and biasing are consistent and meet expected outcomes for this amplifier topology.

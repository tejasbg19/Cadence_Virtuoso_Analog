# Analysis of a Common-Source Amplifier with PMOS Current Mirror Active Load

## 1. Introduction
This report details the design and simulation of a Common-Source (CS) amplifier utilizing a PMOS current mirror as an active load using `gpdk 180nm devices`. The active load provides a high impedance output node, leading to significantly higher voltage gain compared to a resistive load. The circuit was simulated for transient response, and AC frequency response.

## 2. Circuit Schematic
The core circuit consists of an NMOS transistor (the amplifying device) whose drain is connected to the high-impedance output node formed by a PMOS current mirror. `Vbias_p` sets the current through the mirror, which also defines the drain current of the NMOS amplifier.

![Schematic](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2011-45-01.png)

*Figure 1: Schematic of the CS amplifier with PMOS current mirror active load.*


The symbol view for this amplifier, used to create the test bench, is shown below.


![Symbol](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2010-31-58.png)

*Figure 2: Symbol of the CS amplifier with PMOS current mirror active load.*


## 3. Pre-Layout Simulation
Transient & AC analysis were performed to find the amplifier's gain, UGB (Unity gain Bandwidth) with the `Vbias_p` set to 592m A.




![Test Circuit](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2010-46-16.png)

*Figure 3: Test Circuit with all the appropriate biasing.*




![Transient Response](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2011-25-48.png)

*Figure 4: Transient Response.*




![AC Response](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2011-39-09.png)

*Figure 5: AC Response.*



|Parameter | Description |	Value |	
|:--------:|:------------:|:----:|
| Technology Used | Cadence gpdk 180nm | - | 
| Gain | It is a measure of how much an amplifier increases a signal's power or amplitude | 28.2219 dB |
| UGB | Unit Gain Bandwidth is the frequency at which an amplifier's open-loop gain drops to unity | 400.204 MHz |






## 6. Post Layout Simulation
The physical layout of the amplifier was implemented in Virtuoso Layout XL by instantiating devices from the schematic.

![Layout](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2012-17-03.png)

*Figure 6: Implemented Layout of the Amplifier.*

Physical Verification namely DRC (Design Rule Check) & LVS (Layout vs Schematic) were performed using Assura. After verification, RC parasitic extraction was performed using Quantus and post layout simulation was performed.


![pl_AC response](https://github.com/tejasbg19/Cadence_Virtuoso_Analog/blob/main/CS_Amplifier/Screenshot%20from%202025-05-15%2012-39-40.png)

*Figure 7: Post Layout AC response.*



|Parameter | Description |	Value |	
|:--------:|:------------:|:----:|
| Technology Used | Cadence gpdk 180nm | - | 
| Gain | It is a measure of how much an amplifier increases a signal's power or amplitude | 27.5896 dB |
| UGB | Unit Gain Bandwidth is the frequency at which an amplifier's open-loop gain drops to unity   (0 dB) | 396.974 MHz |







## 7. Conclusion
The Common-Source amplifier with a PMOS current mirror active load was successfully designed and simulated. The pre-layout gain & UGB were found to be 28.2219 dB & 400.204 MHz respectively while the post layout values were 27.5896 dB & 396.974 MHz respectively. The reduction in gain & UGB shows the impact of parasitic elements have on a design.  

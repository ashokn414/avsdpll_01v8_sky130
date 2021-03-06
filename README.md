## 1. Introduction to On-chip clock multiplier
This repository consists of simulation files and other related files on the On-chip clock multiplier using PLL (Fclkin—5MHz to 12MHz, Fclkout—40MHZ to 100MHZ at 1.8v) IP worked on in the VSD Online Internship.

This repo presents the design of On-chip clock multiplier using the Sky130 Open PDK provided by Google. 


## Table of Contents
- [1. Introduction to On-chip clock multiplier](#1-introduction-to-On-chip-clock-multiplier)
- [2. Theory](#2-Theory)
- [3. Sky130 PDK](#3-Sky130-PDK)
- [4. EDA Tools Used](#4-eda-tools-used)
- [5. Steps for simulation](#5-Steps-for-simulation)
- [6. Pre-layout Simulations](#6-Pre-layout-Simulations)
- [7. Post-layout Simulations](#7-Post-layout-Simulations)
- [8. Author](#8-Author)
- [9. Contributors](#9-Contributors)
- [10. Acknowledgments](#10-acknowledgments)
- [11. Contact Information -](#11-contact-information--)

## 2. Theory

A Phase Locked Loop is the most demanded in on-chip clock synthesis.PLL is used in the demodulation of FSK and FM and mainly as a Clock multiplier in microprocessors. It has been built as monolithic IC’s.

In view of its usefulness, the phase locked loop or PLL is found in many wireless, radio, and general electronic items from mobile phones to broadcast radios, televisions to Wi-Fi routers, walkie talkie radios to professional communications systems etc.

PLL can be used to generate new frequencies that are stable and are the multiples of the input reference frequency. It is mainly for the conversion of Low input frequency from Off-chip Peripherals to High frequency for the microprocessor.

The circuit simulated here uses PLL block to get desired frequency at it’s output (i.e., 8 times to that of input frequency provided).
This IP block can be used for clock distribution for processor chip.  

## 3. Sky130_PDK
sky130_fd_pr is the pdk file used in the simulations.The SKY130 is a mature 180nm-130nm hybrid technology originally developed internally by Cypress Semiconductor before being spun out into SkyWater Technology and made accessible to general industry. SkyWater and Google’s collaboration is now making this technology accessible to everyone!
more detailed info can be obtained at [skywater-pdk](https://github.com/google/skywater-pdk).

## 4. EDA Tools Used 
The design has been built using open-source EDA tools. The library used is sky130_fd_pr that consists of all primitive cells of sky130.

1. [Ngspice](http://ngspice.sourceforge.net/download.html)
2. [Magic](http://opencircuitdesign.com/magic/)

## 5. Steps for simulation
1. To make the simulation files work you need to include libraries of sky130_fd_pr that consists of primitive cells of sky130.
2. For this, you need to clone the repository of sky130_fd_pr into the working directory(i.e., clone the sky130_fd_pr into the directory in which your circuit files are present).
3. The git clone command for the sky130_fd_pr is 
   `git clone https://foss-eda-tools.googlesource.com/skywater-pdk/libs/sky130_fd_pr  `

For example, my circuit files are present in ashdir. then i need to clone sky130_fd_pr into ashdir (i.e., change directory to ashdir and then do the cloning).


## 6. Pre-layout Simulations
The PLL is designed with respect to the following Block-Diagram. All the resistors,capacitors and transistors are modeled from sky130_fd_pr.


</p>

![Alt Text](https://github.com/parasgidd/avsdpll_3v3/blob/master/images/block_diagram.png)

</p>

The simulation Waveform obtained for 5Mhz input clock is
</p>

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/images/ngspice_sim_5mhz.PNG)

</p>

Fig: Input-Output waveforms from Pre-layout Simulation. </p> 
Fin - Input Frequency. (Red) </p> 
up - Up signal (Blue) </p> 
down - Down signal (Yellow) </p> 
Vcp - Input Voltaage of VCO (Green) </p> 
fout - Output Frequency (Pink) </p> 
</p>



</p>
</p>

**Pre-layout Simulation Results**

</p>

| Input Frequency | Output Frequency |
| :---:  | :-: |
|5MHz|41.1MHz|
|10MHz|80.64MHz|
|12MHz|96.15MHz|

</p>
## 7.Post-layout Simulations

### A. Phase Frequency Detector
![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/pfd/pfd.PNG)

</p>

Fig: Layout of Phase Frequency Detector (PFD)
</p>
</p>

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/pfd/pfdw.PNG)

</p>
Fig: Input-Output waveforms of Phase Frequency Detector (PFD) </p>
     Inputs - fin (Input Frequency) &
              fvco_8 (Output Frequency divide by 8) </p> </p>
     Outputs - Up Signal &
               Down Signal         </p>
</p>
</p>

### B. Voltage Controlled Oscillator

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/vco/vco.PNG)

</p>
Fig: Layout of Voltage Controlled Oscillator (VCO).

</p>
</p>

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/vco/vcow.PNG)

</p>

Fig: Input-Output waveforms of Voltage Controlled Oscillator (VCO). </p>
Vin - Input Voltage </p>
Fout - Output Frequency
</p>
</p>

### C. Frequency Divider by 2

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/freqdiv2/freqdiv2.PNG)
</p>
Fig: Layout of Frequency Divider by 2. </p> 
</p>

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/freqdiv2/freqdiv2w.PNG)

</p>

Fig: Input-Output waveforms of Frequency Divider by 2. </p>

clk - Input Freqency. </p>
q - Output Freqency (Input Freq. by 2). </p>
</p>

### D. Frequency Divider by 8

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/freqdiv2/freqdiv8w.PNG)

</p>

Fig: Input-Output waveforms of Frequency Divider by 8. </p>

clk - Input Freqency. </p>
q - Output Freqency (Input Freq. by 8). </p>

</p>
</p>

### E. Phase lock Loop 

![Alt Text](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/post_layout_simulations/pll/pll.PNG)

</p>

</p>

Fig: Layout of Phase Lock Loop (Combining all the Sub-circuits of PLL). 

</p> 

</p>

## 8. Author
- Venkata Ashok Kumar Nallaballe, B.Tech.( ECE ), JNTUA College of Engineering Anantapur , ashoknallaballe@gmail.com

## 9. Contributors 

- **Venkata Ashok Kumar Nallaballe** 
- **Kunal Ghosh** 

## 10. Acknowledgments
- Kunal Ghosh, Co-founder VSD Corp. Pvt. Ltd.
- Paras Gidd - [On chip clock multiplier using pll(40-100Mhz), 180nm OSU](https://github.com/parasgidd/avsdpll_3v3)


## 11. Contact Information - 
 - Venkata Ashok Kumar Nallaballe, B.Tech.( ECE ), JNTUA College of Engineering Anantapur , ashoknallaballe@gmail.com
 - Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
 


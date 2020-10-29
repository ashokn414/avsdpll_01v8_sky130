## 1. Introduction to On-chip clock multiplier
This repository consists of simulation files and other related files on the On-chip clock multiplier using PLL (Fclkin—5MHz to 12MHz, Fclkout—40MHZ to 100MHZ at 1.8v) IP worked on in the VSD Online Internship.

The target is to design a On-chip clock multiplier using the Sky130 Open PDK provided by Google. The problem statement included in the file [Stage_1](https://github.com/ashokn414/avsdpll_01v8_sky130/blob/main/Documents/Stage_1.pdf) is presented to VSD Corporation Pvt. Ltd.
The On-chip clock multiplier is present in almost all synchronous processor chips.



## Table of Contents
- [1. Introduction to On-chip clock multiplier](#1-introduction-to-On-chip-clock-multiplier)
- [2. Theory](#2-Theory)
- [3. Sky130 PDK](#3-Sky130 PDK)
- [4. EDA Tools Used](#4-eda-tools-used)
- [5. Pre-layout Simulations](#5-Pre-layout-Simulations)
- [6. Author](#6-Author)
- [7. Contributors](#7-Contributors)
- [8. Acknowledgments](#8-acknowledgments)
- [9. Contact Information -](#9-contact-information--)

## 2. Theory

The clock generator is one of the most crucial part in synchronous processor & probably most susceptible after power lines which can cause failure of entire circuitry if not designed properly.

The phase locked loop or PLL is a circuit block that is widely used in radio frequency or wireless applications.

In view of its usefulness, the phase locked loop or PLL is found in many wireless, radio, and general electronic items from mobile phones to broadcast radios, televisions to Wi-Fi routers, walkie talkie radios to professional communications systems etc.

the circuit simulated here uses PLL block to get desired frequency at it’s output (which is 8 times to that of input frequency provided).
This IP block can be used for clock distribution for processor chip.  

## 3. Sky130 PDK
sky130_fd_pr

## 4. EDA Tools Used 
The design has been built using open-source EDA tools. The library used is sky130_fd_pr that consists of all primitive cells of sky130.

1. [Ngspice](http://ngspice.sourceforge.net/download.html)

## 5. Pre-layout Simulations
The complete circuit of PLL is built hierarchically using the following subcircuit blocks.


</p>

</p>

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
|5MHz|40MHz|
|10MHz|80.64MHz|
|12MHz|96.15MHz|

</p>

## 7. Author
- Venkata Ashok Kumar Nallaballe, B.Tech.( ECE ), JNTUA College of Engineering Anantapur , ashoknallaballe@gmail.com

## 8. Contributors 

- **Venkata Ashok Kumar Nallaballe** 
- **Kunal Ghosh** 

## 9. Acknowledgments
- Kunal Ghosh, Co-founder VSD Corp. Pvt. Ltd.
- Paras Gidd - [On chip clock multiplier using pll(40-100Mhz), 180nm OSU](https://github.com/neethujohny/avsdpll_3v3)


## 10. Contact Information - 
 - Venkata Ashok Kumar Nallaballe, B.Tech.( ECE ), JNTUA College of Engineering Anantapur , ashoknallaballe@gmail.com
 - Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalghosh@gmail.com
 



# DESIGNING A 10 BIT POTENTIOMETRIC DAC

This is the github repository which documents the design of a 10 Bit Potentiometric Digital to Analog Converter which makes use of SKY130 technology with the help of simulation tools like eSim and ngspice. 

## Table of Contents
- [What is a DAC?](#what-is-a-dac-)
  * [How do we implement a 10-bit DAC?](#how-do-we-implement-a-10-bit-dac-)
- [Pre Layout Design and Simulation](#pre-layout-design-and-simulation)
  * [The Switch](#the-switch)
  * [2-bit DAC](#2-bit-dac)
  * [3-bit DAC](#3-bit-dac)
  * [4-bit DAC](#4-bit-dac)
  * [5-bit DAC](#5-bit-dac)
  * [6-bit DAC](#6-bit-dac)
  * [7-bit DAC](#7-bit-dac)
  * [8-bit DAC](#8-bit-dac)
  * [9-bit DAC](#9-bit-dac)
  * [10-bit DAC](#10-bit-dac)
 - [Future Work](#future-work)
 - [Contributors](#contributors)
 - [Acknowledgements](#acknowledgements)




# What is a DAC?
DAC stands for Digital to Analog Converter, which as the name suggests is a system which converts a digital signal into an analog signal. Since the vast majority of signals in the real world are analog signals and digital systems can only work with digital signals as input, systems that can convert signals from analog to digital and vice versa become very crucial. After a digital system generates the output(which is a digital signal) it needs to be converted back to analog form to be readable or for further processing by analog systems, this is where we require a Digital to Analog converter(DAC).

## How do we implement a 10-bit DAC?
A 10-bit DAC takes a 10-bit digital word and converts it into an equivalent analog voltage wrt a reference voltage. A typical potentiometric DAC uses the concept of voltage divider which in the case of a 10-bit DAC means that the analog voltage range i.e. the Vref is equally divided into 2^10 voltage values which is achieved by connecting 2^10 equal resistors(R) in series and connecting taps across each R.
To achieve our aim of designing a 10-bit DAC we will be following a *Bottom Up Approach* by designing subcircuits in the following order - **Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and _10-bit_**


![109262054-e2fafd00-77ce-11eb-91ad-d75cca9803a2](https://user-images.githubusercontent.com/65102677/135520524-4a72338f-8afe-49f8-9ba0-75c280808e6f.png)

> Fig 1. Architecture of an n-bit DAC

# Pre Layout Design and Simulation

#### Tools used:
- [eSim](https://esim.fossee.in/downloads)
- [ngspice](http://ngspice.sourceforge.net/download.html)
- [Skywater 130nm PDK](https://github.com/google/skywater-pdk)

## The Switch


![switchSchematic](https://user-images.githubusercontent.com/65102677/135567712-e788946b-b3ec-42e0-8754-e960bac498a9.png)


> Fig.2  Schematic of the Switch circuit designed using eSim

![switch run](https://user-images.githubusercontent.com/65102677/135523593-192ac68a-36cd-4ea4-a13b-2839ee9fde3a.png)
> Fig. 3 Initializing transient analysis of the Switch circuit in pgspice 35

![t analysis of switch](https://user-images.githubusercontent.com/65102677/135523910-cf68c23a-2c86-410e-aefe-39a621a1012e.png)

> Fig. 4 Transient Analysis of the Switch circuit 

From the output graph for the Switch circuit we can observe that the circuit is working as intended.
-------------------------------------------------------
## 2-bit DAC

![2bitSchematic](https://user-images.githubusercontent.com/65102677/135568324-d2053d63-0af6-4590-934d-43720dd0f4b7.png)

> Fig. 5 Circuit schematic of a 2-bit DAC designed using eSim

![Annotation 2021-09-30 214319](https://user-images.githubusercontent.com/65102677/135525558-916c4632-62d5-4858-b0b6-1bfb2d10a934.png)
> Fig. 6 pgspice command window running transient analysis for the 2bit_DAC


![3bit](https://user-images.githubusercontent.com/65102677/135714391-b81fc832-5936-4fd7-abd9-637ca1e38a6c.png)

> Fig. 7 Transient analysis of the 2-bit DAC

Here we observe that the 2-bit didigtal input has been converted into its corresponding analog output.
We 2^2 = 4 steps in the analog output.

-------------------------------------------------------
## 3-bit DAC

![3bit](https://user-images.githubusercontent.com/65102677/135658426-11ff328b-c0b9-49e0-8ea1-f6a29e029bf6.png)
> Fig. 8 Circuit Schematic of a 3-bit DAC designed in eSim

![3bitspice](https://user-images.githubusercontent.com/65102677/135658471-47c21e9c-fa89-4639-a4ad-c00fab75f8bb.png)
> Fig. 9 Simulation of the 3-bit DAC in pgspice

![3bitoutput](https://user-images.githubusercontent.com/65102677/135658502-d233f94b-8c88-41f7-afd8-2ec36c6356df.png)
> Fig. 10 Transient analysis of the 3-bit DAC

Here we get 8 steps in the analog output as the system was given 3 digital input bits.

-------------------------------------------------------
## 4-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135658959-1b271e61-5553-467c-840a-c9e54a93529f.png)
> Fig. 11 Circuit Schematic of a 4-bit DAC designed in eSim 

![cktlevelsim](https://user-images.githubusercontent.com/65102677/135658986-4cd6d960-0758-49a0-870f-d71a7c600279.png)
> Fig. 12 Simulation of the 4-bit DAC in pgspice

![4bit](https://user-images.githubusercontent.com/65102677/135712512-19e10955-b2bb-4943-b6a2-a2b941d0e7cd.png)
> Fig. 13 Transient analysis of the 4-bit DAC

Here we get 16 steps in the analog output as the system was given 4 digital input bits.

-------------------------------------------------------
## 5-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135659268-dfa0271d-f84c-4c72-b1a8-25585224e368.png)
> Fig. 14 Circuit Schematic of a 5-bit DAC designed in eSim

![sim](https://user-images.githubusercontent.com/65102677/135659286-83074922-fb2c-4392-bf12-d0c2faef7b5c.png)
> Fig. 15 Simulation of the 5-bit DAC in pgspice

![image](https://user-images.githubusercontent.com/65102677/135712627-7d8920e9-1343-4f0c-b608-aaeea02bbef4.png)
> Fig. 16 Transient analysis of the 5-bit DAC

Here we get 32 steps in the analog output as the system was given 5 digital input bits.

-------------------------------------------------------
## 6-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135659651-328f9924-fc0b-4471-b013-6a9afb7a5f2f.png)
> Fig. 17 Circuit Schematic of a 6-bit DAC designed in eSim

![sim](https://user-images.githubusercontent.com/65102677/135659663-de78a334-080d-4efb-b487-51ed35bc16ed.png)
> Fig. 18 Simulation of the 6-bit DAC in pgspice

![6bit](https://user-images.githubusercontent.com/65102677/135712792-710cb06b-1769-4602-bbdc-ee98fd9eaa25.png)
> Fig. 19 Transient analysis of the 6-bit DAC

Here we get 64 steps in the analog output as the system was given 6 digital input bits.

-------------------------------------------------------
## 7-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135660194-d35ba46a-584c-479f-9c2d-26aee8ee0584.png)
> Fig. 20 Circuit Schematic of a 7-bit DAC designed in eSim

![sim](https://user-images.githubusercontent.com/65102677/135660274-00012481-9791-482e-b75c-9cfaa8d030c7.png)
> Fig. 21 Simulation of the 7-bit DAC in pgspice

![7bit](https://user-images.githubusercontent.com/65102677/135713096-74959a9d-fbc6-45a4-ad9b-a4fabaf2d1ba.png)
> Fig. 22 Transient analysis of the 7-bit DAC

Here we get 128 steps in the analog output as the system was given 7 digital input bits.

-------------------------------------------------------
## 8-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135660555-e852538d-9f1e-4702-9098-c7cda73c49d9.png)
> Fig. 23 Circuit Schematic of a 8-bit DAC designed in eSim

![sim](https://user-images.githubusercontent.com/65102677/135660614-f1db3175-9a36-4f19-8f66-f0d4a4d5c465.png)
> Fig. 24 Simulation of the 8-bit DAC in pgspice

![8bit](https://user-images.githubusercontent.com/65102677/135714159-04df1387-7fb5-4d76-ad26-d01c19114181.png)
> Fig. 25 Transient analysis of the 8-bit DAC

Here we get 256 steps in the analog output as the system was given 8 digital input bits.

-------------------------------------------------------
## 9-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135660878-f7f93f75-687b-47ba-860a-f12d83f95878.png)
> Fig. 26 Circuit Schematic of a 9-bit DAC designed in eSim

*Simulation in progress*

-------------------------------------------------------
# 10-bit DAC

![schematic](https://user-images.githubusercontent.com/65102677/135661186-935bdb41-0821-4d17-b4b8-f8abdc572849.png)
> Fig. 27 Circuit Schematic of a 10-bit DAC designed in eSim

*Simulation in progress*

## Future Work

Obtaining the simulations of 9-bit DAC and 10-bit DAC

## Contributors

- Bhaiswajyoti Lahon **BTech Electronics and Communications Engineering, North Eastern Hill University, Shillong** bhaiswajyoti@gmail.com

## Acknowledgements

- Kunal Ghosh, Co-Founder of VLSI System Design (VSD) Corp. Pvt. Ltd. - kunalghosh@gmail.com
- Sameer S Durgoji , B.Tech (Electronics and Communication Engineering), National Institute of Technology Karnataka - sameerdurgoji@gmail.com









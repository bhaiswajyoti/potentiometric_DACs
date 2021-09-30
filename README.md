# DESIGNING A 10 BIT POTENTIOMETRIC DAC
This is the github repository which documents the design of a 10 Bit Potentiometric Digital to Analog Converter which makes use of SKY130 technology with the help of simulation tools like eSim and ngspice. 

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


![Screenshot (921)](https://user-images.githubusercontent.com/65102677/135522570-e6f1b304-4ec3-48f2-8cd5-fd0b1d5721a0.png)

> Fig.2  Schematic of the Switch circuit designed using eSim

![switch run](https://user-images.githubusercontent.com/65102677/135523593-192ac68a-36cd-4ea4-a13b-2839ee9fde3a.png)
> Fig. 3 Initializing analysis of the Switch circuit in pgspice 35

![t analysis of switch](https://user-images.githubusercontent.com/65102677/135523910-cf68c23a-2c86-410e-aefe-39a621a1012e.png)

> Fig. 4 Transient Analysis of the Switch circuit 

From the output graph for the Switch circuit we can observe that the circuit is working as intended.

## 2-bit DAC

![2bit_DAC](https://user-images.githubusercontent.com/65102677/135524942-1a7914a7-6cf7-4fb9-8468-0f249eafda43.png)
> Fig. 5 Circuit schematic of a 2-bit DAC designed using eSim

![Annotation 2021-09-30 214319](https://user-images.githubusercontent.com/65102677/135525558-916c4632-62d5-4858-b0b6-1bfb2d10a934.png)
> Fig. 6 pgspice command window running transient analysis for the 2bit_DAC

![2bitdac](https://user-images.githubusercontent.com/65102677/135525864-c1c7d11c-637d-41fe-8736-c18cdfe19c8e.png)
> Fig. 7 Transient analysis of the 2-bit DAC











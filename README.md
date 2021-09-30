# DESIGNING A 10 BIT POTENTIOMETRIC DAC
This is the github repository which documents the design of a 10 Bit Potentiometric Digital to Analog Converter which makes use of SKY130 technology with the help of simulation tools like eSim and ngspice. 

## What is a DAC?
DAC stands for Digital to Analog Converter, which as the name suggests is a system which converts a digital signal into an analog signal. Since the vast majority of signals in the real world are analog signals and digital systems can only work with digital signals as input, systems that can convert signals from analog to digital and vice versa become very crucial. After a digital system generates the output(which is a digital signal) it needs to be converted back to analog form to be readable or for further processing by analog systems, this is where we require a Digital to Analog converter(DAC).

### How do we implement a 10-bit DAC?
A 10-bit DAC takes a 10-bit digital word and converts it into an equivalent analog voltage wrt a reference voltage. A typical potentiometric DAC uses the concept of voltage divider which in the case of a 10-bit DAC means that the analog voltage range i.e. the Vref is equally divided into 2^10 voltage values which is achieved by connecting 2^10 equal resistors(R) in series and connecting taps across each R.
To achieve our aim of designing a 10-bit DAC we will be following a *Bottom Up Approach* by designing subcircuits in the following order - **Switch, 2-bit, 3-bit, 4-bit, 5-bit, 6-bit, 7-bit, 8-bit, 9-bit and _10-bit_**


![109262054-e2fafd00-77ce-11eb-91ad-d75cca9803a2](https://user-images.githubusercontent.com/65102677/135520524-4a72338f-8afe-49f8-9ba0-75c280808e6f.png)

> Fig 1. Architecture of an n-bit DAC

## Pre Layout Design and Simulation

#### Tools used:
- [eSim](https://esim.fossee.in/downloads)
- [ngspice](http://ngspice.sourceforge.net/download.html)
- [Skywater 130nm PDK](https://github.com/google/skywater-pdk)

### The Switch


![Screenshot (921)](https://user-images.githubusercontent.com/65102677/135522570-e6f1b304-4ec3-48f2-8cd5-fd0b1d5721a0.png)

> Fig.2  Schematic of the Switch circuit designed using eSim







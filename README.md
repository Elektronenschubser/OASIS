# OASIS

## Introduction
*The future will show, if I bite more then I can chew...*

OASIS stands for "Open AFM / STM Integrated Solution"

The aim of this project is to provide electronic for Atomic Force Microscopes (AFM) and Scanning Tunnel Microscopes (STM). The development startet in septemper 2021. The standard licence will be a open source licence without the possibility of commercial selling the devices. That means everyone who can assemble a PCB with SMD parts, will be able to build his own hardware - and modify it if needed. But it will not be allowed to sell assembled boards or even devices without an extra, explicit permission.

Although this is something like a "hobby project" and should be affordable for nearly anyone who is interrested in probe scanning microscopy, the outcome should not make any compromises in respect to capability or precision. To achieve this, I use the pinciple of a chopper bike: Take only, what realy needed, but this must be the best. So there will not many of "nice to have" features.

It is not the aim to provide a "out of the box" solution. The idea is more to provide a start point everyone ca adopt and improve for his needs. 

## Modules
At this time I'm planning three modules. The size of every module as planned is (LxWxH) 154mmx214mmx42mm. All are powered by 24V DC. An aluminium case will be recommended, but there will also be files for a 3D printer solution.

The "bill of material" (BOM) costs, i.e. the price of all electronic parts without PCB, housing etc. will be - roughly estimated - far below 1000 EUR.

### Main Controller
The first module is the control-module. It will include an actual FPGA to do the work and a raspberry (-like) computer to provide the communication to the PC. Two ADCs with 20 bit solution and 500kSPS will be used for STM- and AFM-signals, respectively. PLL and Lock-In in the FPGA-Firmware will provide tapping and non-contact AFM modes and spectroscopy. For these applications the box will also provide a regulated sine modulator with arbitrary amplitudes from 1µV to 6.5V (VPP).

### High Voltage Amplifier
Often the voltages has to be amplified to drive piezo electric scanners (tubes etc.). There will be threedouble  channels, dedicated for the X, Y and Z-direction. "Double-channel" means that there will be two outputs for every channel whereas the second mirrors the voltage of the first into the opposite direction. The maximum output will be +/-150V. It will also be possible to mix the Z-signal into the X- and Y-channel which is needed for so called "four quadrand scanners".

It will also include the digital analog converters (DAC) who are driven b< the FPGA module in the control module. The resolution of the DACs will be 20 bit. For every channel there will be 4 gain stages (2, 5, 10 and 15) and an analog input of +/-10V which can be choosen instead of the build-in DAC. An optional selectable offset to the signal will allow to increase the effective resolution of the DAC. I.e. you can choose an offset of 100V and a gain of 2 in order to scan in the area from 80V to 120V with a nominal resolution of 38µV. This results in an effective increase of resolution of 3 bits. (And this can even be improved by modifing the hardware and change the resulting gain)

### Universal Piezo Motor Driver
(Compared to the  others this module has a low priority.) Many microscopes, especially which are dedicated to work in vacuum, uses piezo electric elements for a coarse positioning of the sample and the probe. For this you need low ("ramp") and high ("edge") currents to reload piezo electric actuators. 

In the limits of a common high voltage up to +/- 180V there will be eight channels where you can change independendly for every channel the low current by software up to 40mA in steps of 100µA. It should be possible to use this module without the main controller by RS485 and an easy protocol - we will see. For this application there will also be some TTL-signal inputs where the moves can be started.  

## The Software
(tbd)

## Project Plan / Time Schedule
(tbd)
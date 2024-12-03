# BRAINSBoard Results

<p align="center">
 <img src=/Results/Figures/ResultsExpSetup.png/>
</p>

## Key Elements of the BRAINSBoard:
### 1. Analog Stimulus Isolation

<p align="center">
 <img src=/Results/Figures/ResultsExpSetup.png/>
</p>

|                        |Arduino Microcontroller|   Octal Latches   |     SP3T Switches   |  Solid State Relays | Units |
|:----------------------:|:---------------------:|:-----------------:|:-------------------:|:-------------------:|:-----:|
| **Delay Time**         | Software Dependant    | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  |   μs  |
| **Leak Current**       | Pin 16 + 1 + 7 + 8    | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  |   μA  |
| **Output Capacitance** | Pin 16 + 1 + 9 + 10   | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  |   μA  |
| **Input Voltage**      | Pin 16 + 1 + 14 + 15  | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  | Units |
| **Output Voltage**     | Pin 16 + 2 + 5 + 6    | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  | Units |
| Channel **6**          | Pin 16 + 2 + 7 + 8    | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  | Units |
| Channel **7**          | Pin 16 + 2 + 9 + 10   | Electrode Channel |    Arduino Pins     | Pin 16 + 1 + 5 + 6  | Units |




### 2. Rapid and Customizable Switching and Configurations of electrode contacts

<p align="center">
 <img src=/Results/Figures/RapidSwitchingFigure.png/>
</p>

***(a):*** *tested average of stimulation at various frequencies to determine the maximum frequency one could switch between channels with a direct connection to a NIDAQ recording at 30MHz. The board was able to adequately switch between configurations that involved switching states of every pin from an active cathode-anode pairing to a ground state in clusters of four without leak due to Solid State Relay or Octal Latch Reconfiguration or On/Off times at ~ 600Hz.* ***(b):*** *switching times will increase for every new Octal Latch (1 for every 4 channels) required to set state configurations for electrode channels. Recorded duration of the Output Enable on the NIDAQ at 30MHz demonstrates that for one Octal Latch, activation time is between 133* $\tfrac{1}{3}\$ *μs to 166* $\tfrac{2}{3}$ *μs and each additional Octal Latch adds ~ 66* $\tfrac{2}{3}\$ *μs to set channel states on the side of the Arduino Pro Micro. Precise measurement of time taken is limited by the 30MHz sample rate* ***(c):*** *recording of Multichannel Monopolar 50µA Cathode Leading 500µs Biphasic Single Pulses rapidly switching active cathode channels at 500 Hz. Stimulation sent through an A-M 4100 Analog Isolated Stimulator through the BRAINSBoard with all 16 outputs connected through a 100kΩ resistor to a NIDAQ Board and a building ground. No leak current presents itself when every other channel is grounded and a single contact is activated.* ***(d):*** *attempted multipolar test with a single cathode and multiple anode channels in saline with 50µA Cathode Leading 500µs Biphasic Single Pulses with an AM4100 Analog Isolated Stimulator through the BRAINSBoard to a NeuroNexus A1x16 (50 µm spacing between contacts) Electrode Array.*

#### Problem 2:
 - Rapid switching has the following theoretical time limitations due to board components:

 - 

### 3. Programmability:

## $\textbf{\color{white}This work was supported by NIH NINDS project number 1R01NS120850}$

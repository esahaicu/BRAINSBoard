# BRAINSBoard Results

<p align="center">
 <img src=/Results/Figures/ResultsExpSetup.png/>
</p>

## Key Elements of the BRAINSBoard:
### 1. Analog Stimulus Isolation

<p align="center">
 <img src=/Results/Figures/ResultsExpSetup.png/>
</p>

<p align="center">
 <img src=/Results/Figures/datasheet2.PNG/>
</p>

#### Problem 1: Leak Current and Output Capacitance

 -
#### Solution 1: Replace the <a href="https://cdn1-originals.webdamdb.com/14154_151801265?cache=1732603283&response-content-disposition=inline;filename=PAA193.pdf&response-content-type=application/pdf&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cCo6Ly9jZG4xLW9yaWdpbmFscy53ZWJkYW1kYi5jb20vMTQxNTRfMTUxODAxMjY1P2NhY2hlPTE3MzI2MDMyODMmcmVzcG9uc2UtY29udGVudC1kaXNwb3NpdGlvbj1pbmxpbmU7ZmlsZW5hbWU9UEFBMTkzLnBkZiZyZXNwb25zZS1jb250ZW50LXR5cGU9YXBwbGljYXRpb24vcGRmIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoyMTQ3NDE0NDAwfX19XX0_&Signature=KEhrRK-vYwk0ggFpEj8wrtBzJmtt7BLaQpuE0VpQ6zIkfrLoIbx35HtgxQp~mzP1G8wXjwMnEd2zExPyTWqPD8bcKLJTfQP483ssKtQgMZSv9g4kMZWmTeWzq72~uDpBGg3QDFOSoxpoQ4pNKS8JEbIiLR73WmyYWHy~x8HXiKn1oemtWMO5ZJkIW832eBlLtIbZF6mad9GiruNMyseB5M5vAtnD5xpdgm85AQOtLEowx-~A6fRC1GCmJKfGsC2NgjsDT588YpRlWTskNJhZ7zaYhGDO9GeALtxS0ZmNQy8JBUkahIwGCS4s0QiuV7Lvj7qD-rCDa4SswuSvqyvkgw__&Key-Pair-Id=APKAI2ASI2IOLRFF2RHA">PAA193 SSR</a> with <a href="https://cdn1-originals.webdamdb.com/12956_135154079?cache=1729648393&response-content-disposition=inline;filename=OAA160.pdf&response-content-type=application/pdf&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cCo6Ly9jZG4xLW9yaWdpbmFscy53ZWJkYW1kYi5jb20vMTI5NTZfMTM1MTU0MDc5P2NhY2hlPTE3Mjk2NDgzOTMmcmVzcG9uc2UtY29udGVudC1kaXNwb3NpdGlvbj1pbmxpbmU7ZmlsZW5hbWU9T0FBMTYwLnBkZiZyZXNwb25zZS1jb250ZW50LXR5cGU9YXBwbGljYXRpb24vcGRmIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoyMTQ3NDE0NDAwfX19XX0_&Signature=AXHYEUwQeGlJv0wT-6YeKM1RikhenEa59iUFNI39tTOkFUg2SDUpqC-E0H8ncd0Q7HQ08yBqlckWgHi77eyu01f4YnqluGsyMgwveAA9lgVK35F8CKfdHTVbH9U3SGNk3P30u9mg-Cwjt3lLbItZ5srsjdkrtmY~ygdudVYNud--zzGRss3OerThwrDle2YjYWR0AnRQs9qA01ERjdj3iEWlwWsxjy~kbYyX732hxke7vOttaN5PPq~9jG1AofzusaQnYLKNld86RVlLb~SNYGWz9AfdbnLhnX-XlATFZXGDKhS-sPZHe1oXKVAZrJjDEzQASST77NQPldvNG~NaTg__&Key-Pair-Id=APKAI2ASI2IOLRFF2RHA">OAA160 SSR</a>



### 2. Rapid and Customizable Switching and Configurations of electrode contacts

<p align="center">
 <img src=/Results/Figures/RapidSwitchingFigure.png/>
</p>

***(a):*** *tested average of stimulation at various frequencies to determine the maximum frequency one could switch between channels with a direct connection to a NIDAQ recording at 30MHz. The board was able to adequately switch between configurations that involved switching states of every pin from an active cathode-anode pairing to a ground state in clusters of four without leak due to Solid State Relay or Octal Latch Reconfiguration or On/Off times at ~ 600Hz.* ***(b):*** *switching times will increase for every new Octal Latch (1 for every 4 channels) required to set state configurations for electrode channels. Recorded duration of the Output Enable on the NIDAQ at 30MHz demonstrates that for one Octal Latch, activation time is between 133* $\tfrac{1}{3}\$ *μs to 166* $\tfrac{2}{3}$ *μs and each additional Octal Latch adds ~ 66* $\tfrac{2}{3}\$ *μs to set channel states on the side of the Arduino Pro Micro. Precise measurement of time taken is limited by the 30MHz sample rate* ***(c):*** *recording of Multichannel Monopolar 50µA Cathode Leading 500µs Biphasic Single Pulses rapidly switching active cathode channels at 500 Hz. Stimulation sent through an A-M 4100 Analog Isolated Stimulator through the BRAINSBoard with all 16 outputs connected through a 100kΩ resistor to a NIDAQ Board and a building ground. No leak current presents itself when every other channel is grounded and a single contact is activated.* ***(d):*** *attempted multipolar test with a single cathode and multiple anode channels in saline with 50µA Cathode Leading 500µs Biphasic Single Pulses with an AM4100 Analog Isolated Stimulator through the BRAINSBoard to a NeuroNexus A1x16 (50 µm spacing between contacts) Electrode Array.*

**Rapid switching has the following theoretical time limitations due to board components beyond the Solid State Relays:**
<p align="center">
 <img src=/Results/Figures/datasheet1.PNG/>
</p>

*** *denotes dependancy on software efficiency and specific microcontroller used* 

#### Problem 2: LFP spike when Serial Commands sent
 - Put in a pic of noise from a recording?
#### Solution 2: USB Isolation
 - Talk about how it's done?

### 3. Programmability:

## $\textbf{\color{white}This work was supported by NIH NINDS project number 1R01NS120850}$

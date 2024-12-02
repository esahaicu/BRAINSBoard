# BRAINSBoard

<p align="center">
 <img src=images/BRAINSBoardFinalProfile.png/>
</p>

# Abstract

  **Objective:** Multipolar Intracranial Electrical Brain Stimulation (ICBS) is a promising method increasingly explored for use in both closed-loop neuromodulation experiments and clinical treatments for neurological diseases. Current tools for multipolar ICBS face several limitations that hinder exploratory research: high entry costs, lack of flexibility in managing different stimulation parameters and electrodes, absence of an open-source, customizable platform, and often an overabundance of features unnecessary for single-unit level exploratory research. These constraints limit the progress in understanding and applying multipolar ICBS effectively. To address these challenges, we developed the Bioelectric Router for Adaptive Isochronous Neuro Stimulation (BRAINS) Board.

  **Approach:** The BRAINS Board a cost-effective and customizable device designed to facilitate multipolar stimulation experiments across a 16-channel electrode array using common research electrode setups. The BRAINS Board interfaces with a microcontroller, allowing users to configure each channel for cathodal or anodal input, establish a grounded connection, or maintain a floating state. The design prioritizes ease of integration by leveraging standard tools like a microcontroller and an Analog Isolated Stimulator while providing options to customize setups according to experimental conditions. It also ensures output isolation, reduces noise, and supports remote configuration changes for rapid switching of electrode states. To test the efficacy of the board, there will be a series of tests run with 2 different stimulators with a fixed set of currents congruent with typical microcurrent brain stimulation. There will be 2 sets of bench tests: first with a direct connection to a DAQ system with current passing through 110KΩ resistors for all channels; next, a test through stimulation sent through contacts of a 16 channel electrode in saline and recordings through a Neuropixel. Once completed, monopolar, bipolar, and multipolar parameters will be tested in-vivo with stimulation and 3 Neuropixel recordings in V1.

  **Main Results:** The BRAINS Board, when delivering stimulation through a conventional isolated stimulator (A-M 4100), demonstrates no significant differences in Root Mean Square Error (RMSE) noise or signal-to-noise ratio compared to the baseline performance of the isolated stimulator alone. The board supports configuration changes at a rate of up to 600 Hz without introducing residual noise, enabling high-frequency switching necessary for temporally multiplexed multipolar stimulation.

  **Significance:** The BRAINS Board represents a significant advancement in exploratory brain stimulation research by providing a user-friendly, customizable, open source, and cost-effective tool capable of conducting sophisticated, reproducible, and finely controlled stimulation experiments. With its capacity for real-time information processing and efficient parameter exploration, the BRAINS Board is poised to enhance both exploratory research and clinical applications of closed-loop ICBS.

# Introduction

Intracranial electrical brain stimulation (EBS) is a cornerstone therapeutic approach in clinical neurology and neurosurgery, particularly for treating conditions like Parkinson's disease, obsessive compulsive disorder[1], [2], dystonia[3], and epilepsy[4]. Furthermore, microstimulation paradigms have been used for decades in animal research. Utilizing EBS with neural prosthetics has promise to improve the quality and efficacy of brain-machine interfaces[5]. Despite widespread clinical use and role in neuroscience research, our fundamental understanding of how EBS affects neural circuits remains surprisingly limited. Current clinical protocols rely heavily on trial-and-error programming approaches during and after electrode implantation stimulation parameters frequently require adjustment over multiple clinical visits to achieve optimal therapeutic effects [6], [7], [8].

While we know that EBS can activate varied neural elements - including somas, dendrites, and axons - the precise composition of recruited neural ensembles remains unclear[6], [7]. This knowledge gap is particularly evident in clinical settings, where stimulation parameters must often be modified empirically by clinicians during patient follow-up visits[8]. Recent advances in multipolar brain stimulation have shown promise [9] in providing more precise [10], [11] and efficient therapeutic outcomes [12]. Current FDA-approved devices typically offer unipolar, bipolar, and limited multipolar stimulation options (4-8 contacts), with clinicians generally exhausting unipolar configurations before exploring more complex stimulation patterns[6]. Research devices with more contacts....reference specific papers... However, investigating  advanced approaches, including multipolar stimulation, faces significant technical and practical barriers in most research settings. Traditional research tools for exploring multipolar stimulation, such as clinical neurostimulators or high-end research systems (e.g., Tucker-Davies STG5 Satellite, Intan headstages), are either prohibitively expensive, inflexible in their configuration, or excessive in their complexity for basic research applications [13].

The scientific community currently lacks access to flexible, open-source, cost-effective tools for exploring multipolar stimulation paradigms. Existing solutions often require substantial financial investment, offer limited customization options, and frequently include unnecessary features that complicate their use in fundamental research settings. These limitations have created a significant barrier to entry for researchers interested in exploring novel stimulation paradigms and understanding the basic principles of neural activation patterns.

To address these challenges, we developed a modular and readily reprogrammable interface - the Bioelectric Router for Adaptive Isochronous Neuro Stimulation (BRAINS) Board for control of electrical brain stimulation. This system enables rapid switching and multipolar stimulation while maintaining compatibility with existing monopolar and bipolar stimulation experimental frameworks. Our approach prioritizes accessibility, flexibility, and signal isolation while keeping costs aligned with standard experimental setups.   

# Hardware

The BRAINSBoard uses a custom designed PCB to ensure that:
 1) Output signal to the electrode array remains **isolated** with little to no leak or loss of current
 2) Channels can be set and changed **rapidly (~600Hz)**
 3) Channels can be controlled using any microcontroller and can be customizable

The BRAINSBoard is easy to plug into many up to 16-channel stimulation setups for experiments and can customizably recieve and communicate information to and from other devices in a setup. A current setup looks like:

<p align="center">
 <img src=/Hardware/images/BRAINSBoardSetup.png>
</p>

If you want to BUILD YOUR OWN:
Use the <a href="/Hardware/BRAINSBoard%20Production%20Files">following folder</a>, which has everything required to submit the PCB to a manufacturer to be processed.

For a more in-depth explanation of the schematic and setup of this board, <a href="/Hardware">look here</a>!

# Software

We have designed this to be compatible and easily programmed by any microcontroller. We have prewritten code to pair with an Arduino Pro Micro with the following configuration:

<p align="center">
 <img src=images/BB2ProMicro_bb.png/>
</p>

Use the <a href="/Software/arduinoProMicroBRAINSBoard">following folder</a>, which has code that can be downloaded onto an Arduino Pro Micro.

The guide and description on how to easily control the board is <a href="/Software">here</a>!

# General Results

Hey! General results that will be good to prominently display as well as maybe setup pics could be great!

# Future Directions

Look forward <a href=https://github.com/esahaicu/BRAINSBoard/>HERE</a> for more updates on the BRAINSBoard that are based on, but not limited to, the following key improvements and a future timeline:

### By January 2025 - BRAINSBoard V3

1. Switching the <a href="https://cdn1-originals.webdamdb.com/14154_151801265?cache=1732603283&response-content-disposition=inline;filename=PAA193.pdf&response-content-type=application/pdf&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cCo6Ly9jZG4xLW9yaWdpbmFscy53ZWJkYW1kYi5jb20vMTQxNTRfMTUxODAxMjY1P2NhY2hlPTE3MzI2MDMyODMmcmVzcG9uc2UtY29udGVudC1kaXNwb3NpdGlvbj1pbmxpbmU7ZmlsZW5hbWU9UEFBMTkzLnBkZiZyZXNwb25zZS1jb250ZW50LXR5cGU9YXBwbGljYXRpb24vcGRmIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoyMTQ3NDE0NDAwfX19XX0_&Signature=KEhrRK-vYwk0ggFpEj8wrtBzJmtt7BLaQpuE0VpQ6zIkfrLoIbx35HtgxQp~mzP1G8wXjwMnEd2zExPyTWqPD8bcKLJTfQP483ssKtQgMZSv9g4kMZWmTeWzq72~uDpBGg3QDFOSoxpoQ4pNKS8JEbIiLR73WmyYWHy~x8HXiKn1oemtWMO5ZJkIW832eBlLtIbZF6mad9GiruNMyseB5M5vAtnD5xpdgm85AQOtLEowx-~A6fRC1GCmJKfGsC2NgjsDT588YpRlWTskNJhZ7zaYhGDO9GeALtxS0ZmNQy8JBUkahIwGCS4s0QiuV7Lvj7qD-rCDa4SswuSvqyvkgw__&Key-Pair-Id=APKAI2ASI2IOLRFF2RHA">current Solid State Relay</a> to a <a href="https://cdn1-originals.webdamdb.com/12956_135154079?cache=1729648393&response-content-disposition=inline;filename=OAA160.pdf&response-content-type=application/pdf&Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cCo6Ly9jZG4xLW9yaWdpbmFscy53ZWJkYW1kYi5jb20vMTI5NTZfMTM1MTU0MDc5P2NhY2hlPTE3Mjk2NDgzOTMmcmVzcG9uc2UtY29udGVudC1kaXNwb3NpdGlvbj1pbmxpbmU7ZmlsZW5hbWU9T0FBMTYwLnBkZiZyZXNwb25zZS1jb250ZW50LXR5cGU9YXBwbGljYXRpb24vcGRmIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoyMTQ3NDE0NDAwfX19XX0_&Signature=AXHYEUwQeGlJv0wT-6YeKM1RikhenEa59iUFNI39tTOkFUg2SDUpqC-E0H8ncd0Q7HQ08yBqlckWgHi77eyu01f4YnqluGsyMgwveAA9lgVK35F8CKfdHTVbH9U3SGNk3P30u9mg-Cwjt3lLbItZ5srsjdkrtmY~ygdudVYNud--zzGRss3OerThwrDle2YjYWR0AnRQs9qA01ERjdj3iEWlwWsxjy~kbYyX732hxke7vOttaN5PPq~9jG1AofzusaQnYLKNld86RVlLb~SNYGWz9AfdbnLhnX-XlATFZXGDKhS-sPZHe1oXKVAZrJjDEzQASST77NQPldvNG~NaTg__&Key-Pair-Id=APKAI2ASI2IOLRFF2RHA">better Solid State Relay</a> for microstimulation with the current devices.
  - The current SSR has two key issues noted in this version 2 of the BRAINSBoard:
    - ***10µA leak current*** on the isolated channels that is solved in the <a href="https://github.com/esahaicu/BRAINSBoard/Results">results section </a> under issue #1 **vs** a ***250nA leak current*** in the newer Solid State Relay
    - ***50pF output capacitance*** on the isolated channels that is solved in the <a href="https://github.com/esahaicu/BRAINSBoard/Results">results section </a> under issue #1 **vs** a ***5pF leak current*** in the newer Solid State Relay
  - The goal is to remove a notable reduction in the signal provided due to leak and capacitance issues. Both a theoretical demonstration of the issue and intial results presenting the benefits of the new Solid State Relay based on saline tests in the <a href="https://github.com/esahaicu/BRAINSBoard/Results">results section</a> in the solution #1 Section
  - With this fix, we estimate only a 3% signal loss rather than estimated 30% loss of the signal current with high impedance electrodes.
2. Replace connector to any microcontroller with an embedded RP2040 microprocessor and develop the BRAINSBoard as the microcontroller itself to be able to implement more electrical isolation.
  - One noticeable issue (Problem #2) is that, when sending serial commands from a computer and through an Arduino where said computer is the power source for the board, there will be some introduced noise that is present in the LFP Band in Neuropixel recordings (though no noticeable noise in the AP Band of the recording) that is always present when a serial command is sent from the computer to the board.
  - We suspect this is due to ground loops forming between the building ground and the ground of the computer that is powering the Arduino
  - The most effective solution is to isolate the USB power, utilize an external power source, and allow for  
3. Update Connectors
  - USB and Power Connector Updates:
   - Since the plan is to embed a microprocessor directly onto the BRAINSBoard, we will utilize a USB-C connector directly on the board.
   - A 5.5mm DC Barrel Jack will also be added for external power.
  - Update the 2 2x8 Box Connctors to a more universal neuroscience connector with the NanoZ 2x<a href="(https://www.digikey.com/en/products/detail/samtec-inc/MOLC-110-01-S-Q/6695611)">32 Samtec Connector (MOLC‐110‐01‐S‐Q)</a>
   - This will make it easier to connect to varying electrode headstages utilizing already shielded products like <a href="https://plexon.com/products/nanoz-adaptors-omnetics/#1585316524959-3f3aca9b-4d99">this one from Plexon</a>.
   - This also allows for easy modifications to upgrade the board to be compatible with 32 and 64 channel electrodes.
  - Omnetics18 Connector for a <a href="https://intantech.com/RHS_headstages.html?tabSelect=RHS16ch&yPos=0">16-Channel Recording Headstage</a>
   - The plan is to implement more Solid State relays for a similar isolated input from the electrodes through the BRAINSBoard for a 16-channel recording headstage
   - The board will be setup to connect to the recording state instead of having a "floating" state as it does now when SP3T state is all LOW.
  - BNC Connectors along with male headers for microcontroller I/O 

# REFERENCES
[1]	B. D. Greenberg et al., “Three-Year Outcomes in Deep Brain Stimulation for Highly Resistant Obsessive–Compulsive Disorder,” Neuropsychopharmacology, vol. 31, no. 11, pp. 2384–2393, Nov. 2006, doi: 10.1038/sj.npp.1301165.

[2]	T. Wichmann and M. R. DeLong, “Deep Brain Stimulation for Neurologic and Neuropsychiatric Disorders,” Neuron, vol. 52, no. 1, pp. 197–204, Oct. 2006, doi: 10.1016/j.neuron.2006.09.022.

[3]	“Electrical stimulation of the globus pallidus internus in patients with primary generalized dystonia: long-term results in: Journal of Neurosurgery Volume 101 Issue 2 (2004) Journals.” Accessed: Nov. 08, 2024. [Online]. Available: https://thejns.org/view/journals/j-neurosurg/101/2/article-p189.xml

[4]	C. N. Heck et al., “Two-year seizure reduction in adults with medically intractable partial onset epilepsy treated with responsive neurostimulation: Final results of the RNS System Pivotal trial,” Epilepsia, vol. 55, no. 3, p. 432, Feb. 2014, doi: 10.1111/epi.12534.

[5]	C. Orlemann, C. Boehler, R. Kooijmans, B. Li, M. Asplund, and P. Roelfsema, “Flexible Polymer Electrodes for Stable Prosthetic Visual Perception in Mice,” Adv. Healthc. Mater., vol. 13, p. e2304169, Mar. 2024, doi: 10.1002/adhm.202304169.

[6]	J. Vorwerk, A. A. Brock, D. N. Anderson, J. D. Rolston, and C. R. Butson, “A retrospective evaluation of automated optimization of deep brain stimulation parameters,” J. Neural Eng., vol. 16, no. 6, p. 064002, Nov. 2019, doi: 10.1088/1741-2552/ab35b1.

[7]	C. J. Hartmann, S. Fliegen, S. J. Groiss, L. Wojtecki, and A. Schnitzler, “An update on best practice of deep brain stimulation in Parkinson’s disease,” Ther. Adv. Neurol. Disord., vol. 12, p. 1756286419838096, 2019, doi: 10.1177/1756286419838096.

[8]	G. Deuschl et al., “Deep brain stimulation: postoperative issues,” Mov. Disord. Off. J. Mov. Disord. Soc., vol. 21 Suppl 14, pp. S219-237, Jun. 2006, doi: 10.1002/mds.20957.

[9]	J. Buhlmann, L. Hofmann, P. A. Tass, and C. Hauptmann, “Modeling of a Segmented Electrode for Desynchronizing Deep Brain Stimulation,” Front. Neuroengineering, vol. 4, Dec. 2011, doi: 10.3389/fneng.2011.00015.

[10]	D. N. Anderson et al., “The μDBS: Multiresolution, Directional Deep Brain Stimulation for Improved Targeting of Small Diameter Fibers,” Front. Neurosci., vol. 13, Oct. 2019, doi: 10.3389/fnins.2019.01152.

[11]	S. Zhang et al., “Comparing Current Steering Technologies for Directional Deep Brain Stimulation Using a Computational Model That Incorporates Heterogeneous Tissue Properties,” Neuromodulation, vol. 23, no. 4, p. 469, Aug. 2019, doi: 10.1111/ner.13031.

[12]	C. Pollo et al., “Directional deep brain stimulation: an intraoperative double-blind pilot study,” Brain, vol. 137, no. 7, pp. 2015–2026, Jul. 2014, doi: 10.1093/brain/awu102.

[13]	J. A. Frank, M.-J. Antonini, and P. Anikeeva, “Next-generation interfaces for studying neural function,” Nat. Biotechnol., vol. 37, no. 9, pp. 1013–1023, Sep. 2019, doi: 10.1038/s41587-019-0198-8.

## $\textbf{\color{white}This work was supported by NIH NINDS project number 1R01NS120850}$

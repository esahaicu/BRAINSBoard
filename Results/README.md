# BRAINSBoard Results

<p align="center">
 <img src=/Results/Figures/ResultsExpSetup.png/>
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

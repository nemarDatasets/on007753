### Overview
This dataset includes EEG data in which Japanese native speakers read Japanese newspapers in the scanner. Stimuli were presented word by word. This dataset is part of BCCWJ-Brain, This dataset is part of BCCWJ-Brain; three types of brain data — fMRI, MEG, and EEG — were acquired from separate groups of participants using the same stimuli, enabling cross-modality comparisons of language processing with high spatial and temporal resolution respectively.
The BCCWJ-Brain collection consists of the following datasets:

- BCCWJ-fMRI: ds007752
- BCCWJ-MEG: 
- BCCWJ-EEG: ds007753


## Participants
Forty-two Japanese native speakers were recruited (22 females and 20 males; mean age=20.5 (SD = 2.89)). All participants were right-handed, had no neurological illness, and had normal or corrected-to-normal vision. 

## Data Acquisition
EEG data were recorded using a BrainAmp amplifier (Brain Products GmbH, Germany) with a 64-channel electrode cap. The online reference electrode was placed at FCz, and the ground electrode was placed at AFz. An electrode was placed below the right eye (IO) to monitor ocular artifacts. Electrode impedances were kept below 40kΩ prior to the recording. Data were recorded at a sampling rate of 1,000Hz.

## Experiment Procedure
Twenty Japanese newspaper articles were used as stimuli. Stimuli were presented word by word using rapid serial visual presentation (RSVP) implemented in PsychoPy (Peirce, 2007). Each stimulus was presented for 500 ms, followed by a 500 ms blank screen. The order of the newspaper articles were randomaized.

## Data Preprocessing
EEG data were preprocessed using MNE-Python (v1.9.0; Gramfort et al., 2013) and Eelbrain (v0.40.3; Brodbeck et al., 2023). Continuous EEG was recorded with an easycap-M1 electrode layout and one bipolar EOG channel (IO). Independent component analysis (ICA) was then applied, and components reflecting ocular artifacts were identified and removed. The ICA decomposition was subsequently applied to the 0.1–40 Hz bandpass filtered data, and the cleaned signal was re-referenced to the common average. Data were then segmented into epochs from −100 to 1,000 ms relative to word onset and downsampled to 200 Hz. Baseline correction was applied using the pre-stimulus interval (−100 to 0 ms). The preprocessed EEG data can be found in the ``derivatives``.
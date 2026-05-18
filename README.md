
## Overview
This dataset contains EEG data collected while Japanese native speakers read Japanese newspaper articles from the Balanced Corpus of Contemporary Written Japanese (BCCWJ; Maekawa et al., 2014). Stimuli were presented word by word. This dataset is part of BCCWJ-Brain, This dataset is part of BCCWJ-Brain; three types of brain data — fMRI, MEG, and EEG — were acquired from separate groups of participants using the same stimuli, enabling cross-modality comparisons of language processing with high spatial and temporal resolution respectively.
The BCCWJ-Brain collection consists of the following datasets:

- BCCWJ-fMRI: ds007752 ([https://openneuro.org/datasets/ds007752](https://openneuro.org/datasets/ds007752))
- BCCWJ-MEG: ds007763 ([https://openneuro.org/datasets/ds007763](https://openneuro.org/datasets/ds007763))
- BCCWJ-EEG: ds007753 ([https://openneuro.org/datasets/ds007753](https://openneuro.org/datasets/ds007753))


## Participants
Data from forty-one participants were included in the dataset (22 females and 19 males; mean age=20.5 (SD = 2.89)). All participants were right-handed, had no neurological illness, and had normal or corrected-to-normal vision. 

## Data Acquisition
EEG data were recorded using a BrainAmp amplifier (Brain Products GmbH, Germany) with a 64-channel electrode cap. The online reference electrode was placed at FCz, and the ground electrode was placed at AFz. An electrode was placed below the right eye (IO) to monitor ocular artifacts. Electrode impedances were kept below 20kΩ prior to the recording. Data were recorded at a sampling rate of 1,000Hz.

## Experiment Procedure
Twenty Japanese newspaper articles were used as stimuli. Stimuli were presented word by word using rapid serial visual presentation (RSVP) implemented in PsychoPy (Peirce, 2007, 2009). Each stimulus was presented for 500 ms, followed by a 500 ms blank screen. The order of the newspaper articles were randomized.

## Data Preprocessing
EEG data were preprocessed using MNE-Python (v1.9.0; Gramfort et al., 2013) and Eelbrain (v0.40.3; Brodbeck et al., 2023). Continuous EEG was recorded with an easycap-M1 electrode layout and one bipolar EOG channel (IO). Independent component analysis (ICA) was then applied, and components reflecting ocular artifacts were identified and removed. The ICA decomposition was subsequently applied to the 0.1–40 Hz bandpass filtered data, and the cleaned signal was re-referenced to the common average. Data were then segmented into epochs from −100 to 1,000 ms relative to word onset and downsampled to 200 Hz. Baseline correction was applied using the pre-stimulus interval (−100 to 0 ms). The preprocessed EEG data can be found in the ``derivatives``.

```
derivatives/
├── eeg/
    ├── sub-XX_task-BCCWJreading_eeg_raw.fif (raw data converted to fif files)
    ├── sub-XX_task-BCCWJreading_eeg_reref0.1-40-ica_raw.fif (preprocessed files without downsampling (1,000Hz))
    └── sub-XX_task-BCCWJreading_eeg_reref0.1-40-ica_ave.fif (evoked files)
```

## Notes
Since the BCCWJ texts are not copyright-free, texts for the experiment is not included in this dataset. To obtain the text, users must register for access to the BCCWJ corpus separately. Once access is granted, we provide a script to incorporate the text into the corresponding ``events.tsv`` files.


## References
Brodbeck, C., Das, P., Gillis, M., Kulasingham, J. P., Bhattasali, S., Gaston, P., Resnik, P., & Simon, J. Z. (2023). Eelbrain, a Python toolkit for time-continuous analysis with temporal response functions. eLife, 12, e85012. https://doi.org/10.7554/eLife.85012

Gramfort, A., Luessi, M., Larson, E., Engemann, D. A., Strohmeier, D., Brodbeck, C., Goj, R., Jas, M., Brooks, T., Parkkonen, L., & Hämäläinen, M. (2013). MEG and EEG data analysis with MNE-Python. Frontiers in Neuroinformatics, 7, 267. https://doi.org/10.3389/fnins.2013.00267

Maekawa, K., Yamazaki, M., Ogiso, T., Maruyama, T., Ogura, H., Kashino, W., Koiso, H., Yamaguchi, M., Tanaka, M., & Den, Y. (2014). Balanced corpus of contemporary written Japanese. Language Resources and Evaluation, 48, 345–371. https://doi.org/10.1007/s10579-013-9261-0

Peirce, J. W. (2007). PsychoPy—Psychophysics software in Python. Journal of Neuroscience Methods, 162(1–2), 8–13. https://doi.org/10.1016/j.jneumeth.2006.11.017

Peirce, J. W. (2009). Generating stimuli for neuroscience using PsychoPy. Frontiers in Neuroinformatics, 2, 10. https://doi.org/10.3389/neuro.11.010.2008
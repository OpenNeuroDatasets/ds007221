# Cross-environment Multi-paradigm Motor Imagery EEG Dataset
# Description
This dataset contains EEG recordings collected during motor imagery (MI) tasks under different recording environments. The primary dataset includes recordings from a controlled laboratory setting and a simulated hospital environment, designed to investigate the impact of environmental variability on EEG-based brain–computer interface (BCI) performance.In addition, a small supplementary dataset recorded in a space station environment is provided, extending the dataset to a non-terrestrial recording condition.

# Participants
Main dataset: 84 healthy participants
Supplementary dataset: 3 participants (space station environment)
All participants completed motor imagery tasks following similar experimental protocols.

# Experimental Design
# Recording Environments
Laboratory environment: electromagnetically shielded, low-noise condition
Simulated hospital environment: multi-sensory setup including visual, auditory, and contextual elements
Space station environment (supplementary): microgravity condition with distinct acquisition setup

# Motor Imagery Tasks
Tasks include:
Left-hand motor imagery
Right-hand motor imagery
Resting state (space station dataset only)

# Paradigms
The main dataset includes multiple paradigms:
Graz motor imagery paradigm
SSMVEP-MI paradigm
Hybrid paradigms (including video and SSVideo conditions)

# Trial Structure
Each trial consists of:
Cue period: −2 to 0 s
Task period: 0 to 4 s
Rest period: 4 s

# Data Format
Main Dataset
Organized in BIDS format
Space Station Dataset (Supplementary)
Format: MATLAB .mat files

# EEG Recording
Main Dataset
64-channel EEG system (10–20 system)
60 channels used
Sampling rate:
Raw: 1000 Hz
Processed: 250 Hz
Space Station Dataset
EGGO system
32 dry electrodes
Data stored directly in .mat format

# This dataset can be used for:
Motor imagery BCI algorithm development
Cross-subject decoding
Cross-environment analysis
Robustness evaluation under different recording conditions
Benchmarking EEG signal processing methods

# Notes
The main dataset (84 participants) is designed for systematic analysis across environments.The space station dataset is provided as a supplementary resource due to its different acquisition setup and limited sample size.

# License
This dataset is released under an open-access license. Please refer to the repository for details.
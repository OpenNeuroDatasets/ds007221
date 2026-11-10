# Cross-Environment Multi-Paradigm Motor Imagery EEG Dataset

## Overview

This dataset contains electroencephalography (EEG) recordings from **84 healthy participants**, each recorded in two environments: a **simulated hospital ward** and a **controlled laboratory**. It comprises four sub-datasets covering multiple motor imagery (MI) paradigms and both offline and online recordings.

The dataset supports research on MI decoding, cross-subject transfer, cross-environment generalization, and the effects of visual stimulation on MI-based brain-computer interfaces (BCIs). Raw recordings, preprocessed EEG, and supporting questionnaire materials are provided.

- **Data:** [OpenNeuro ds007221](https://openneuro.org/datasets/ds007221)
- **Dataset DOI (version 1.0.1):** [10.18112/openneuro.ds007221.v1.0.1](https://doi.org/10.18112/openneuro.ds007221.v1.0.1)
- **Analysis code:** [GitHub](https://github.com/boom-sun/Cross-Environment-Multi-Paradigm-Motor-Imagery-EEG-Dataset)

## Participants and experimental design

Participants were aged 20-32 years (mean 23.18 years; 49 female). Each participant completed recordings in both environments, with environment order counterbalanced across participants. The four sub-datasets contain separate participant groups.

| Sub-dataset | Participants | Tasks and paradigms |
| --- | ---: | --- |
| Graz | 14 | Left-hand MI, right-hand MI, feet MI, and rest |
| SSMVEP-MI | 22 | Left- and right-hand MI and action observation (AO), using periodic hand-action video stimuli |
| Hybrid | 37 | Left- and right-hand MI under four stimulus conditions: Graz, SSMVEP, Video, and SSVideo |
| Hybrid-online | 11 | The same four stimulus conditions, with offline calibration and online feedback |

**Scene 1** was a simulated hospital ward incorporating visual, auditory, olfactory, and tactile contextual cues. **Scene 2** was a laboratory within an electromagnetically shielded enclosure. These recordings were collected from healthy volunteers, not a clinical patient cohort.

The manuscript describes a trial sequence of a 2-second cue, a 4-second task, and a 4-second rest period. Use recording-specific event files to determine marker timing and class labels.

The study was approved by the ethics committee of Tianjin University. All participants provided written informed consent, including consent to share de-identified data.

## EEG acquisition and preprocessing

The acquisition protocol used a SynAmps2 system with a 64-channel Quick-Cap, with 60 scalp channels selected for analysis. Raw EEG was sampled at **1000 Hz**, referenced to the **tip of the nose**, with a forehead ground and a 50 Hz acquisition notch filter.

The preprocessed derivatives contain 60-channel EEG at **250 Hz**. Processing included a 49-51 Hz notch filter, common-average re-referencing, an approximately 4 Hz high-pass filter, downsampling, and epoching from **-2 to 4 seconds relative to task onset**.

Some raw sidecars currently differ from the manuscript in manufacturer and channel-count fields. Check recording-specific channel files and headers before analysis; the number of stored raw channels may differ from the 60-channel analysis montage.

## Data organization

Raw EEG is organized using BIDS conventions, with BrainVision recordings (`.vhdr`, `.vmrk`, `.eeg`) and accompanying event, channel, and acquisition metadata.

| File or directory | Contents |
| --- | --- |
| `sub-*/ses-*/eeg/` | Raw EEG and recording-specific metadata |
| `participants.tsv` | Demographics and sub-dataset membership (`source`) |
| `recordings.tsv` | Recording inventory, including task, paradigm, run, and environment-order information |
| `derivatives/` | Preprocessed MATLAB files grouped into Graz, SSMVEP-MI, Hybrid, and Hybrid-online |
| `Questionnaire.xlsx` | Questionnaire texts and raw STAI responses |

Derivative `.mat` files contain `data` (channels x time points x trials), `labels` (task-trigger labels), and `fs` (250 Hz). Their filenames encode participant and scene indices, with additional paradigm labels for Hybrid and Hybrid-online. Verify participant correspondence and environment assignment when combining raw data and derivatives. Consult event metadata for task-specific label mappings.

Raw recordings can be accessed using compatible EEG tools such as MNE-Python and EEGLAB. For reproducible comparisons, report the dataset version, selected sub-dataset, task classes, preprocessing, and train/test split.

## Citation

**If you use this dataset in your research, please cite the dataset DOI below.** Your citation acknowledges the contributors and helps others find and reuse the data. Cite the specific version you use; the example below refers to version 1.0.1.

Cross-Environment Multi-Paradigm Motor Imagery EEG Dataset (Version 1.0.1) [Data set]. OpenNeuro. https://doi.org/10.18112/openneuro.ds007221.v1.0.1

```bibtex
@misc{cross_environment_mi_eeg_v1_0_1,
  title        = {Cross-Environment Multi-Paradigm Motor Imagery {EEG} Dataset},
  howpublished = {OpenNeuro},
  doi          = {10.18112/openneuro.ds007221.v1.0.1},
  url          = {https://doi.org/10.18112/openneuro.ds007221.v1.0.1},
  note         = {Data set, version 1.0.1}
}
```

Use the OpenNeuro-generated citation for the release's authoritative creator list and release date.

The accompanying manuscript, *A Cross-Environment Multi-Paradigm EEG Dataset for Motor Imagery Brain-Computer Interface*, is being prepared and has not yet been submitted or peer reviewed (status: November 10, 2026). The DOI above identifies the dataset, not a journal article. Paper citation details will be added when publicly available.

## License and contact

Please consult the license information for the OpenNeuro release you download. The local dataset metadata does not currently specify a license; the code repository's license should not be assumed to apply to the data.

For questions, contact the corresponding authors:

- Xinwei Sun: sxwsdhf@163.com
- Kun Wang: flora_wk@tju.edu.cn

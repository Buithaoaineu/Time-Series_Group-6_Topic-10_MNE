**Introduction**  

In this section, I will present the exploratory data analysis of our EEG and eye‑tracking dataset. The goal of EDA is to understand the basic structure of the data
**Dataset Description**  

In this study, we use the MNE Sample Dataset, a standard dataset commonly employed for practicing EEG analysis. The dataset contains both EEG signals (recorded with the EGI system) and eye-tracking data (in ASCII format), collected from a pupillary light reflex experiment.

In the experiment, one participant fixated on the screen while short light flashes appeared. The onset of each flash was recorded by a photodiode attached to the screen, and the signal was sent simultaneously to both the EEG and eye-tracking systems.

This setup provides data that captures both the brain’s electrical activity and the eye’s response, enabling analysis of the relationship between brain waves and eye movements within the same experiment.

**Analysis Steps**  

Our analysis follows several key steps:

1. First, we load the dataset using MNE functions.  
2. Second, we inspect the basic information: duration, sampling rate, number of channels, and event markers.  
3. Third, we preprocess the EEG data by applying a band‑pass filter between 1 and 30 hertz to remove noise.  
4. Fourth, we segment the data into epochs around the light flash events.  
5. Fifth, we compute event‑related potentials to see the average brain response.  
6. Finally, we analyze the eye‑tracking data, including gaze position and pupil size, and compare these with the EEG responses.

**Channels Overview**  

The dataset has several types of channels: three extra channels, one stimulus channel, two channels for eye position, and one channel for pupil size. Information about head and sensor positions is missing. With this setup, we can study both brain activity and eye movements during the experiment.

**Filters Applied**  

The data was recorded with a high‑pass filter at 0 Hz and a low‑pass filter at 500 Hz. This means the raw signal includes almost the whole frequency range. We will need more preprocessing to focus on the brain wave bands that matter


**Issues Identified**  

There are some problems:

No participant information, so we cannot do subject‑specific analysis.

No head or sensor position data, so we cannot locate brain sources.

The wide frequency range means noise and artifacts are present, so careful filtering is needed

**Transition**  

In summary, the dataset is rich in EEG and eye‑tracking signals, with high resolution and multiple channels. But missing metadata and noise must be handled in preprocessing. 



**NỘI DUNG LÀM SLIDE**
**Introduction & Dataset description**

Introduction:
Goal: Explore EEG + eye‑tracking dataset
Understand structure, detect patterns, highlight issues
Dataset description:
EyeLink dataset: 129‑channel EEG (EGI) + ASCII eye‑tracking
Task: Pupillary light reflex (fixation + light flashes)
Events recorded simultaneously by both systems

**Analysis & Findings**
Analysis steps:
Load dataset with MNE
Inspect metadata (duration, sampling rate, channels, events)
Band‑pass filter EEG (1–30 Hz)
Epoch around light flash events
Compute ERPs (average brain response)
Analyze gaze + pupil size vs EEG
Findings:
Channels overview: 3 misc channels, 1 stimulus, 2 gaze, 1 pupil. No digitization → limits source localization
Filter applied: Acquisition: 0 Hz high‑pass, 500 Hz low‑pass. Raw signal wide range → preprocessing needed
Trends and Seasonality: No long‑term cycles. Short‑term repeating responses (pupil/gaze) linked to stimuli

**Issues**
Missing participant info
No head/sensor digitization
Noise/artifacts → require filtering & rejection

**Summary**
Dataset rich in EEG + eye‑tracking, high resolution
Preprocessing needed to address metadata gaps & noise
Next: detailed event‑related analysis

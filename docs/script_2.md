**Introduction**  

In this section, I will present the exploratory data analysis of our EEG and eye‑tracking dataset. The goal of EDA is to understand the basic structure of the data, identify potential patterns such as trends or seasonality, and highlight any issues that may affect further analysis

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

“The dataset contains three miscellaneous channels, one stimulus channel, two channels for gaze position, and one channel for pupil size. Head and sensor digitization information is not available. This combination allows us to analyze both brain responses and eye movements during the experiment.”

**Filters Applied**  

“At acquisition, the data was recorded with a high‑pass filter at zero hertz and a low‑pass filter at five hundred hertz. This means that the raw signal covers almost the entire frequency range of interest, and further preprocessing will be required to focus on the relevant bands.”

**Trends and Seasonality**  

“Because the data is continuous EEG and eye‑tracking, we do not expect long‑term seasonal cycles like in sales or weather data. Instead, we look for repeating patterns in the pupil size and gaze position that correspond to stimulus events. These repeating responses can be considered short‑term cycles in the data.”

**Issues Identified**  

“There are several issues to note. First, the participant information is missing, which limits subject‑specific analysis. Second, head and sensor digitization data is not available, which restricts source localization. Third, the wide frequency range means that noise and artifacts are present, so careful filtering and artifact rejection will be necessary.”

**Transition**  

“In summary, the exploratory analysis shows that the dataset is rich in EEG and eye‑tracking signals, with high sampling resolution and multiple channels. However, missing metadata and potential noise must be addressed in preprocessing. In the next section, we will move from exploration to detailed analysis, focusing on event‑related responses.”

**Transition**  


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

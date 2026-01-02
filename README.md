# fNIRS-2-RL Dataset

A multimodal dataset containing synchronized **functional near-infrared spectroscopy (fNIRS)** signals and **agent task variables/MDP tuples** collected during human-agent interaction in various reinforcement learning environments.

This dataset is intended for research on:
- Human-in-the-Loop Reinforcement Learning (HITL-RL)
- Brain-Computer Interfaces (BCI)
- Passive Reinforcement Learning from Human/Neural Feedback
- Implicit human feedback modeling
- Human-agent alignment through neuroadaptive technologies

**Code for AAAI-26:** [NeuroLoop-Classification GitHub repository](https://github.com/your-profile/NeuroLoop-Classification/tree/aaai)  
**Dataset link:** [fNIRS2RL Dataset GitHub repository](https://github.com/your-profile/fNIRS2RL)  

---

## Table of Contents
- [Dataset Overview](#dataset-overview)
- [Experimental Setup](#experimental-setup)
- [Data Modalities](#data-modalities)
- [Directory Structure](#directory-structure)
- [Data Format and Schema](#data-format-and-schema)
- [Preprocessing](#preprocessing)
- [Participant Logs](#participant-logs)
- [Surveys and Questionnaires](#surveys)
- [Ethics and Consent](#ethics-and-consent)
- [Citation](#citation)
- [License](#license)
- [Contact](#contact)

---

## Dataset Overview

This dataset captures **time-aligned human neural signals and agent transition data** during passive and active interaction tasks.

Each episode consists of:
- Continuous fNIRS recordings
- Agent–environment task variables (e.g. state, action, reward...)
- Shared timestamps

The dataset supports both:
- **Offline Learning** (e.g., classification, inverse RL, preference inference)
- **Online Learning through Simulated Replay** of human feedback signals during agent-environment interactions

---

## Experimental Setup

- **Participants:** Human subjects interacting with an RL agent
- **Domain Type:** Domain (e.g. Robot, Lunar Lander or Flappy Bird)
- **Task Type:** Interaction Typr (e.g., passive observation, active teleoperation)
- **Agent:** RL policy (autonomous or teleoperated)
- **Human Role:** Implicit evaluator (neural feedback only, no explicit labels)

TO ADD:
- Sampling rates (5.2 Hz)
- Hardware used for fNIRS acquisition
- Task duration and episode length
- Environment details (simulated / physical)

---

## Data Modalities

| Modality | Description |
|--------|-------------|
| fNIRS | Hemodynamic responses from multiple cortical channels |
| State | Environment state variables |
| Actions | Discrete or continuous agent actions |
| Rewards | Environment-provided rewards (if any) |
| Metadata | Episode IDs, subject IDs, timestamps |

---

## Directory Structure

```text
.
├── Experiment/
│   ├── Logs/
│   │   ├── experiment_logs.pdf
│   │   └── participant_deindentified_metadata.json
│   ├── ParticipantData/
│   │   ├── fnirs-data
│   │   │   ├── filtered-data
│   │   │   │   ├── PID_CONDITION_processed.csv
│   │   │   │   └── ...
│   │   │   ├── labeled-data
│   │   │   │   ├── PID_CONDITION_LabeledData.csv
│   │   │   │   └── ...
│   │   │   └── raw-data
│   │   │       ├── PID_DATE.fnirs
│   │   │       └── ...
│   │   └── task-data
│   │       ├── PID_CONDITION_DATE.pickle
│   │       └── ...
│   └── ...
├── Post-Experiment/
│   ├── nasa-tlx
│   └── post-experiment-surveys
└── README.md

```
---

## Data Format and Schema

Due to hardware and software differences for collecting fNIRS recordings and RL agent task variables, these two sets of data were collected separately.

Raw fNIRS data was collected as a whole experiment, where all conditions exist in the same file. Markers in the raw fNIRS recording indicate which trial was completed, not the specific condition. Raw task data was separated by condition. 

Raw fNIRS data had to be classified by hand dependent on the condition in lab notes associated with the raw data's trial marker.

Due to this, we recommend users pay closer attention to the filtered-data and labeled-data folders, where the separation has already been completed.

**Key**:
PID: Participant ID (e.g. 011, 022)
CONDITION: Task Condition (Lunar Watch/Passive: LW, Robot Play/Active: RP, Flappy Play/Active: FP)
DATE: DD/MM/YY (e.g. 013026 is Jan. 30, 2026)

#### Raw Data
Raw data includes the unfiltered and unseparated fNIRS recordings during an entire session with a participant.
**Filename**: PID_DATE.fnirs

#### Filtered Data
Filtered data includes the preprocessed and separated fNIRS recordings during one session condition with a participant.
**Filename**: PID_CONDITION_processed.csv

#### Labeled Data
Filtered data includes the filtered and separated fNIRS recordings alongside task variables and an optimality label during one session condition with a participant.
**Filename**: PID_CONDITION_LabeledData.csv

## Preprocessing

To be documented on 01/05/26.

## Participant Logs

To be uploaded and documented on 01/05/26.

## Surveys and Questionnaires 

To be uploaded and documented on 01/05/26.

## Ethics and Consent

This study was approved by the Institutional Review Board (IRB) of Tufts University's Social, Behavioral, and Educational Research Office (SBER) under protocol IRB-00005080, and all participants provided informed consent.

## Citation 

Santaniello, J., Russell, M., Jiang, B., Sassaroli, D., Jacob, R., & Sinapov, J. (2026).  
**Towards Reinforcement Learning from Neural Feedback: Mapping fNIRS Signals to Agent Performance.**  
*To appear in AAAI 2026.*


## Contact
Contact Julia Santaniello for inquiries: [julia.santaniello@tufts.edu](mailto:julia.santaniello@tufts.edu)



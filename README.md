# Neural Interfaces Challenge 2026

This repository contains our research, experimentation, and competition pipeline for **Track 2** and **Track 3** of the **Neural Interfaces Challenge 2026**.

The project focuses on developing reproducible EEG-based machine learning systems for two different neural interface problems:

* **Track 2 — EEG-to-BCI Decoding:** decoding user commands from EEG signals with an emphasis on generalization across recording sessions.
* **Track 3 — Sleep Onset Prediction:** estimating sleep onset from wearable EEG recordings, with an emphasis on generalization to unseen participants.

The repository separates **local research and experimentation**, **NeuralBench integration**, and **Codabench submissions** so that experimental development remains independent from the official competition pipeline.

---

## Challenge Tracks

|                            | **Track 2 — EEG-to-BCI Decoding**           | **Track 3 — Sleep Onset Prediction**             |
| -------------------------- | ------------------------------------------- | ------------------------------------------------ |
| **Problem**                | Decode BCI commands from EEG recordings     | Estimate sleep onset from wearable EEG           |
| **Task type**              | Classification                              | Temporal regression                              |
| **Generalization setting** | Cross-session                               | Cross-subject                                    |
| **Input**                  | EEG recordings during cognitive / BCI tasks | Wearable EEG recorded during sleep               |
| **Output**                 | Predicted command / class                   | Estimated time to sleep onset                    |
| **Main research focus**    | Robust EEG representations across sessions  | Robust sleep representations across participants |
| **Local workspace**        | `local/track2/`                             | `local/track3/`                                  |
| **Experiments**            | `local/track2/experiments/`                 | `local/track3/experiments/`                      |
| **Codabench submissions**  | `submissions/track2/`                       | `submissions/track3/`                            |
| **Documentation**          | `docs/track2/`                              | `docs/track3/`                                   |

---

## Track 2 — EEG-to-BCI Decoding

<img width="1280" height="600" alt="bci-decoding" src="https://github.com/user-attachments/assets/8a194b53-8347-470c-9931-6871ded3495a" />

Track 2 investigates EEG-based decoding of user commands under a **cross-session generalization setting**.

Development for this track is located in:

```text
local/track2/
```

---

## Track 3 — Sleep Onset Prediction

<img width="1280" height="600" alt="sleep-onset" src="https://github.com/user-attachments/assets/2be6b0b6-017a-49ab-bd68-94716b7c11a2" />

Track 3 focuses on predicting **sleep onset from wearable EEG**, with particular emphasis on generalization to participants not observed during training.

Development for this track is located in:

```text
local/track3/
```

---

## Repository Structure

```text
neural-interfaces-2026/
│
├── local/
│   ├── common/
│   ├── track2/
│   └── track3/
│
├── neuralbench_integration/
│   ├── neuraltrain_models/
│   ├── neuralbench_models/
│   └── overrides/
│
├── submissions/
│   ├── track2/
│   └── track3/
│
└── docs/
    ├── track2/
    └── track3/
```

## Repository Organization

| Directory                  | Purpose                                                                                                             |
| -------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| `local/`                   | Main research workspace: datasets, preprocessing, models, training, evaluation, experiments, notebooks, and outputs |
| `local/common/`            | Components genuinely shared between Track 2 and Track 3                                                             |
| `local/track2/`            | Track 2 development and experiments                                                                                 |
| `local/track3/`            | Track 3 development and experiments                                                                                 |
| `neuralbench_integration/` | Minimal compatibility layer required to evaluate selected models with NeuralBench / NeuralTrain                     |
| `submissions/`             | Candidate and final packages prepared for Codabench                                                                 |
| `docs/`                    | Public documentation and GitHub Pages content                                                                       |

---

## Development Workflow

```text
Local Research
     ↓
Experimentation
     ↓
Model Selection
     ↓
NeuralBench Integration
     ↓
Official Validation
     ↓
Codabench Submission
```

Experimental models are developed first inside `local/`. Only selected models are promoted to `neuralbench_integration/` once they are ready to be evaluated using the official NeuralBench workflow.

Final competition packages are stored separately under `submissions/`.

---

## NeuralBench Integration

**NeuralBench** and **NeuralTrain** are external tools used by the challenge.

Their complete source repositories are **not duplicated here**.

Instead, `neuralbench_integration/` contains only the minimum components required to connect selected models from this repository with the official benchmark pipeline.

```text
local model
     ↓
neuralbench_integration/
     ↓
NeuralBench evaluation
     ↓
Codabench submission
```

# Codex Instructions

This repository has three operational layers.

## 1. local/
Main research workspace.

Use for:
- datasets and preparation
- preprocessing
- model development
- training
- evaluation
- experiments
- notebooks
- scripts
- generated outputs

Code here does not need to be NeuralBench-compatible during exploration.

## 2. neuralbench_integration/
Only for selected models that need to run with the official NeuralBench / NeuralTrain ecosystem.

Use for:
- NeuralTrain-compatible model wrappers/config classes
- NeuralBench model YAML files
- minimal task/config overrides

Do not copy the whole NeuralBench or NeuralTrain source tree here.

## 3. submissions/
Only for Codabench-ready packages and submission history.

Do not use this folder for active research.

## Track separation

- Track 2 -> `local/track2/`
- Track 3 -> `local/track3/`
- Shared code -> `local/common/`

Only move code to `common/` if it is genuinely reusable by both tracks.

## Naming

Experiments:
- T2-E001
- T3-E001

Submissions:
- T2-S001
- T3-S001

Avoid filenames such as final.py, final_v2.py, final_REAL.py.

## Data and weights

Do not commit large EEG datasets, caches or model checkpoints.
Keep preparation code, manifests, metadata and instructions in Git.

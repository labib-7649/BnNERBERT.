# Reproducibility notes

## Status

The notebook has been prepared for source sharing, but training has not been rerun or independently validated. Python and Git were unavailable in the preparation environment. The supplied dataset/BnNERIntent25.json matches the original notebook class names and split counts. Original package versions, hardware details, and checkpoint revisions remain unverified. Exact reproduction of manuscript scores is therefore not currently established.

## Settings recorded in the source

| Setting | Value |
| --- | --- |
| Main model | `sagorsarker/bangla-bert-base` |
| Random seed | 42 for Python, NumPy and PyTorch |
| Learning rate | 2e-5 |
| Train/evaluation batch size | 32 |
| Maximum epochs | 10 |
| Weight decay | 0.01 |
| Warmup steps | 200 |
| Scheduler | Linear |
| Gradient accumulation | 1 |
| Evaluation/checkpoint frequency | Each epoch |
| Best checkpoint | Loaded at end, default validation loss selection |
| Early stopping patience | 2 in main training; 3 in comparison loop |
| Metrics | Accuracy, macro precision/recall/F1, Matthews correlation |

## Changes for repository sharing

- Removed saved outputs and execution counts from the research notebook. These may contain full text samples, local paths, or stale results. No saved output is presented as verified paper evidence.
- Removed the mandatory Google Drive mount and replaced it with notebook guidance.
- Replaced the absolute Colab dataset path with a repository-relative UTF-8 loader and an optional `BNNER_DATASET_PATH` override.
- Replaced inline package installation with requirements-based setup instructions.
- Added introductory notebook documentation. Training logic and hyperparameters were otherwise preserved.

## Known source limitations

1. Labels are enumerated from a Python set, so label IDs can vary across interpreter sessions despite seed 42. Recover and save the original mapping for an exact replay. Sorting labels would be an explicit change to the experiment.
2. The comparison loop uses `BertForSequenceClassification` for all model names, including ELECTRA, DistilBERT, and T5 architectures. Architecture compatibility and pretrained weight loading must be checked before treating those runs as valid comparisons. No correction or retraining was made during preparation.
3. Tokenization disables truncation. Inputs longer than the model limit may fail.
4. The metrics tracker is shared across comparison runs and is not attached to the initial training run.
5. MAE, MSE, and RMSE are calculated on arbitrary categorical IDs. Their magnitudes depend on label ordering and should not be interpreted as distances between intents. The final results list also appends the last model twice.
6. The intent pipeline is created before training; later model reassignment and device changes make the exploratory combined intent/NER examples state-dependent. Use a fresh pipeline from a verified trained checkpoint for deployment.
7. The NER section loads an external pretrained model and demonstrates predictions; it does not train or evaluate a Bengali NER benchmark. The final example assigns the `(intent, ner)` tuple to `ner_tags` rather than unpacking it.

Before making reproduction claims, verify the supplied data provenance and recover the original environment and label mapping, run the relevant sections, and compare their results to the manuscript. Keep any corrected experiments distinguishable from the submitted implementation.

# Bengali intent classification research notebook

Research code for Bengali intent classification using transformer models, with exploratory named entity recognition (NER) examples. The main artifact is [BERT.ipynb](BERT.ipynb).

This repository shares the notebook associated with a submitted manuscript. The manuscript title, authors, publication details, and original software environment have not yet been supplied. No new experimental results are claimed by this repository preparation.

## Contents

- `BERT.ipynb`: training, validation/test metrics, model comparisons, error analysis, and exploratory NER.
- `dataset/BnNERIntent25.json`: the 25-class intent dataset used by the notebook.
- `requirements.txt`: dependency ranges for a candidate execution environment, not the recovered paper environment.
- [REPRODUCIBILITY.md](REPRODUCIBILITY.md): experimental settings, preparation changes, and known limitations.
- [PUBLISHING.md](PUBLISHING.md): GitHub upload and reviewer-link instructions.

## Setup

Use Python 3.10 or 3.11 and open a terminal in the repository root:

```sh
python -m venv .venv
```

Activate with `.venv\Scripts\activate` on Windows or `source .venv/bin/activate` on macOS/Linux, then:

```sh
python -m pip install -r requirements.txt
python -m jupyter lab BERT.ipynb
```

A CUDA GPU is recommended for training. CPU execution can be slow; batch size 32 may exceed available GPU memory. Internet access is required to download pretrained models and evaluation metrics.

## Required experiment data

The supplied `dataset/BnNERIntent25.json` contains 25 classes and 3,750 records: 2,500 training, 500 validation, and 750 test examples. Its class names and counts match the original notebook outputs. The notebook loads this file by default; optionally set `BNNER_DATASET_PATH` to use another location.

The expected UTF-8 JSON structure is:

```json
{
  "train": [["Bengali sentence", "intent_label"]],
  "val": [["Bengali sentence", "intent_label"]],
  "test": [["Bengali sentence", "intent_label"]]
}
```

Preserve the original splits and labels. The example above illustrates the schema only. See [dataset/README.md](dataset/README.md) for the supplied data's status.

Run the main notebook from the repository root. The primary training/evaluation section precedes the optional model comparison and NER experiments; read the limitations before running those sections.

## Citation and reuse

Citation metadata and a license are pending the authors' decision. Cite the associated manuscript once its bibliographic details are available. No license is granted here for code or data; upstream models and source datasets retain their own terms.

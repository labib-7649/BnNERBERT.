# Data availability

`BnNERIntent25.json` is the supplied dataset consumed by the main notebook. It contains 25 intent classes with 100 training, 20 validation, and 30 test records per class (3,750 total). Class names and counts match the original notebook outputs. Records are `[sentence, intent]` pairs under `train`, `val`, and `test`; separate NER annotation fields are not present.

Exact text checks found 185 unique sentences shared between training and validation, 24 between training and test, and 3 between validation and test. These overlaps may affect evaluation. The supplied dataset and splits are preserved unchanged.

Authors should document provenance, annotation methodology, attribution, and redistribution terms. No data license is assigned by this preparation.
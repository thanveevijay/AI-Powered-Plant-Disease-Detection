# Dataset and evaluation protocol

This note describes a reproducible evaluation process for the plant-disease classifier. It does not claim a particular accuracy; report metrics only after running the experiment on the selected dataset.

## Dataset preparation
1. Record the dataset source, version, license, and download date.
2. Preserve the original class labels and document any label normalization.
3. Inspect class counts before splitting. Record missing, corrupt, and duplicate images.
4. Split by source image or plant/collection group where possible so near-duplicate images cannot leak across partitions.
5. Fit image normalization and any learned preprocessing using training data only.

## Model evaluation
- Keep training, validation, and test partitions separate.
- Select hyperparameters using validation data, not the final test set.
- Report per-class precision, recall, and F1 in addition to macro and weighted averages.
- Include a confusion matrix and class support counts.
- Record random seeds, framework versions, image size, augmentation settings, and model checkpoint identifier.

## Limitations
Photographs taken in controlled datasets may not represent field conditions, lighting, camera quality, or mixed infections. Predictions should be treated as decision support, not as a substitute for expert agronomic assessment. Include an abstain/low-confidence path when confidence is insufficient.

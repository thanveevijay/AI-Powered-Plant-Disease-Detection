# Model Evaluation Guide

This guide provides a repeatable checklist for evaluating the plant disease classifier. It does not claim a particular accuracy or establish clinical/agronomic validation.

## Before training

- Record the dataset source, version, license, and class distribution.
- Inspect labels and remove corrupted or unreadable images.
- Check for duplicates and near-duplicates before splitting.
- Split by plant, field, capture session, or source where possible. A random image-level split can place near-identical images in both training and test sets.
- Fix and record the random seed and preprocessing configuration.

## During training

- Use the validation set for model selection and early stopping.
- Apply augmentation only to training images.
- Fit normalization statistics on training data only when the chosen preprocessing requires learned statistics.
- Save the class-to-index mapping alongside the model artifact.
- Record framework versions, model architecture, input dimensions, and checkpoint identifier.

## Final evaluation

Evaluate once on an untouched test set. Report:

- Overall accuracy and balanced accuracy.
- Per-class precision, recall, and F1 score.
- Macro and weighted averages.
- Confusion matrix and class support.
- Calibration or confidence reliability where confidence scores are displayed.
- Performance on images captured under different lighting, devices, backgrounds, and growing conditions.

A single aggregate accuracy can hide poor performance on minority disease classes. Include per-class results and the number of test examples for every class.

## Inference safeguards

- Reject unsupported file types and oversized uploads.
- Verify that the decoded image is valid before preprocessing.
- Preserve the exact preprocessing and class ordering used during training.
- Treat low-confidence or out-of-distribution inputs as uncertain rather than forcing a confident disease label.
- Present predictions as decision support for further inspection, not as a substitute for an agronomist's assessment.

## Reproducibility record

For each experiment, retain the dataset version, split manifest, seed, package versions, training configuration, model checksum, evaluation metrics, and date. Never compare two model scores unless their test sets and evaluation procedures are comparable.

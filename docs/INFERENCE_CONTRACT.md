# Inference Contract

The inference function should accept a validated image, apply the same preprocessing used in training, return class probabilities and model version, and handle unreadable files gracefully. Include a confidence warning and avoid claiming that a low-confidence prediction is a confirmed diagnosis.
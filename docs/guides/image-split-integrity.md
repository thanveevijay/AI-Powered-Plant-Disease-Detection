# Image Split Integrity

Check for duplicate and near-duplicate images across training, validation, and test splits. Where multiple images come from the same plant or capture session, keep related samples grouped when defining splits.

Record the split-generation seed and manifest. This reduces the risk of overly optimistic evaluation caused by image leakage.
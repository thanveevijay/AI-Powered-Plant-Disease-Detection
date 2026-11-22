# Dataset Split Protocol

Split images by plant, farm, or acquisition session where possible so near-duplicate images do not leak across train and test sets. Preserve class balance where feasible and document the split seed. Keep the final test set untouched during model selection.
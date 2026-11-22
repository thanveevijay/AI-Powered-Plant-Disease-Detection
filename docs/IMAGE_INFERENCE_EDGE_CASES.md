# Image inference edge cases

Test image handling beyond clean examples from the training dataset.

## Input edge cases
- Empty upload and zero-byte file.
- Corrupt or partially decoded image.
- Unsupported file format.
- Grayscale image when RGB is expected.
- RGBA image with transparency.
- Very small or unusually large dimensions.
- Portrait and landscape aspect ratios.
- Blurry, dark, overexposed, or low-resolution photographs.
- Multiple leaves, overlapping leaves, or a background-dominant image.

## Expected handling
- Validate the file before preprocessing.
- Convert supported channel formats consistently with the training pipeline.
- Avoid silently stretching images in ways that distort leaf features.
- Return a clear error for inputs that cannot be processed.
- Use a low-confidence or out-of-scope response when the image is unsuitable for classification.

## Evaluation
Keep a small, versioned edge-case set separate from the final test set. Record the preprocessing version and expected handling for each case. Do not interpret a confident prediction as proof that the input belongs to a supported class.

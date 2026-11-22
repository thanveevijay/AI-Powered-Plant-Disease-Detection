# Inference Validation Checklist

## Input checks
- Confirm that the uploaded file is a supported image format.
- Reject unreadable or empty files with a clear message.
- Check image dimensions and handle unusually large inputs safely.
- Apply the same resizing, color conversion, and normalization used during training.

## Prediction checks
- Verify that the model output has the expected number of classes.
- Confirm that class-index-to-label mapping is consistent with training.
- Handle non-finite scores and unexpected output shapes safely.
- Display confidence as a model score, not as a guarantee of correctness.

## User-facing result
Include the predicted label, confidence information, and a reminder that automated predictions should be confirmed when the result affects crop treatment decisions.

## Monitoring
Collect privacy-conscious aggregate information about failed inputs and uncertain predictions to guide future testing. Do not store uploaded images unless the application has a clear need and appropriate user notice.

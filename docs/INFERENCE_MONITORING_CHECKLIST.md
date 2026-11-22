# Inference monitoring checklist

Use this checklist when exposing the plant-disease model through an inference service.

## Request validation
- Reject empty, corrupt, or unsupported image files.
- Enforce maximum request size and supported image dimensions.
- Normalize image channels and dimensions consistently with training.
- Return a clear validation error when preprocessing fails.

## Prediction quality signals
- Track prediction volume and input validation failures.
- Monitor class distribution and confidence distribution over time.
- Review low-confidence and out-of-distribution examples.
- Compare sampled predictions with verified labels when available.
- Segment evaluation by device, lighting, crop type, and capture setting where those attributes are legitimately collected.

## Operational safeguards
- Record model version and preprocessing version with each prediction.
- Avoid logging uploaded image bytes or personal metadata unnecessarily.
- Provide a low-confidence/unknown outcome rather than forcing every image into a known class.
- Define a rollback procedure for a model version that causes regressions.

Monitoring signals indicate when review is needed; they do not independently prove that a model is accurate or safe for every field condition.

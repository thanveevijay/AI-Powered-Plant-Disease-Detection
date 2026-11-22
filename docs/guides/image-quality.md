# Image Quality Checks

Check image dimensions, file readability, color channels, and severe blur before inference.

Do not silently stretch images into the model input shape. Apply the same documented resize and normalization steps used during training, and tell users when an image is unsuitable.
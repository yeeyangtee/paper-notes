# Generative Adversarial Network for Integrated Circuits Physical Assurance Using Scanning Electron Microscopy

## Summary
- Task is detection and recognition of **elements** (logic cells) from SEM images
- Claim: Traditional augmentation such as intensity changes, noise injection, rotation, shear, translation, is not always able to 'project the variations of images acquired by SEM with different acquisition parameters.'
- Proposed: ROI extraction to auto grab logic cells from existing images, use GAN to transform and add variation, use these synthetic images to form a synthetic dataset.

## Method
- preprocess SEM image: denoising followed by binarisation to obtain gate regions vs background.
- 
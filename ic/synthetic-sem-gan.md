# Generative Adversarial Network for Integrated Circuits Physical Assurance Using Scanning Electron Microscopy

## Summary
- Task is detection and recognition of **elements** (logic cells) from SEM images
- Claim: Traditional augmentation such as intensity changes, noise injection, rotation, shear, translation, is not always able to 'project the variations of images acquired by SEM with different acquisition parameters.'
- Proposed: ROI extraction to auto grab logic cells from existing images, use GAN to transform and add variation, use these synthetic images to form a synthetic dataset.

## Contributions
1. Automatic cell extraction technique for logic cells
2. Synthetic cell generation technique based on MSGAN
3. Image quality assesment metric to measure how meaningful the synthetic data is.

## Methods
### Cell extraction: 
1. preprocess SEM image: denoising, binarisation, connected components analysis to obtain cell components.
2. Cell detection: novel technique where rows are split (as cell components are aligned row-wise) > based on distance between cell component determine if they are belonging to the same cell > extract out the 'list' of cells for each row.

### Synthetic image generation
- Use Mode-seeking GAN (MSGAN) to train on the extracted cell images. 
- There are 13 classes of cells, which are used as class conditional labels to the MSGAN
- Random variable input to MSGAN creates variations in the synthetic cell images. Essentially, underlying features (shape) are consistent but texture is different in the synthetic images.
- 
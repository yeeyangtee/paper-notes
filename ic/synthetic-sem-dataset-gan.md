# Generative Adversarial Network for Integrated Circuits Physical Assurance Using Scanning Electron Microscopy


## Summary | Problem statement
- We need large and diverse set of image for AI techniques for SEM image analysis.
- Conventional techniques such as augmentation cannot help much for IC, as SEM imaging has many acquisition parameters, also, some types of conventional augmentation cannot be directly transfered to IC.
- 

## Main contributions
- Method to detect logic cells on SEM images.
- Use extracted samples to train a mode seeking GAN to generate diversified samples.
- Propose metric for image quality assement of IC images.

## Method summary
**Region extraction of logic cells**
1. preprocessing by denoising + binarisation
2. Connected component analysis
3. Cell detection based on row/ column alignment logic, also use distance between consecutive components to determine if they belong to the same cell.

**MS-GAN for synthetic cell generation**
1. class conditional GAN is used. 
2. Classes are the different type of cells. 
3. Visually the different cells have different shape, some have differenet complexity. 
4. Fundamentally, cells appear to be rectangular bright shapes located near each other in some neat arrangement, and have repetitive nature.

**Image quality assessment metric**
1. Fourier descriptor with vector length 27, not sure howi ts computed.
2. This metric was only applied for 7/12 of the proposed classes.

## Future work on GAN with arbitrary crop ratio
- GANs synthetize images with fix square ratio as commonly done for almost all domains. Else if different ratio such as cityscapes, it is still fixed for whole dataset.
- For IC image, the cells which are fundamental units have different size and different ratio all the time.
- Can we design a GAN that can adapt to different aspect ratios, which is quite interesting. 

# Old

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
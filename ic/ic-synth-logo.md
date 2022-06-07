# IC SynthLogo: A Synthetic Logo Image Dataset for Counterfeit and Recycled IC detection


## Summary | Problem statement
- Logos are a problem in text detection methods such as Tesseract, EAST when applied to PCB analysis.
- To eventually deal with this, propose a way to generate a synthetic dataset of logo images in PCB data.

## Main contributions
- Method to generate the synthetic logo images
- Method allows a way to replicate effects such as ghost marking, recycling detects, focusing on counterfeit 'artifacts'
- Enables removal of logos.

## Method summary
### Logo removal
- Logo removed using ROI method, on the IC only.
- Main data input is still the whole (?) PCB iamge.

### Image inpainting (fill in gap)
- Fast Marching and Navier Stokes used to do image inpainting, filling in the gap from the logo removal.

### Image cloning (copy in new logo)
- First need identify the logo to be copied over. This is based on matching the shape (essentially just aspect ratio) of the logo region and the proposed 'synthetic' logo.
- Then use seamless cloning or mask composting to paste the new logo in.

### Postprocessing
- Do grayscale... add noise
- Add noise using gaussian noise throughout entire image apparently.

## Others

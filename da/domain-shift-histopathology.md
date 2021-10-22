# A Closer Look at Domain Shift for Deep Learning in Histopathology

studies domain shift in histopathology which is the analysis of microscope images of cells/tissue. i.e. medical images. Domain shift in their context arises from:
- staining variations
- scanner properties
- different medical centres doing the scan (probably combination of the two above)

3 methods of data transformation/augmentation were studied to see how they deal with domain shift. Domain shift was presented from data coming from 3 different scanners.
1. Colour and intensity augmentations, to increase model robustness to colour. The augmented images actually look quite extreme and unnatural. authors say that doing this is to force model to focus on features other than color - so why don't just grayscale?
2. stain normalization: Not very sure what is this but... generally they want to normalize the image in relation to a 'reference patch'. These will come from a medical centre.
3. cyclegan: Do image translation of each dataset into the domain of one medical centre. See if this helps reduce the domain shift.

## Interesting stuff:
- Histopathology images (of tissue and cells i think) do NOT give GABOR filters in the first few layers for a trained CNN on such images. Gabor filters are the typical ones that seem to do edge detection, which are very common for image sets like imagenet (natural images). This observation is probably true also for IC images.
- They present a representation shift metric to quantify amount of domain shift. This compares the mean distance between the distributions (of training set to a dataset from different domain) at the final filter of the network. Essentially measuring feature similarity after extraction from CNN. If two datasets are similar, network trained on one set should be generalisable to the other > domain shift is mitigated.
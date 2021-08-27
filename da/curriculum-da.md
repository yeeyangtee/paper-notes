# Curriculum Domain Adaptation for Semantic Segmentation of Urban Scenes

Previous methods try to do alignment in the feature space, but authors say that this will be quite hard for a segmentation task, because the predictions are very structured...

Main idea is to split domain adaption in image space into easy and hard tasks. this is the 'curriculum' idea as per title.

## Easy tasks:
- predicting label distributions, i.e. percentage of pixels belonging to each class.
- predict superpixel (coarse segmetnation)

## Hard tasks:
- pixelwise semantic segmentation (final objective)

## Loss functions
The overall loss function is just cross entropy loss on the source images plus the 2 novel 'easytasks'(label distributions and superpixel) on the target images.

## Details
### Predicting label distributions on target images
- Since do not have labels for target domain, instead use a CNN + Log regression classifier trained on *Source Domain*, apply directly on target domain to predict label distributions.
- Another way is search in source dataset for some nearest neighbours of a target image, and use the mean of the nearest neighbours' label distros as the target label distribution.
- Linear spectral clustering is used to segment each image into 100 superpixels. Linear SVM trained on source domain to classify superpixels into dominant class. Keep top 60% of superpixels as the landmark superpixels in the target domain to be used in the training loss.
- The way of computing label distributions of superpixel on target domain seems quite complicated... use a FCN trained on PASCAL to get the class labels, then do averaging....transfer idk.


[code](https://github.com/YangZhang4065/AdaptationSeg)
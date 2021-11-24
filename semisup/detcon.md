# Efficient Visual Pretraining with Contrastive Detection

This paper introduces the DETCON objective (contrastive detection), to be used for unsupervised **PRE-TRAINING**. SHould be considered a transfer learning/ semi-supervised technique. 

Main claims are that this objective can achieve the same performance (accuracy) despite requiring significantly less computation in training (one order of magnitude) than SOTA unsupervised methods.

### Main steps:
1. Use unsupervised segmentation techniques based on grouping, clustering to approximate the object instances in the image.
2.  Take two local views(crops) from one image and augment them. Corresponding masks from step 1 are similarly processed.
3.  Pass the two views to a feature extractor (ResNet-50), to form a feature map of (7 x 7) size, 2048 channels. Downsize the corresponding mask image as well to 7x7 using average pooling
4.  Mask the feature map and pass each one through a two layer MLP, this will give a final latent vector
5.  Apply DetCon objective to the two latent vectors.

### DetCon Objective details:
DetCon starts with a contrastive loss (simple explanation [here](https://towardsdatascience.com/contrastive-loss-explaned-159f2d4a87ec)). To expand on that, there are two main additions to formulate the DetCon loss:
1. A large set of 16 masks are sampled at each training iteration. Following that, the similarities between each pair of mask/image are densely evaluated. (Not super clear on this but I think it's basically taking 16 'crops' which are augmented differently, happens in step 2 of the [main steps](###main-steps:)


[code](https://github.com/deepmind/detcon) (tensorflow unfortunately)



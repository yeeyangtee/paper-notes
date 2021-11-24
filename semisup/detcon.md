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
1. A large set of 16 masks are sampled at each training iteration. Following that, the similarities between each pair of mask/image are densely evaluated. (Not super clear on this but I think it's basically taking 16 'crops' which are augmented differently, happens in step 2 of 'Main steps'. Also, try to choose crops/masks that contain objects that are as diverse as possible. 
2. Mask out the loss such that similarity in the contrastive loss is only computed on regions that are the same object (determined by the binary masks.)

### Segmentation methods to generate masks for step 1:
Few methods to automatically generate masks that semantically segment different objects are covered, will just list them out.
1. Spatial heuristic (just split image into regular grids)
2. Image computable, [Felzenszwalb Huttenlocher](http://people.cs.uchicago.edu/~pff/papers/seg-ijcv.pdf) method (seems to work the best.)
3. [Multiscale combinatorial Grouping](https://arxiv.org/abs/1503.00848)
4. Human annotated (obviously not unsupervised)



[code](https://github.com/deepmind/detcon) (tensorflow unfortunately)



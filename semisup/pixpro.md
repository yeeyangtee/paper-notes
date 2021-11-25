# Propagate Yourself: Exploring Pixel-Level Consistency for Unsupervised Visual Representation Learning

Tackles task of unsupervised representation learning. Similar to detcon/SIMCLR/BYOL. But this one is specifically for pixel-level applications such as semantic segmentation!

The main idea is to modify contrastive loss into a pixel-level loss instead of an image-level loss. DetCon takes a step in this direction by using masking of objects in the contrastive loss, PixPro here does it literally pixel-by pixel. 

First concept: *PixContrast*
- Take two crops of the image that contain pixel A.
- Pass the two crops through feature extractors.
- Two output features are used to form positive training pairs,
- While features obtained from different pixels form negative pairs.

Second concept: *PixPro* (pixel-to-propagation consistency)
- similarly take two crops.
- Pass the two crops through different pipelines instead.
- One is a standard feature extractor, other has a unique pixel propagation module (PPM)
- PPM filters a specific pixel's features by propagating features of similar pixels to it (???)






[official code](https://github.com/zdaxie/PixPro)  
[code 2](https://github.com/lucidrains/pixel-level-contrastive-learning)
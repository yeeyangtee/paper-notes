# Simplified unsupervised image translation for semantic segmentation adaptation

## Problem
- SUIT aims to solve the problem of unsupervised domain adaptaion for segmentation. Essentially, how to use the training data (img+pixelwise labels) from one dataset to train a segmentation model that performs well for another dataset.
- Usually, slight differences in target dataset can lead to great errors in segmentation performance. This paper is in the context of cityscape, i.e. predicting segmentation maps of cities/road etc. 
- Many people use the GTA5 <> cityscape as their experiments whereby GTA5 is the source dataset with a large number of near perfect annotations - this is generated by the game engine. The challenge is how to use knowledge learnt from GTA5 dataset to get good performance on cityscapes?

## Main ideas/ Summary
- Use I2I translation to transform source to target in image space
- Downstream segmentation network is trained to predict labels on transformed images. Labels are enforced to be the same as the labels of the source image, this preserves content information. This part is called the *semantic loss*.
- Source and Transformed images are passed through pre-trained network to extract features. Features are enforced to be similar through the *content loss*.
- Semantic and content loss are used to train the generator network.
- Segmentation network is trained to predict on BOTH source AND transformed image, with target labels being the labels of the source image. This is the *task loss*. This part is pretty weird/interseting, might be restricted to domains that are very similar! Need to try.

## Whats new:
Points are with comparison/ reference to CyCADA
- Only have source to target generator model, removed cycle consistency loss. The 2 main reasons for this is to reduce memory constrains during training (Don't need another entire G and D network), and also to amke the traing process easier.
- Without the cycle consistency, they are saying that using the semantic content consistency loss (use segmentation network) will enforce the shape consistencies.

## Some small stuff to note for implementation
- Generator is using typical encoder/decoder with res blocks. They add in Instance normalization at each layer.
- Discriminator uses Spectral Norm at each layer
- They tested with average weight/ aggregation of model paramters during training and show that it helps a little.
- Segmentation network used is FCN8/VGG-16 
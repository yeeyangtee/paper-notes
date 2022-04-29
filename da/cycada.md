# CyCADA: Cycle-Consistent Adversarial Domain Adaptation

problem: domain adaptation fails in naive situation, specifically, segmentation of traffic images by a model trained on **real traffic images** acheive 93% accuracy, but drops to 54% if **trained only on synthetic images** from game engines.

initial thoughts: This actually seems more sike than SUIT method even though it's 2 years older. lol.

## Existing solutions:
- Feature space alignment, which uses some similarity or distance measure (e.g. maximum mean discrepancy/ correlation distance/ discriminator accuracy) between the feature distributions of source and target domain. These aren't great because it doesn't enforce semantic consistency (e.g. target features of car can be mapped/aligned to source features of a bicycle.)
- Image space/ pixel-wise alignment. CycleGAN is part of this, wasn't designed to account for downstream task of segmentation but only for producing visually compelling transformations. Similarly, semantics might not be preserved with such techniques.

## What's new:
- CyCADA claims to adapt representations at both pixel-level and feature-level while enforcing the semantic content to be the same.
- Structural consistency is done using cycle consistency loss (CycleGAN)
- Semantic consistency is done using a semantics loss, which is based on the task. So for segmentation this would be a segmentation network (FCN is used here).

## Main losses:
- Cycle consistency loss, pretty much cycleGAN, for source <> target transforamtion.
- Feature discriminator loss, which matches the extracted feature distributions of the transformed source>target img and real target images.
- Semantic consistency loss, using one segmentation network to extract label maps from source and target images, these two should align.
- GAN loss, fake target domain should look like real target domain through discriminator.


## Implementation (page 5):
- Implementation is done in stages due to lack of GPU memory at the time this was published
- First train image translation network (cycleGAN)
- Next, use transformed source data (fake target) with the source labels to train a segmentation (task) model.
- Do another round of adaptation between fake target and actual targets, using features from intermediate layers of task model (not sure how this is done concretely)
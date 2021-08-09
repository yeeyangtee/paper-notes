# ADVENT: Adversarial Entropy Minimization for Domain Adaptation in Semantic Segmentation

Tackling the task of unsupervised domain adaptation. Transferring knowledge learnt from a source domain/dataset to get good segmentation performance on a different target dataset.

Main problem is that most existing methods produce overconfident (low entropy) predictions on images that are similar to source domain, but give under-confident (high entropy) predictions on target domain.

## Main idea
- Use unsupervised entropy loss for target domain. Exact loss is shannon entropy, which is minimised. This enforces the segmentation model to produce high confidence predictions on the target domain. For source domain standard supervised segmentation loss (cross entropy) is used.
- Use adversarial losses on the entropy maps also, to preserve the structural consistency of each image. First loss is only concerned with the overall entropy value of each image.



[code](https://github.com/valeoai/ADVENT)
# Scale variance minimization for unsupervised domain adaptation in image segmentation

Task: unsupervised domain adaptation for downstream improving semantic segmentation.

Simplified: train model on labelled dataset (source domain) and then leverage the info learnt on the source domain to achieve a good performance ona n unlabelled dataset in the target domain.

Main ideas that allow UDA to happen are:
- minimising the interdomain discrepency using adversarial learning. A segmentation model (*F*) is trained as a domain-invariant feature extractor on source and target domains, essentially we want to extract the segmentation maps.
- Adversarial losses minimise inter-domain discrepancy but its not stable due to the nature of adversarial training. The domain alignment suffer when the base semantic structures are altered.
- This work introduces a scale invariance loss. Essentially *F* should give the same semantic segmentation prediction on resized versions of the same input image (coming from target domain) since this is where the semantic structures can get affected (because dont have ground truth labels.)
- 
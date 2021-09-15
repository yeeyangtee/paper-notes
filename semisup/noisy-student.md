# Self-training with Noisy Student improves ImageNet classification

The noisy student approach can be summed up as follows:
- Train a teacher model on labeld images
- Use trained teacher to generate pseudo labels on unlabeled images
- Train student model on combination of labeled and pseudo labeled images.
- Repeat by replacing teacher with student model (update pseudo labels) and re-training a new student.

The main contributions that bring about the improvements are:
- Student model is larger or equal size to teacher model so that it can better learn from the larger unlabeled dataset.
- Noise such as RandAugment, dropout and stochastic depth is added to student model training.

[code](https://github.com/google-research/noisystudent)

# MixMatch: A Holistic Approach to Semi-Supervised Learning

Mixmatch combines 3 of the main ideas in SSL into one single loss term. The 3 concepts are:
- consistency regularisation. make the classifier predict the same result despite applying different augmentations or transformations to the same input.
- entropy minimisation. this requires classifiers to ouput low entropy predictions on unlabelled (or any other) data. Mainly so that the final decision boundaries don't pass through high density regions.
- Standard regularisation.

Main steps:
- Data augmentation. This is done on both labelled and unlabelled.
- Label guessing. This is done on unlabelled data. An average guess is computed across K samples of differently augmented unlabelled data. This is used as a sort of artificial target in the loss term
- Sharpening. some math function that reduces the entropy of label distribution, not very sure on this.
- use mixup in a combination of above 3 things to train. (not super sure)

Losses: cross entropy for labelled set, multiclass Brier score for unlabelled set as its less sensitive to incorrect predictions, apparantly quite normal for unlabelled predictions.


[code](https://github.com/google-research/mixmatch)
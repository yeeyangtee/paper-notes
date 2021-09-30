# Unsupervised Data Augmentation for Consistency Training

### Intro/background
This one explores consistency training for semi-supervised learning. To recap, consistency training in this context allows for training on unlabeled data by enforcing the same (consistent) predictions on inputs that have been perturbed by some small noise. There are many ways to inject this noise: 1) Location - at input layer or at hidden state. 2) Type - additive gaussian, dropout, adversarial noises.

## Main idea
- Basically just applying RandAugment as the augmentation technique for semi-sup image classification. 
- There are some experiments on NLP but didn't look into that, same idea.
- Somehow is quite highly cited: probably because of the excellent performance improvements.


[code](https://github.com/google-research/uda)
# Rethinking Pre-training and Self-training
Using models pre-trained on imagenet is becoming a standard practice, no matter what vision application you are working on. Authors are questioning the effectiveness of doing it this way.

Going back to basics, I think main objective of doing pretrain/self train is to answer this question: how can we use information from one dataset to help my performance on another dataset. Usually the situation is that existing datasets have bigger quantity, quality compared to my own data. Also working under the assumption that the data contents are somehow transferrable.

Assuming we are using imagenet as the external dataset, in pretraining we **train** a model on imagenet, then finetune the model on my own application. Self training is I **train** a new model on my application, then do pseudo-label for imagenet, then use that to augment the training.

## Main conclusions
- Pretraining (self-supervised or fully supervised) might not always be useful for the paradigm of using external dataset to improve another task. Some examples are when heavy augmentation is used.
- Self-training scheme is pretty dope and works well consistently, can give improvement even when used alongside pretraining.
- Pre-trainig is definitely still advantageous in the 2 main situations: when you don't have sufficient quality data in your own task and when you are limited by compute resources.

[code](https://github.com/tensorflow/tpu/tree/master/models/official/detection/projects/self_training)
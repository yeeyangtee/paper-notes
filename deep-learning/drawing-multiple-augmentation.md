# Drawing Multiple Augmentation Samples Per Image During Training Efficiently Decreases Test Error

Main idea: Instead of only doing 1 augmentation for each input image (i think in 1 training **batch**), how about we do multiple augmentations per input image for each batch? This will essentially reduce the no.of unique samples in each minibatch but authors claim that this actually improves test accuracy. Lets see.

They define 'augmentation multiplicities' (AMs) which describes how many times each unique image is augmented in a mini batch. 2 ways to implement:
- Simply expand the batch size as AMs increase
- Keep batch size constant, hence no.of unique images per batch drops as AMs increase.

Why does this help to increase test accuracy?
- Mainly shown through empirical studies on imagenet. Higher AMs are shown to help test accuracy.
- Also discuss that this improvement is because the augmentation introduces bias. Whereas additional studies using the growing batch method show that variance introduced by data augmentation kind of decreases model performance. (Feels abit smoky but can refer to section 2 in the paper.)
# CutMix: Regularization Strategy to Train Strong Classifiers with Localizable Features

A very popular regularisation technique that seems to work well on many functions even outside of classification. The main idea is a sort of augmentation to force CNNs to pay more attention to less discriminative parts of an image, hence improving generalisation ability.

This draws inspiration from MixUp regularisation and also CutOut. Mixup can be done by interpolating two input images, then setting the label for the mixed image as 0.5 for each class involved. Cutout is just a regional dropout at the input layer, where a patch of the input image is removed.

Cutmix is done by patching in a region from image B onto image A. The percentage coverage of the input image determines the class labels. So if top left quarter of a dog image is replaced with cat image, label will be 0.25 cat, 0.75 dog. Simple idea.

Why does this work? Paper explains it in a manner that it takes the best of both worlds from cutout and mixup which makes sense. But didnt really have an intuitive explanation of the idea by itself.

[code](https://github.com/clovaai/CutMix-PyTorch)


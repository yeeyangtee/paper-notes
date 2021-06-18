# The Unreasonable Effectiveness of Deep Features as a Perceptual Metric

This paper looks at using the feature maps/intermediate outputs of deep networks such as VGG, GANs as a way to measure perceptual similarties between images. The nets could be trained for classification task or self-supervised networks. They show that using such metrics largely beats classic distance metrics by far! But it kind is just reinforcing other work like style transfer and image synthesis which are also using the feature maps for 'perceptual loss'.

Not much cool stuff, just extracting feature maps, comparing them by doing diff, some other functions to get a perceptual loss LPIPS. Can test this to compute IC image differences


[code](https://github.com/richzhang/PerceptualSimilarity)
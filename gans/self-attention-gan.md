# Self-Attention Generative Adversarial Networks

This work tries to solve the problem of local dependencies arising from convolutional operations in GANs. The local receptive field have caused problems such as dogs being generated with great fur texture but without defined/separate feet. 

It basically applies a self attention module to the generator and discriminator networks. Got great generation results in terms of FID and Inception score. But not much cool stuff here

Methods for stabilising training:
- spectral norm is applied to G and D.
- Use separate learning rates for G and D.

Read chain:
- Spectral normalization
- Self attention

[code](https://github.com/brain-research/self-attention-gan)
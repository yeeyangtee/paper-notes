# StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation

Key problem: many multi-domain models require a separate generator network to be trained for each PAIR of domain mapping. Essentially a N^2 cost where N=no. of domains.
StarGAN uses a single 'unified' generator to perform multi domain translation. One main assumption is that the domains are simpler in a sense, only relating to classifications. For example, different facial expressions are considered a multi domain problem.

## Key ideas/techniques:
- Add domain labels as input to the generator network. These are one-hot encoded labels! The domain labels are concatenated depth wise to the input image. 
- Domain label has a mask vector component such that G knows which part of the domain label to pay attention to. This allows starGAN to be trained using multiple datasets, because different datasets could have different domain label lengths)
- G produces fake images that has been transformed to the target domain. Perform reconstruction loss by passing through the same G, concatenating with the original domain label.
- Discriminator is trained with standard adversarial loss. There is an additional domain classification performed by the discriminator.

Interesting and highly cited work, but seems to be a little restrictive in the applications. Might only work well on visually/semantically similar images with well-defined labels.
There is also a v2 version, yet to read!

[code](https://github.com/yunjey/stargan)
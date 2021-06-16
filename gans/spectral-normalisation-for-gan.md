# SPECTRAL NORMALIZATION FOR GENERATIVE ADVERSARIAL NETWORKS

purpose of this is to stabilise training of GAN. Apply weight normalisation to discriminator network. The whole work is mainly base on this Lipschitz constant. The assumption is that D weights need to be constrained based on this L.constant, which would allow the 'boundedness of statistics' and lower the chance of training failure.

So this paper uses some matrix math to come up with a normalisation function for Discriminator weights that allow it to fulfil the L.constant contraint. Not gonna try to understand the math. [Pytorch has this layer](https://pytorch.org/docs/stable/generated/torch.nn.utils.parametrizations.spectral_norm.html#torch.nn.utils.parametrizations.spectral_norm) so its all cool.


Reading chain:
- what is lipschitz constant?
- Probably need to understand more deeply the math in WGAN to get this.

[code](https://github.com/pfnet-research/sngan_projection)
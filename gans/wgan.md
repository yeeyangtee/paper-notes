# Wasserstein GANs

Purpose of GANs is to generate a distribution that is as close as possible to natural data distribution. But normal GAN with adversarial loss TENDS to have very bad loss function (vanishing gradient when its close to the natural images, exploding gradients when its far from natural image distribution). This is one of the reasons for poor GAN training stability, hence WGAN is proposed as as way to make it more stable!

I think the 2 main differences in WGAN are:
- Wasserstein loss function. This uses the idea of Earth Mover ([Wikipedia](https://en.wikipedia.org/wiki/Earth_mover%27s_distance), [Blog](https://jonathan-hui.medium.com/gan-spectral-normalization-893b6a4e8f53)) distance to denote the 'distance' between generated data distribution and NATURAL distribution as the loss function. So just minimise this then you can make the two distributions close to one another. This loss function has very nice properties (continuous and reliable gradient) so ideally training more under this loss function will allow us to converge to matching distributions.
-  Because need to keep some Lipschitz constant as a constraint, weight clipping is done on the critic/discriminator for WGAN. Not sure on the details, but enforcing a Lipschitz constant means that you keep the maximum value of gradients within a certain limit. Similarly just to ensure stability.

Code is everywhere. Just a loss func mainly.

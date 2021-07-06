# Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks

one of the OG papers on I2I translation. CycleGAN handles transformation between unpaired images (dont have exact pixelwise correspondences), but of course need to be somwhat similiar. Some good contextual examples presented were:
- zebra <> horse
- night <> day scenery
- monet painting style <> real scenery

In order to learn this transformation two unpaired domains, 2 separate generator networks are trained. Main loss introduced is the cycle consistency loss, quite similar to reconstruction loss. Image from domain A is passed to G_B to transform to domain B. This fake B is passed again to G_A to transform back to domain A. This method allows for training on unlabelled/unpaired images! This loss is L1 loss.

Other losses:
- Adversarial loss that enforces realism/similarity of fake domain to the real images using discriminator.
- identity loss for preserving color composition between input and output... this essentially enforces G_A(A) = A.

[code](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix)
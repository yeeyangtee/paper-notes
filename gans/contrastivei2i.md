# Contrastive Learning for Unpaired Image-to-Image Translation

Explicitly defines I2I translation as a disentanglement problem: separate content (which we want to preserve) from the texture or style, which we want to change into the new domain. Usually style is enforced through discrminator/adversarial losses while content is enforced by cycle consistency/reconstruction losses.

Introduces another way to enforce that content remains preserved, using idea of contrastive learning. Image patches are sampled from the real input image. Corresponding patch in the same spatial location is selected from the fake sample and used as postiive sampled. Random patches from other locations in the real iage are used as negative samples.

These patches are passed through an encoder network + MLP, and then trained with a classifier loss (should be some sort of cross entropy). This encoder is weight-shared with the generator that is used to do the I2I translation. Essentially only one main G used. 

 very nice stuff!
 [code](https://github.com/taesungp/contrastive-unpaired-translation)
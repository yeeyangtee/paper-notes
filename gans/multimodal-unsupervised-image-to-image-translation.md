# MUNIT, Multimodal Unsupervised Image-to-Image Translation

Solves the one-to-one mapping problem of previous I2I methods such as cyclegan. For a given input, the translated output is always the same!

MUNIT starts with the assumption that images can be decomposed into Content and Style latent spaces. Content is represented as a feature map of similar size to input images, essentially storing the spatial information. Style is simply a latent vector that encodes domain specific properties such as texture, color.

The paper does experiements with images from domain A and B. Each domain has a Generator and Encoder network. Encoder maps each domain into C and S spaces. The 2 domains will share the C space, but have a unique S space. Individually, these are trained with a cycle consistency/reconstruction loss and also adversarial loss. To learn the cross-domain mappings, there is a cross domain reconstruction loss. Given inputs A and B, we reconstruct content A using style B and vice versa. The cross-domain translated images are trained with GAN loss vs the inputs A and B. Reconstruction loss on C and S is done by decomposing the cross-domain images. So the 'fake' image obtained from content A and style B should be encoded/decomposed well back into content A and style B.

nice visual results.


[code](https://github.com/nvlabs/MUNIT)
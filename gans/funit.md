# Few-Shot Unsupervised Image-to-Image Translation

Main goal is to perform unsupervised image translation between source and target class, without the model having been previously trained on images from target class. 3 main contributions, first is don't need to train on target class, second is only need to see a few images from target class to do inference, third is can encompass different types of target classes.

## Generator network
- Takes in one 'source' image and small amount, *K* of 'target' images from another class.
- Implemented using 2 encoders, one for content that acts on source, another for class that acts on target images.
- content one is standard. Class one will do normal encoding also, but take mean at the final encoding output over the sample dimension of *K* vectors.
- decoder is made up of AdaIN res blocks and upconv layers. This seems to act on the content latent vector. Class latent vector is fed to the AdaIN layers.


## Multitask discriminator
- Need special discriminator since there are many classes.
- discriminator output has length N for N source classes.
- Loss function only computed on the related output position instead of computing a typical N-class classification output.

## Losses
- Adversarial: GAN loss as above
- content reconstruction: feed in same image for source and target (singular), want to get back the same image.
- feature matching loss: regulariser, this is a L1 loss of features extracted from aggregated targeted images and the translated image.

Basically what is happening: learn a generator model that encodes 'style' across a small amount of target images, and simultaneously encode 'content' of a source image, feed this style vector to the decoder, transformed. 

visual results look quite insanely good!
[code](https://github.com/NVlabs/FUNIT) 
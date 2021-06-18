# Encoding in Style: a StyleGAN Encoder for Image-to-Image Translation

This is a generic I2I framework. Previous I2I stuff was pretty task-specific, so even tho they can do multi domain etc it was usually suitable only for a few tasks. Some examples that this framework can handle:
- StyleGAN inversion (reconstruction using stylegan + their novel encoder framework)
- facial frontalization
- super-res
- inpainting
- conditional synthesis (pix2pix/bicycle)

The main idea here seems to be using a pre-trained CNN (resnet) to extract feature maps. At certain layers, the feateure maps are fed to this 'map2style' network which is just a small convnet. This creates 18 target styles from the input image. Target styles are fed to different layers of a StyleGAN generator. This doesn't seem to work out of the box on the other tasks as claimed in the intro.

So reading on, for different tasks a slightly different approach is used. 
- Facial frontalization: train model with target image having random horizontal flips. This enforces the GAN to converge to a frontal pose
- Conditional generation: do style mixing on their encoder network with a randomly generated vector.


[code](https://github.com/eladrich/pixel2style2pixel)
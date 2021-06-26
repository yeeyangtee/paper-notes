# Image-to-Image Translation with Conditional Adversarial Networks

I think this is the OG of image 2 image (I2I) translation using GANs

## Motivation
Previous I2I research was very specific and suitable for single domain only. Custom loss functions need to be designed for different types of images... But actually we are all doing the same stuff, transform one pixel into another pixel. So why not just use a generic/high-level loss function that says: make the output image indistinguishable from what we want?? 

Perfect formulation for adversarial training, just that we add in a conditioning criteria in the form of an input image that we wish to transform.




[code](https://github.com/phillipi/pix2pix)
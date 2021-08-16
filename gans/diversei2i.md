# Diverse Image-to-Image Translation via Disentangled Representations

contains a good review on unsupervised i2i methods with intuitive graphics

## main idea
- disentangle content and attribute (style) of each image
- This is done using two different encoder networks per domain. 
- There is an assumption of shared content space across domains, which is enforced by the content discriminator. Content encoders from both domains learn to produce content vectors that are indistinguishable from one another.
- attributes space is regularised to unit normal distribution using KL divergence loss. This allows for multimodel generation of different attributes using random sampling at inference time
### cross cycle consistency:
forward translation is done using... from a non corresponding pair of X and Y, encode them, then do first translation by swapping attribute vectors. This completes the image translation of X>Y' and Y>X' while preserving the initial content.

Next, do the backward translation be encoding X' and Y', and swap attributes, do translation again. X > Y' > X'' , Y > X' > Y''. the final X'' and Y'' are enforced to be the same as original X and Y, called the cross cycle consistency loss.

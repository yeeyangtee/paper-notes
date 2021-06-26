# SegAN: Adversarial Network with Multi-scale L1 Loss for Medical Image Segmentation

Note: under DL even though it uses adversarial training since there's not really a generative component to this.

Quite an interesting idea, main thing was to use the MASKED input image as input to discriminator, then take D feature maps to compute a loss.

At first reminds me of the advsemisup paper but is not. Main ideas:
- Standard segmentation network (e.g. UNet) with the aim of producing a segmentation map.
- Loss function implemented by a critic network. Inputs to this are the ground truth mask * input image AND predicted masks * input image. Basically it will see a masked section of the input image.
- Multiscale loss is computed from feature maps of Critic network. This is computed by **Mean absolute error** between real and fake feature maps.
- Train in adversarial manner, alternate between Segment and Critic network, S tries to minimise, C tries to maximise.
- 

[code](https://github.com/YuanXue1993/SegAN)
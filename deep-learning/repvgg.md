# RepVGG: Making VGG-style ConvNets Great Again

Main claim is that using simple feedforward nets (i.e. VGG style) have better accuracy-speed tradeoff compared to other SOTA methods like Res/Reg/Efficient-NET.

## Main idea:
- Train with a resnet-like structure with identity and 1x1 conv branches
- At inference time, convert these identity and 1x1 convs into 'degraded' 3x3 convs and merge with the 3x3 conv (main branch) so inference network only has 3x3 convs and relus.
- This is named structural reparameterisation, and allows inference time network to perform same function with just convs + relus.
- 

## Interesting pointers:
- Many papers such as EfficientNET use TFLOPs as their main indication of efficiency. However TFLOP are not truly indicative of speed!
  - For example, VGG-16 has 8.4x FLOPs as EfficientNet-B3 but runs 1.8x faster on 1080Ti
  - This is due to FLOPS not taking into account other factors: memory access cost and degree of parallelism.
  - Stuff like Residual blocks at inference time require the intermediate outputs of each branch to be kept until the next addition/concat, which makes it very memory inefficient.
  - parallelism is lower in multi branch structures as there are multiple small operators at each layer, instead of few larger operations.
- 




[code](https://github.com/megvii-model/RepVGG)
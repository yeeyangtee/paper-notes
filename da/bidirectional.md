# Bidirectional Learning for Domain Adaptation of Semantic Segmentation

## Whats new:
- Bidirectional learning framework, where image translation and segmentation are seen as 2 modules. Use results from segmentation to improve IT models.
- Integrate Self supervised learning idea into the segmentation module. 

## Problem formulation:
Standard UDA for segmentation. Have source image and label, have target image. Want to train a model to predict on target.

## Main ideas:
**bidirectional learning**: 
- two modules: Image Translation (CycleGAN) and Segmentation Adaptation (Deeplab/FCN)
- Typical flow for UDA is train image translation, use outputs to train segmentation and done.
- For BDL, the results from segmentaiton model are used to feedback image translation model to improve it through a perceptual loss. 
- Then repeat the process (in expt they only do up to 2X)

**perceptual loss**:
- Computed as the L1 loss between segmentation output between A and fake_B, Also between A and reconstructed_A.
- This is added to the Overall loss term to train F.
- 




### Forward direction, translation-to-segmentation (T2S)
- self supervised approach.
- segmentation is trained on both synthetic and real data, real data no labels
- use prediction on real data as pseudo label (with confidence threshold)
- This self supervised is simply the same as semi-sup methods doing psuedo label.

### Backward direction, segmentation to translation (S2T)
- translation module is updated by segmentation model using a perceptual loss
- 


[code](https://github.com/liyunsheng13/BDL)
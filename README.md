Inspired by [Daniel Takeshi](https://github.com/DanielTakeshi/Paper_Notes)

Too many papers in DL/AI. Need some way to keep track of skimmed papers. Highlighting/annotating PDFs don't work too well for me so gonna try this.

This repo holds the notes for papers that I've read. Previously did this in a MS word document but that got too messy and slow when I needed to refer back. Still have yet to port over most of the past readings. Score is a number from (1) to (5) where 1 is just a quick skim through and 5 is complete understanding of the whole paper including all equations and reading chains.

## TOC:
- [Deep Learning](#deep-learning)
  - [2022](#2022)
  - [2021](#2021)
  - [2020](#2020)
  - [2019](#2019)
  - [2018](#2018)
  - [2017](#2017)
  - [2014](#2014)
- [Generative Adversarial Networks](#generative-adversarial-networks)
  - [2021](#2021-1)
  - [2020](#2020-1)
  - [2019](#2019-1)
  - [2018](#2018-1)
  - [2017](#2017-1)
  - [Rest](#rest)
- [Domain Adaptation](#domain-adaptation)
- [Semi-supervised and Self-supervised Learning](#semi-supervised-and-self-supervised-learning)
- [IC focused Deep Learning | IC related stuff](#ic-focused-deep-learning--ic-related-stuff)
- [Reinforcement Learning](#reinforcement-learning)
  - [Articles](#articles)


## Formatting guide for this index page:
- Name[Link to notes], Source/Conf/Journal [link to source], Year, Misc Source(Optional), Score

# Deep Learning
Generic papers on DL that don't fit into the other categories.

## 2022
- [CADTransformer](https://github.com/yeeyangtee/paper-notes/blob/master/ic/cadtransformer.md), CVPR 2022

## 2021
- [CAPTURE the Bot](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/capture-adversarial-captcha.md): Using Adversarial Examples to Improve CAPTCHA Robustness to Bot Attacks
: [IEEE IS](https://ieeexplore.ieee.org/document/9257172) 2021 (3)
- DINO
- torch.manual seed(3407) is all you need: On the influence of random seeds in deep learning architectures for computer vision, [arXiv](https://arxiv.org/abs/2109.08203) 2021
- [RepVGG](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/repvgg.md): Making VGG-style ConvNets Great Again, [CVPR](https://arxiv.org/abs/2101.03697) 2021 (3)
- [Rethinking "Batch" in BatchNorm](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/rethinking-batch-in-batchnorm.md), [Review](https://arxiv.org/abs/2105.07576) 2021 FacebookAI (1) 
- [Drawing Multiple Augmentation Samples Per Image During Training Efficiently Decreases Test Error](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/drawing-multiple-augmentation.md), [Preprint](https://arxiv.org/abs/2105.13343) 2021 DeepMind (3)

## 2020
- [Once For All: Train one network and specialize it for efficient deployment](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/once-for-all-train-one-network-and-specialize-it-for-efficient-deployment.md), [ICLR](https://arxiv.org/pdf/1908.09791) 2020 (2)
- [Rethinking Pre-training and Self-training](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/rethinking-pretraining-and-self-training.md), [NIPS](https://proceedings.neurips.cc/paper/2020/file/27e9661e033a73a6ad8cefcde965c54d-Paper.pdf) 2020 (2)
- [Bootstrap Your Own Latent A New Approach to Self-Supervised Learning](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/bootstrap-your-own-latent.md), [NIPS](https://arxiv.org/abs/2006.07733) 2020 (3)


## 2019 
- [CCNet](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/criss-cross-attention-segmentation.md): Criss-Cross Attention for Semantic Segmentation, [ICCV](https://arxiv.org/abs/1811.11721) 2019 (4)
- [CutMix](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/cutmix-regularization.md): Regularization Strategy to Train Strong Classifiers with Localizable Fatures, [ICCV](https://openaccess.thecvf.com/content_ICCV_2019/html/Yun_CutMix_Regularization_Strategy_to_Train_Strong_Classifiers_With_Localizable_Features_ICCV_2019_paper.html) 2019 (4)

## 2018
- [The Unreasonable Effectiveness of Deep Features as a Perceptual Metric](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/effectiveness-deep-features-perceptual-metric.md), [CVPR](https://arxiv.org/abs/1801.03924) 2018 (4)
- [SegAN](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/segan_adversarial_multiscale_loss_medical_segmentation.md): Adversarial Network with Multi-scale L1 Loss for Medical
Image Segmentation, [Neuroinformatics](https://link.springer.com/article/10.1007/s12021-018-9377-x) 2018 (4)

## 2017
- [Neural Architecture Search with Reinforcement Learning](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/neural-architecture-search-with-reinforcement-learning.md), [ICLR](https://arxiv.org/abs/1611.01578) 2017
- [Attention is All you need](https://github.com/yeeyangtee/paper-notes/blob/master/deep-learning/attention-is-all-you-need.md), [NIPS](https://arxiv.org/abs/1706.03762) 2017 (2)

## 2014
- Neural Machine Translation by Jointly Learning to Align and Translate, [ICLR](https://arxiv.org/abs/1409.0473) 2015 

# Generative Adversarial Networks
Any GAN related stuff. Image 2 Image translations, super-res etc. I put VAE related stuff here too since they are mostly used for generative purposes or thats what I read them for.

## 2021
- [Im2Vec](https://github.com/yeeyangtee/paper-notes/blob/master/gans/im2vec.md): Synthesizing Vector Graphics without Vector Supervision, [CVPR](https://openaccess.thecvf.com/content/CVPR2021/html/Reddy_Im2Vec_Synthesizing_Vector_Graphics_Without_Vector_Supervision_CVPR_2021_paper.html) 2021 (4)
- [Encoding in Style: a StyleGAN Encoder for Image-to-Image Translation](https://github.com/yeeyangtee/paper-notes/blob/master/gans/encoding-in-style.md), [CVPR](https://arxiv.org/abs/2008.00951) 2021 (4)

## 2020
- [Contrastive Learning for Unpaired Image-to-Image Translation](https://github.com/yeeyangtee/paper-notes/blob/master/gans/contrastivei2i.md), [ECCV](https://arxiv.org/abs/2007.15651) 2020


## 2019
- [SAGAN](https://github.com/yeeyangtee/paper-notes/blob/master/gans/self-attention-gan.md): Self-Attention Generative Adversarial Networks, [PMLR](https://proceedings.mlr.press/v97/zhang19d.html) 2019 (4)
- [Few-Shot](https://github.com/yeeyangtee/paper-notes/blob/master/gans/funit.md) Unsupervised Image-to-Image Translation, [ICCV](https://arxiv.org/abs/1905.01723) 2019 (2)

## 2018
- [Spectral Normalisation for GANs](https://github.com/yeeyangtee/paper-notes/blob/master/gans/spectral-normalisation-for-gan.md), [ICLR](https://arxiv.org/abs/1802.05957), 2018 (1)
- [Multimodal Unsupervised Image-to-Image Translation](https://github.com/yeeyangtee/paper-notes/blob/master/gans/multimodal-unsupervised-image-to-image-translation.md), [ECCV](http://openaccess.thecvf.com/content_ECCV_2018/papers/Xun_Huang_Multimodal_Unsupervised_Image-to-image_ECCV_2018_paper.pdf) 2018 (3)
- [StarGAN](https://github.com/yeeyangtee/paper-notes/blob/master/gans/stargan.md): Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation, [CVPR](http://openaccess.thecvf.com/content_cvpr_2018/papers/Choi_StarGAN_Unified_Generative_CVPR_2018_paper.pdf) 2018 (3)
- [Diverse](https://github.com/yeeyangtee/paper-notes/blob/master/gans/diversei2i.md) Image-to-Image Translation via Disentangled Representations, [ECCV](https://arxiv.org/abs/1808.00948) 2018

## 2017
- [Vector Quantized-VAE, Neural Discrete Representation Learning](https://github.com/yeeyangtee/paper-notes/blob/master/gans/vq-vae.md), [NIPS](https://arxiv.org/abs/1711.00937) 2017 Deepmind (3)
- [Wasserstein GAN](https://github.com/yeeyangtee/paper-notes/blob/master/gans/wgan.md), [PMLR](https://arxiv.org/abs/1701.07875) 2017 (2)
- [pix2pix](https://github.com/yeeyangtee/paper-notes/blob/master/gans/pix2pix.md): Image-to-Image Translation with Conditional Adversarial Networks, [CVPR](https://phillipi.github.io/pix2pix/) 2017 (5)
- [CycleGAN](https://github.com/yeeyangtee/paper-notes/blob/master/gans/cyclegan.md): Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks, [ICCV](https://arxiv.org/abs/1703.10593) 2017 (5)
- [UNIT](https://github.com/yeeyangtee/paper-notes/blob/master/gans/unit.md), Unsupervised Image-to-Image Translation Networks, [NIPS](https://arxiv.org/abs/1703.00848) 2017 (3)


## Rest
- OG GAN from Goodfellow
- DCGAN
- [Variational Autoencoders](https://github.com/yeeyangtee/paper-notes/blob/master/gans/vae.md), [Paper](https://arxiv.org/abs/1312.6114), 2014 (2)
- 
- Pix2Pix
- CycleGAN

# Domain Adaptation
- [An introduction to domain adaptation and transfer learning](https://github.com/yeeyangtee/paper-notes/blob/master/da/da-tl-review.md), [Review](https://arxiv.org/abs/1812.11806) Paper 2018
- [Unsupervised Domain Adaptation](https://github.com/yeeyangtee/paper-notes/blob/master/da/uda-segmentation-review.md) in Semantic Segmentation: a Review, [Review](https://www.mdpi.com/2227-7080/8/2/35) Paper 2020
- [A Closer Look at Domain Shift for Deep Learning in Histopathology](https://github.com/yeeyangtee/paper-notes/blob/master/da/domain-shift-histopathology.md), [MICCAI](https://arxiv.org/abs/1909.11575) (WORKSHOP) 2019
- [Curriculum Domain Adaptation for Semantic Segmentation of Urban Scenes](https://github.com/yeeyangtee/paper-notes/blob/master/da/curriculum-da.md) [ICCV](https://openaccess.thecvf.com/content_iccv_2017/html/Zhang_Curriculum_Domain_Adaptation_ICCV_2017_paper.html) 2017 (3)
- [ADVENT](https://github.com/yeeyangtee/paper-notes/blob/master/da/advent.md): Adversarial Entropy Minimization for Domain Adaptation in Semantic Segmentation, [CVPR](https://arxiv.org/abs/1811.12833) 2019 (1)
- [Simplified unsupervised image translation for semantic segmentation adaptation](https://github.com/yeeyangtee/paper-notes/blob/master/da/suit.md), [Pattern Recognition](https://www.sciencedirect.com/science/article/abs/pii/S0031320320301461) 2020 (3)
- [Scale variance](https://github.com/yeeyangtee/paper-notes/blob/master/da/scale-variance-min.md) minimization for unsupervised domain adaptation in image segmentation, [Pattern Recognition](https://www.sciencedirect.com/science/article/abs/pii/S0031320320305677) 2021 (1)
- [Bidirectional](https://github.com/yeeyangtee/paper-notes/blob/master/da/bidirectional.md) Learning for Domain Adaptation of Semantic Segmentation, [CVPR](https://arxiv.org/abs/1804.05827) 2019, 
- [CyCADA](https://github.com/yeeyangtee/paper-notes/blob/master/da/cycada.md): Cycle-Consistent Adversarial Domain Adaptation, [PMLR](https://arxiv.org/abs/1711.03213) 2018

# Semi-supervised and Self-supervised Learning
- [Unsupervised Data Augmentation](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/unsup-data-augment.md) for Consistency Training, [NIPS](https://arxiv.org/abs/1904.12848) 2020 (4)
- [Self-training](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/noisy-student.md) with Noisy Student improves ImageNet classification, [CVPR](https://openaccess.thecvf.com/content_CVPR_2020/html/Xie_Self-Training_With_Noisy_Student_Improves_ImageNet_Classification_CVPR_2020_paper.html) 2020 (2)
- [MixMatch](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/mixmatch.md): A Holistic Approach to Semi-Supervised Learning, [NIPS](https://arxiv.org/abs/1905.02249) 2019 (2)
- [Towards Annotation Efficient Segmentation via Image to Image Translation](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/semi-segment-i2i.md), [IEEE T-MI](https://arxiv.org/abs/1904.01636) 2020 (1)
- [DIVIDEMIX](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/dividemix.md): LEARNING WITH NOISY LABELS AS SEMI-SUPERVISED LEARNING , [ICLR](https://arxiv.org/abs/2002.07394) 2020 (2)
- [Efficient Visual Pretraining with Contrastive Detection](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/detcon.md), [ICCV](https://arxiv.org/abs/2103.10957) 2021
- [PixPro](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/pixpro.md), Propagate Yourself: Exploring Pixel-Level Consistency for Unsupervised Visual
Representation Learning, [CVPR](https://arxiv.org/abs/2011.10043) 2021
- [SimCLR](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/simclr.md): A Simple Framework for Contrastive Learning of Visual Representations, [ICML](https://arxiv.org/abs/2002.05709) 2021
- [Self-supervised learning](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/ssl-fair.md): The dark matter of intelligence, [FAIR Blog](https://ai.facebook.com/blog/self-supervised-learning-the-dark-matter-of-intelligence/), 2021
- [GATO](https://github.com/yeeyangtee/paper-notes/blob/master/semisup/gato.md): A Generalist Agent, [DeepMind](https://www.deepmind.com/publications/a-generalist-agent), 2022


# IC focused Deep Learning | IC related stuff
- [Logo Classification and Data Augmentation](https://github.com/yeeyangtee/paper-notes/blob/master/ic/logo-dataaug-pcb.md) Techniques for PCB Assurance and Counterfeit Detection, [ISTFA](https://dl.asminternational.org/istfa/proceedings-abstract/ISTFA2021/84215/12/18241) 2021
- [PCB Component](https://github.com/yeeyangtee/paper-notes/blob/master/ic/pcb-detection-cv.md) Detection Using Computer Vision for Hardware Assurance, [Big Data and Cognitive Computing](https://www.mdpi.com/2504-2289/6/2/39) 2022
- [REFICS](https://github.com/yeeyangtee/paper-notes/blob/master/ic/refics.md): Assimilating Data-Driven Paradigms Into Reverse Engineering and Hardware Assurance on Integrated Circuits, [IEEEAccess](https://ieeexplore.ieee.org/abstract/document/9543688) 2021
- [Generative Adversarial Network](https://github.com/yeeyangtee/paper-notes/blob/master/ic/synthetic-sem-dataset-gan.md) for Integrated Circuits Physical Assurance Using Scanning Electron Microscopy, [IPFA](https://ieeexplore.ieee.org/document/9617416) 2021
- [IC SynthLogo](https://github.com/yeeyangtee/paper-notes/blob/master/ic/ic-synth-logo.md): A Synthetic Logo Image Dataset for Counterfeit and Recycled IC detection, [IPFA](https://ieeexplore.ieee.org/document/9617352) 2021
- [Segmentation of Integrated Circuit Layouts from Scan Electron Microscopy Images](https://github.com/yeeyangtee/paper-notes/blob/master/ic/segmentation-of-layout-from-sem.md), [CCECE](https://ieeexplore.ieee.org/document/8447878) 2018

# Reinforcement Learning
Not really my focus but its a topic I find to be real cool. Somehow this is integrated with alot of DL work in general nowadays also, so better to know abit. Mainly will be reading articles or summaries by other people instead of the actual paper, just to get an intuitive idea and save time.

## Articles
- [An Intuitive Explanation of Policy Gradient](https://github.com/yeeyangtee/paper-notes/blob/master/reinforcement-learning/an-intuitive-explanation-of-policy-gradient.md)
, [Article](https://towardsdatascience.com/an-intuitive-explanation-of-policy-gradient-part-1-reinforce-aa4392cbfd3c) on policy gradient rule by Adrien Lucas Ecoffet
- [Going Deeper Into Reinforcement Learning: Understanding Deep-Q-Networks](https://github.com/yeeyangtee/paper-notes/blob/master/reinforcement-learning/going-deeper-into-reinforcement-learning-understanding-deepq-networks), [Blog Post](https://danieltakeshi.github.io/2016/12/01/going-deeper-into-reinforcement-learning-understanding-dqn/) from [Daniel Taskeshi](https://danieltakeshi.github.io/).
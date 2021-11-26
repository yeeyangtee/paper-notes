# A Simple Framework for Contrastive Learning of Visual Representations

Main outcome: contrastive learning which is a form of unsupervised learning. This allows the learning of important visual representations from unlabelled images, output is a trained backbone model to be applied for other vision tasks.

Main ideas behind contrastive learning:
1.  Two crops from one image should yield similar features. (positive samples)
2.  Different images should yield different features. (negative samples)
3.  Contrastive loss maximises similarity of 1 and minimises similarity of 2.


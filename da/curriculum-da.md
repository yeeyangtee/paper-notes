# Curriculum Domain Adaptation for Semantic Segmentation of Urban Scenes

split domain adaption into easy and hard tasks.
easy tasks:
- predicting label distributions, i.e. percentage of pixels belonging to each class.
- predict superpixel (coarse segmetnation)

Hard tasks:
- pixelwise semantic segmentation (final objective)

loss function is just cross entropy loss on the source images, and the 2 novel losses (easytasks) on the target images.



# bootstrap your own latent

task is self-supervised representation learning. basically without labels, learn some encoding or representation of a particular image dataset. Contrastive learning is one way that performs pretty well on this, which has similar idea to this paper. However this BYOL does not require any negative samples for training. This part is quite SUS because it essentially leaves the possibility of the network optimising to latent vector = 0 since thats technically the ideal solution.

The main idea of contrastive learning approach:
- For each image, you make some augmentation.
- Feed both through encoder network 
- Loss function will enforce that the output latent vectors are the same for the same input image.
- Essentially your encoder which self-learns the representation does this by being able to IGNORE the augmentations performed. This means it is **SUPER** important that the augmentations are designed properly, since that is what you want the network to 'throw away'

Main differences in BYOL:
- Employ the idea of teacher-student/ target-online networks. Target net weights is an EMA of the online network 
- With 2 augmentations, one is passed thru target net and one is passed through online network. 
- Somhow there is an additional projection step that changes the dimensionality of the representation/latent vector. But don't really see the use of this, can just add it to the end of the main encoder network? 

comments:
- authors admit that there could be hypothetically undesirable equilibria, but they dont encounter this.
- Done by google bois so they use stuff like BS=4096, train on 512 cores which is impossible for us plebs. So will be hard to exactly replicate the results.

[code](https://github.com/deepmind/deepmind-research/tree/master/byol)


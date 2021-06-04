# Variational Autoencoders
Tons of resources on this, a very important fundamental technique in generative modelling.
- [Blog 1](https://towardsdatascience.com/understanding-variational-autoencoders-vaes-f70510919f73), Good intuitive explanation
- [Blog 2](https://jaan.io/what-is-variational-autoencoder-vae-tutorial/), More mathematically focused.

Main idea: 
- We want to compress input data (call it x) into a smaller latent space (call it z). Then subsequently be able to decode it well. 
- PCA sounds good for this, but many limitations. There are nonlinear methods as well, which are autoencoders implemented using neural nets. 
- Problem with autoencoder is that the latent space usually has no useful property other than just to store the data. 
- For VAE we output a probability distribution as the latent space. (usually gaussian, so output the mean and variance) 
- To decode, a latent **vector** is sampled from the latent **distribution** and then passed to the decoder.
- This latent distribution is constrained by doing KL divergence with unit normal gaussian. Somehow doing this forces the encoder network to map inputs to Z in the most efficient way, and usually this means similar inputs in x space will be close in z space as well.

Key Implementation details:
- Reconstruction loss between input X and reconstructed D(E(X))
- KL divergence loss between Z = E(X) and unit gaussian.
- Do reparameterisation trick by multiplying var with z sampled from unit gaussian first and add mean so that outputs of encoder (mean,var) can be backpropped.

Don't understand the full mathematical derivation yet



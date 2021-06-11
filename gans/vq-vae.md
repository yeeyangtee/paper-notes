# Vector Quantized Variational Autoencoders
Variation of VAE that uses discrete latent space instead of gaussian distribution.
By deepmind, DALL-E, cool stuff. Yet to read all.
Good blog posts:
- [Blog 1](https://ml.berkeley.edu/blog/posts/vq-vae/), from berkeley 
- [Blog 2](https://blog.usejournal.com/understanding-vector-quantized-variational-autoencoders-vq-vae-323d710a888a)

Main idea:
Instead of using continuous space for latent variable, use a discrete representation. This is more intuitive and representative of real world data such as speech (discrete sequence of phenomes) and images (discrete objects).

Main steps:
- All possible latent variables are stored in a codebook. 
- At each spatial position, the encoder produces one latent variable. 
- Encoded latent variable is converted to the closest one in codebook through argmin of L2 distance. (NON Differentiable, but just remove argmin by setting this codebook vector to 1, others to 0).
- Limited no. of codebook vectors but the latent space has spatial dimensions, so at each 'pixel' of the encoded variable there can be a different latent vector.

How to learn codebook vectors:
This is basically summed up in their loss function. 3 terms. 
1. Reconstruction Loss (Same as VAE)
2. Codebook alignment loss. L2 loss from encoder output and nearest codebook vector. Gradients are not propagated through encoder network.
3. Codebook commitment loss. Same as (2) BUT gradients are propagated thru encoder network, don't affect codebook. 
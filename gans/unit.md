# Unsupervised Image-to-Image Translation Networks

problem to be solved is identical to cyclegan (same title lol)

starting point of approach is different. UNIT uses the shared-latent space assumption. which is that for a pair of images A and B from different domains, they have a shared latent code z.

## main idea/steps
- Have 2 encoder, 2 generator, 2 discriminator networks. E+G together is similar to the generators in cycleGAN
- weight sharing between last few layers of encoder and first few layers of generator.
- Training loops include reconstruction loss of A vs G1(E1(A))
- Discriminator loss of B vs G2(E1(A))

[code](https://github.com/mingyuliutw/unit)
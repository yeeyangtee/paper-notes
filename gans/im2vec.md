# Im2Vec: Synthesizing Vector Graphics without Vector Supervision

This is a end to end vector synthesis model, that only requires **plain, rastered** images for training, no need vector representations as ground truths to train. Essentially, it is unsupervised(no label) generation of vector graphics.

They identify 2 main problems with current methods for vector graphic synthesis:
1. Methods like SVG-VAE and DeepSVG require vector groundtruths for supervision, which is quite expensive to obtain.
2. Current approaches have a sequential generation assumption (similar to how humans draw these vector graphics). However this is an unnecessary/bad constraint > many different 'drawing sequences' can produce the same vectors!

The main idea of the im2vec model is to automatically decompose vector graphics into a set of filled curves/shapes, each shape will be parameterised as a Bezier path.

### Quite important statement that sums up the usage of bezier curves as vector paths, and linking that to the actual image through **differentiable** rasterizers and compositors.
"The key insight that allows the handling of arbitrary complexity is that we can treat any primitive closed shape as a deformation of a unit circle, which is modelled as 1D convolution
on samples from this circle conditioned on a common latent vector. By recombining these primitive paths through a differentiable rasterizer and differentiable
compositing, we can natively represent vector art while learning to generate it purely based on appearance, obviating the need for vector supervision."

## Approach
The whole framework is of course based on the reconstruction of input images. The main steps are:
1. Encode raster input image with encoder.
2. Pass to RNN to obtain *path latent codes* for individual shapes.
3. Decode each path latent code using **path decoder**, producing a vector output (Bezier path)
4. Rasterize the vector output.
5. Composit the rasterized shapes to get the reconstructed output.
6. Apply reconstruction loss which is backproppable through each of the above steps.

## Details
**Encoder**: Use a variational autoencoder to create a global latent code.

**RNN**: No idea, just produces a sequence of paths from the global latent code, each sequence is one shape. 

**Path Decoder**: Some mathematical basics needed here but mainly: 1) Sample some control points from a Unit circle. 2) Pass through 1D CNN to do resampling, which deforms the control points. 3) Pass through decoder to get the final bezier path. 

**Diff-able rasterizer and compositor**: Use DiffVG and DiffComp (existing methods)

**Modified reconstruction loss**: 
- Use a multi resolution loss because at early stages, convergence is slow
- Quote: When we differentiate O with respect to the B´ezier parameters, the gradients have a small area of influence, corresponding to the support of the rasterization prefiltering kernel. This adversely affects convergence especially when the mismatch between I and O is high
- An image pyramid is used, whereby a L2 reconstruction loss is computed on several downsampled versions of the images.
- Gradients at the coarsest levels are more stable, provide crucial signal when images differ by alot.
- Gradients at fine level allow us to obtain great spatial accuracy.

[code](http://geometry.cs.ucl.ac.uk/projects/2021/Im2Vec/)
# Im2Vec: Synthesizing Vector Graphics without Vector Supervision

This is a end to end vector synthesis model, that only requires **plain, rastered** images for training, no need vector representations as ground truths to train.

They identify 2 main problems with current methods for vector graphic synthesis:
1. Methods like SVG-VAE and DeepSVG require vector groundtruths for supervision, which is quite expensive to obtain.
2. Current approach have a sequential generation assumption (similar to how we humans draw these vector graphics). However this is an unnecessary/bad constraint > many different sequences can produc the same vectors!

The main idea of the im2vec model is to automatically decompose vector graphics into a set of filled curves/shapes, each shape will be parameterised as a Bezier path.

"The key insight that allows the handling of arbitrary complexity is that we can treat any primitive closed shape as a deformation of a unit circle, which is modelled as 1D convolution
on samples from this circle conditioned on a common latent vector. By recombining these primitive paths through a differentiable rasterizer and differentiable
compositing, we can natively represent vector art while learning to generate it purely based on appearance, obviating the need for vector supervision."
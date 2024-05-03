# Building Image Generation Using GauGANS

GauGAN uses a Generative Adversarial Network (GAN) to generate realistic images that are conditioned on cue images and segmentation maps

The main components of a GauGAN are:
# SPADE (aka spatially-adaptive normalization) 

The authors of GauGAN argue that the more conventional normalization layers (such as Batch Normalization) destroy the semantic information obtained from segmentation maps that are provided as inputs. To address this problem, the authors introduce SPADE, a normalization layer particularly suitable for learning affine parameters (scale and bias) that are spatially adaptive. This is done by learning different sets of scaling and bias parameters for each semantic label.

# Variational encoder

Inspired by Variational Autoencoders, GauGAN uses a variational formulation wherein an encoder learns the mean and variance of a normal (Gaussian) distribution from the cue images. This is where GauGAN gets its name from. The generator of GauGAN takes as inputs the latents sampled from the Gaussian distribution as well as the one-hot encoded semantic segmentation label maps. The cue images act as style images that guide the generator to stylistic generation. This variational formulation helps GauGAN achieve image diversity as well as fidelity.\

# Multi-scale patch discriminator 

 Inspired by the PatchGAN model, GauGAN uses a discriminator that assesses a given image on a patch basis and produces an averaged score.

 # Results
<img width="662" alt="Screenshot 2024-05-03 at 7 56 00 AM" src="https://github.com/heetmiyani/Building-Image-Generation-Using-GauGANS/assets/124970580/bdd88988-4ef3-4216-9fa7-5a50ae17be84">

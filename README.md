# Fashion GAN

A DCGAN trained on Fashion-MNIST to generate synthetic clothing images,
built as part of Siraj Raval's Machine Learning Bootcamp, October 2019.

## Architecture

Generator: Dense → Reshape → two UpSampling2D blocks with Conv2D and 
BatchNormalization → tanh output. Takes 100-dimensional noise vector, 
outputs 28×28 single-channel images.

Discriminator: Four Conv2D blocks with LeakyReLU, Dropout, and 
BatchNormalization → sigmoid binary output. Trained to distinguish 
real Fashion-MNIST samples from generator output.

Combined model freezes discriminator weights during generator training,
following standard GAN practice. Adam optimizer at lr=0.0002, 
beta_1=0.5 for both networks.

## Dataset

Fashion-MNIST — 60,000 training images across 10 clothing categories,
normalized to [-1, 1] for tanh compatibility.

## Status

Incomplete — architecture implemented and compiles, training loop
partially written. Not maintained.

The label dictionary remains the most carefully considered part of 
the codebase.

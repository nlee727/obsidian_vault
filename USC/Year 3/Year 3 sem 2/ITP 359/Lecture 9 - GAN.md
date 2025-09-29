- Neural network at the end to discriminate between real/generated image to help with training the generator
### What are GANs
VAE sampled from an organized latent space to have certain features
- GAN takes this idea a little further. Creates new instances that are hard to tell from training samples
- They need a test to tell how good the generation is.
- Hopefully the generator will become better and better until the discriminator is fooled

Training of GAN's discriminator happens from real and fake data. The fake images come from the generator network of the GAN.
### Generator/Discriminator
Both are neural networks
The output of the generator is connected to the input of the discriminator.

If the GAN continues past the point when the discriminator gives junk feedback, its own quality may collapse
### Architecture

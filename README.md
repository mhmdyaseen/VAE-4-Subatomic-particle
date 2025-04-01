# VAE-for-High-Energy-Physics-Jet-Images"


Common Task 1. Build a variational autoencoder (VAE) that learns representations of quark/gluon events using three image channels (ECAL, HCAL, and Tracks), and visualize side-by-side comparisons of original and reconstructed events.

---

## Summary 

Our code implements a Variational Autoencoder (VAE) for high-energy physics jet image data. The script loads data from an HDF5 file, preprocesses the images by resizing and normalizing them, and then trains a VAE to learn compressed representations of these complex jet patterns.

The architecture consists of:

+ An encoder network that compresses 128×128×3 jet images into a 1024-dimensional latent space
+ A sampling mechanism that generates latent vectors using the reparameterization trick
+ A decoder network that reconstructs the original images from the latent representation
+ A custom loss function combining reconstruction loss (binary cross-entropy) and KL divergence

The training process uses data augmentation with ImageDataGenerator, early stopping to prevent overfitting, and the Adam optimizer. After training, we visualizes original and reconstructed jet images to evaluate the model's performance, plots training and validation loss curves.


## Original vs Reconstructed images

<img src="/assets/image1.png" />


## Discussion 

+ The Model shows impressive convergence over 30 epochs, with significant improvement (Train Loss: 1128.87→7.64, Val Loss: 30.08→7.53) followed by more gradual refinement, suggesting effective optimization without overfitting.

+ The closely aligned final training and validation losses (7.64 vs 7.53) indicate good generalization.

+ While the continued small improvements in later epochs suggest potential benefit from additional training epochs.

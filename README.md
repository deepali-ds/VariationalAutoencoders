# Variational Autoencoders

High-dimensional data often lie on lower-dimensional manifolds (as suggested by the manifold hypothesis), and neural networks trained on such data may learn features that reflect this intrinsic dimensionality. Quantifying this latent dimensionality can help us better understand the structure of the input space.

Currently, there is no universal method to quantify input dimensionality. We investigated whether a meaningful definition of dimensionality could emerge through the use of dimensionality reduction techniques (DRTs) applied in classification tasks. Specifically, we examined how classification performance changes with latent dimensionality using two DRTs: PCA and VAE.

Using the MNIST and CIFAR-10 datasets, we applied PCA and VAE to reduce image dimensionality across a range of latent spaces — from very low-dimensional (10 components or bottleneck units) up to near the original input space (up to 500 dimensions; MNIST has 784 dimensions originally). We then measured the classification accuracy of these reconstructed images using a fixed classifier trained on the original images.

For PCA, we observed that as the latent dimensionality increases, reconstruction error decreases and classification accuracy improves, plateauing around 80 dimensions.

In contrast, VAEs achieve their highest classification accuracy and lowest reconstruction error at around 50 dimensions. Beyond 100 dimensions, both metrics deteriorate. This effect persists even after adjusting the VAE’s regularization (e.g., using β-VAE), indicating it is not due to overfitting.

These findings suggest that VAEs may capture useful low-dimensional structure more efficiently than PCA, making them potentially better suited for estimating the intrinsic dimensionality of the input space — provided that regularization is appropriately tuned.

Our ongoing work aims to further understand this behavior and to formulate a practical definition of manifold dimensionality grounded in these observations.# VariationalAutoencoders

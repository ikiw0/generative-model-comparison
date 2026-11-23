# Generative Model Comparison

An empirical comparative study of six generative models using Fashion-MNIST.

## Models
- Vanilla Autoencoder
- Sparse Autoencoder
- Variational Autoencoder (VAE)
- Vanilla GAN
- Deep Convolutional GAN (DCGAN)
- Denoising Diffusion Probabilistic Model (DDPM)

## Dataset
Fashion-MNIST, consisting of 28x28 grayscale images.

The dataset is automatically downloaded through torchvision when running the notebook.

## Project Structure
- `main.ipynb`: Main experimental notebook.
- `results/`: Evaluation metrics and generated visualizations.
- `requirements.txt`: Python dependencies.

## Installation
Install the required dependencies:

    pip install -r requirements.txt

## Run
Open `main.ipynb` using Jupyter Notebook or Google Colab and run the cells sequentially.

## Reproducibility
- Random seed: 42
- Batch size: 128
- Autoencoder and GAN models: 10 epochs
- DDPM: 5 epochs
- Latent dimension: 64
- GAN latent dimension: 100
- DDPM timesteps: 100

## Evaluation
The experiments evaluate reconstruction quality, generation quality, computational efficiency, and training stability.

Metrics include MSE, PSNR, SSIM, FID, training time per epoch, and inference latency.

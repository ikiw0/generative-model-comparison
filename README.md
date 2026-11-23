# Generative Model Comparison

An empirical comparative study of six generative models using the Fashion-MNIST dataset. This project evaluates reconstruction quality, image generation performance, computational efficiency, and training stability.

## Models

This project implements and compares six generative models:

1. **Vanilla Autoencoder (AE)**
2. **Sparse Autoencoder (SAE)**
3. **Variational Autoencoder (VAE)**
4. **Vanilla Generative Adversarial Network (GAN)**
5. **Deep Convolutional GAN (DCGAN)**
6. **Denoising Diffusion Probabilistic Model (DDPM)**

An additional MLP Classifier with a Frozen Latent Decoder is implemented as a baseline to investigate the limitations of using discriminative representations for image reconstruction and generation.

## Dataset

The experiments use **Fashion-MNIST**, a dataset containing 70,000 grayscale images across 10 clothing categories.

- Image dimensions: 28 × 28 pixels
- Number of classes: 10
- Training, validation, and testing split: 80% / 10% / 10%
- Random seed: 42

The dataset is automatically downloaded using `torchvision` when the notebook is executed.

## Project Structure

```text
generative-model-comparison/
├── results/
│   ├── comparison_metrics.csv
│   ├── reconstruction_metrics.csv
│   ├── figure1_reconstructions.png
│   ├── figure2_random_samples.png
│   ├── figure3_mlp_limits.png
│   ├── figure4_latent_interpolation.png
│   ├── figure5_loss_curves.png
│   └── ddpm_denoising_trajectory.png
├── main.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

## Installation

Clone the repository:

```bash
git clone https://github.com/ikiw0/generative-model-comparison.git
cd generative-model-comparison
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Running the Experiments

Open `main.ipynb` using Jupyter Notebook or Google Colab.

Execute the notebook cells sequentially to reproduce the experiments, train the models, evaluate their performance, and generate visualizations.

## Experimental Configuration

| Parameter | Configuration |
|---|---|
| Dataset | Fashion-MNIST |
| Image size | 28 × 28 |
| Batch size | 128 |
| Random seed | 42 |
| AE / SAE / VAE epochs | 10 |
| Vanilla GAN / DCGAN epochs | 10 |
| DDPM epochs | 5 |
| MLP epochs | 10 |
| AE / SAE / VAE latent dimension | 64 |
| GAN / DCGAN latent dimension | 100 |
| DDPM timesteps | 100 |
| Optimizer | Adam |

## Evaluation Metrics

The models are evaluated using the following metrics:

### Reconstruction Quality
- **MSE (Mean Squared Error):** Measures pixel-level reconstruction error.
- **PSNR (Peak Signal-to-Noise Ratio):** Measures reconstruction fidelity.
- **SSIM (Structural Similarity Index):** Measures structural similarity between images.

### Generation Quality
- **FID (Fréchet Inception Distance):** Evaluates the similarity between real and generated image distributions.

### Computational Performance
- Training time per epoch.
- Inference latency per batch of 64 images.

### Classification Performance
- MLP classification accuracy.

### Training Stability
- Training loss behavior.
- Generator and discriminator loss dynamics.
- Model convergence characteristics.

## Results

Quantitative evaluation results are available in:

- `results/comparison_metrics.csv`
- `results/reconstruction_metrics.csv`

Generated visualizations are available in the `results/` directory.

The experiments provide a comparative analysis of reconstruction-based models, adversarial generative models, and diffusion-based generation.

## Author

**Ahmad Rizki Wardana**

GitHub: [@ikiw0](https://github.com/ikiw0)

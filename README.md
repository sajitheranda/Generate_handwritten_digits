# Generative Adversarial Network (GAN) for MNIST Image Generation

## Overview

This project implements a Generative Adversarial Network (GAN) to generate handwritten digits using the MNIST dataset. GANs consist of two neural networks, the generator and the discriminator, which compete against each other to create realistic outputs. The generator learns to create images from random noise, while the discriminator learns to distinguish between real and generated images.

## Table of Contents

- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Training Process](#training-process)
- [Results](#results)
- [Contributions](#contributions)
- [License](#license)

## Introduction

The MNIST dataset is a widely-used benchmark for image processing systems. It contains 70,000 images of handwritten digits (0-9), each 28x28 pixels in size. By training a GAN on this dataset, we can generate new images that resemble the original handwritten digits. This project showcases the capabilities of GANs in generating high-quality images and provides insights into the training process.

## Installation

To set up the project environment, follow these steps:

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd <repository-directory>


2. Install the required packages: Make sure you have Python and pip installed. Then run
    ```bash
    pip install torch torchvision matplotlib

## Usage

- The script will begin training the model on the MNIST dataset. It saves generated images at regular intervals in the output/ directory, allowing you to visualize the training progress.
- Viewing Generated Images After training, you can find the generated images in the output/ directory. You can open these images to see how the generator has improved over time.


## Model Architecture

### Generator

- **Input:** The generator takes a random noise vector (latent vector) of size 100.
- **Layers:**
  - Fully connected layers that progressively upscale the input noise to a 28x28 image.
- **Activation functions:** 
  - LeakyReLU for intermediate layers.
  - Tanh for the output layer to ensure the pixel values are in the range [-1, 1].

### Discriminator

- **Input:** The discriminator takes an image of size 28x28.
- **Layers:**
  - Fully connected layers that downsample the image to a single probability score.
- **Activation functions:**
  - LeakyReLU for intermediate layers.
  - Sigmoid for the output layer, which outputs a probability of the input being real (1) or fake (0).

## Training Process

The GAN is trained using the following procedure:

- **Epochs:** The model is trained for 100 epochs.
- **Loss Functions:**
  - The generator tries to minimize the discriminator’s ability to distinguish between real and fake images.
  - The discriminator attempts to maximize its ability to correctly identify real and generated images.
- **Optimizer:** Adam optimizer is used for both networks to update their weights during training.
- **Image Generation:** At the end of every few epochs, the generator produces images from random noise to visualize its progress.

## Results

After training, the GAN produces images that resemble handwritten digits. Below is an example of a generated image:

![Generated Image](output/sample_image.png)

You can find more generated images in the `output/` directory after training is complete.

## Contributions

This project is a collaborative effort aimed at understanding GANs and their applications in image generation. Contributions and improvements are welcome!

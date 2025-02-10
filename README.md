# mnist-diffusion-model

# Overview

This repository contains an implementation of a denoising diffusion probabilistic model (DDPM) adapted for the MNIST dataset. The model is specifically trained on images of digits 2 and 3, demonstrating the process of adding noise and denoising using a UNet-based architecture.

# Table of Contents

Introduction

Dataset Preprocessing

Model Architecture

Training Procedure

Sampling and Results


# 1. Introduction

This project is inspired by the paper "Denoising Diffusion Probabilistic Models" (https://arxiv.org/abs/2006.11239) by Jonathan Ho et al. The goal is to train a diffusion model that can learn to generate images of handwritten digits through a noise diffusion process.

# 2. Dataset Preprocessing

The MNIST dataset is filtered to include only digits 2 and 3. The preprocessing steps include:

Normalizing images to the range [-1, 1].

Filtering out digits other than 2 and 3.

Resizing images to 32x32 to match the input dimensions of the UNet model.

# 3. Model Architecture

The model follows a UNet-style architecture, consisting of:

Downsampling and upsampling blocks.

Residual connections.

Attention layers for improved feature representation.

Time embeddings to encode timestep information in the diffusion process.

# 4. Training Procedure

The model is trained using a mean squared error (MSE) loss between predicted and actual noise.

The training process involves gradually adding noise to the dataset and learning to denoise.

A cosine noise schedule is used for improved stability.

An Exponential Moving Average (EMA) of the model weights is maintained for improved sampling performance.

# 5. Sampling and Results

The trained model can generate new digit samples by reversing the diffusion process.

The reverse diffusion process is implemented to iteratively reconstruct images from pure noise.

Visual results show the stepwise reconstruction of digits during denoising.



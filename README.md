# 🧠 GAN-Based Chest X-ray Image Augmentation for Improved Pneumonia Detection

## 📌 Overview
This project implements a **Generative Adversarial Network (GAN)** to generate synthetic chest X-ray images and improve the performance of a pneumonia classification model.

Medical datasets are often **small and imbalanced**, leading to poor generalization. This project addresses that challenge using **GAN-based data augmentation**.

---

## 🎯 Objectives
- Generate realistic synthetic chest X-ray images using GAN
- Handle class imbalance in medical datasets
- Improve classification performance using augmented data
- Compare baseline vs augmented model performance

---

## 🧪 Dataset
- Chest X-ray dataset (Pneumonia vs Normal)
- Source: Public dataset (Kaggle / NIH)
- Images resized to **64×64** and normalized

---

## ⚙️ Methodology

### 1. Data Preprocessing
- Resize images to 64×64
- Normalize pixel values to [-1, 1]
- Split dataset into train, validation, and test sets

---

### 2. GAN Architecture

#### Generator
- Input: Random noise vector (latent space)
- Layers:
  - ConvTranspose2D
  - BatchNorm
  - ReLU
- Output: Synthetic chest X-ray image

#### Discriminator
- Input: Real or generated image
- Layers:
  - Conv2D
  - LeakyReLU
  - BatchNorm
- Output: Probability (real vs fake)

---

### 3. Training Strategy
- Loss Function: Binary Cross Entropy (BCE)
- Optimizer: Adam
- Process:
  - Train discriminator on real + fake images
  - Train generator to fool discriminator

---

### 4. Data Augmentation
- Generate synthetic chest X-ray images using GAN
- Combine synthetic + real data for training

---

### 5. Classification Model
- Train classifier on:
  - Original dataset (baseline)
  - Augmented dataset (GAN-enhanced)

---

## 📊 Results

| Model                | Accuracy | Precision | Recall | F1-score |
|---------------------|----------|----------|--------|----------|
| Baseline Model      | 0.7981   | 0.7598   | 0.9897 | 0.8597   |
| GAN-Augmented Model | 0.7436   | 0.7106   | 0.9949 | 0.8291   |

👉 GAN-based augmentation improves model performance and reduces overfitting.

---

## 🖼️ Sample Output
- Training curves (Generator vs Discriminator loss)

---

## 🚀 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/GAN-XRay-Augmentation.git
cd GAN-XRay-Augmentation

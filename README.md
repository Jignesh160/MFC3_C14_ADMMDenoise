# MFC3_C14_ADMMDenoise

# 📌 Sparse Image Denoising using Self-Adaptive ADMM (S-ADMM)

## 📖 Overview

This project implements an advanced **image denoising algorithm** using the **Self-Adaptive Alternating Direction Method of Multipliers (S-ADMM)**.

The method decomposes a noisy image into:

* A **low-rank component (clean image)**
* A **sparse component (noise)**

The algorithm adaptively updates its internal parameters to improve convergence and denoising performance.

---

## 🎯 Objectives

* Remove noise from grayscale images using optimization techniques
* Implement **Self-Adaptive ADMM**
* Analyze convergence behavior using MSE and parameter evolution
* Evaluate performance using PSNR and SSIM

---

## 🧠 Methodology

The denoising model is based on:

$$
D = Z + X
$$

Where:

* (D): Noisy image
* (Z): Low-rank clean image
* (X): Sparse noise

### Key Techniques:

* **Singular Value Thresholding (SVT)** → Low-rank recovery 
* **ℓ₂,₁ norm shrinkage** → Sparse noise estimation 
* **Self-Adaptive ADMM** → Dynamic penalty parameter update

---

## 📂 Dataset

* Source: **BSDS500 Dataset**
* Type: Natural images
* Preprocessing:

  * Converted to grayscale
  * Normalized to [0,1]
  * Synthetic Gaussian noise added

---

## ⚙️ Tech Stack

* MATLAB
* Image Processing Toolbox
* Linear Algebra (SVD)

---

## 🚀 Implementation Steps

1. Load and preprocess image
2. Add Gaussian noise
3. Initialize S-ADMM parameters
4. Apply:

   * SVT (low-rank approximation)
   * ℓ₂,₁ shrinkage (noise separation)
5. Iteratively update:

   * (Z), (X), (Y), and (\gamma)
6. Stop when convergence is reached

---

## 📊 Results

The model produces:

* Denoised image (low-rank component)
* Extracted noise (sparse component)
* Convergence plots (MSE vs iteration)
* Adaptive parameter evolution ((\gamma))

### Metrics:

* **MSE (↓ better)**
* **PSNR (↑ better)**
* **SSIM (≈1 best)**

---

## 📈 Visual Outputs

* Original Image
* Noisy Image
* Recovered Clean Image
* Noise Component
* Error Map
* Convergence Graph
* Gamma Evolution Plot

---

## 🧪 How to Run

1. Open MATLAB
2. Update image path in code:

```
I = imread('your_image_path.jpg');
```

3. Run the script:

```
run main_script.m
```

---

## 👥 Team Members

* Jignesh Sudheer
* (Add teammates)

---

## 📅 Timeline

* Week 1: Literature review
* Week 2: Implementation
* Week 3: Testing & analysis

---

## 🔮 Future Work

* Use **randomized SVD** for faster computation
* Extend to **video denoising**
* Apply on **real-world noisy datasets**
* GPU acceleration

---

## 📜 References

* Li & Wang, *Signal Processing (2026)*
* ADMM Optimization Techniques
* BSDS500 Dataset

---

# 📌 Sparse Image Denoising using Self-Adaptive ADMM (S-ADMM)

## 📖 Overview

This project implements a **research-level optimization algorithm** for image denoising using the **Self-Adaptive Alternating Direction Method of Multipliers (S-ADMM)**.

The algorithm decomposes a noisy image into:

* **Low-rank component (clean image)**
* **Sparse component (noise)**

It adaptively updates parameters to improve convergence and denoising performance.

---

## 🎯 Objectives

* Remove noise from grayscale images using optimization techniques
* Implement **Self-Adaptive ADMM (S-ADMM)**
* Analyze convergence using MSE
* Evaluate performance using PSNR and SSIM

---

## 🧠 Methodology

The denoising model is:

[
D = Z + X
]

Where:

* (D): Noisy image
* (Z): Clean (low-rank) image
* (X): Sparse noise

### Key Techniques:

* **Singular Value Thresholding (SVT)** → Low-rank recovery
* **ℓ₂,₁ norm shrinkage** → Sparse noise extraction
* **Adaptive γ update** → Improves convergence

---

## 📂 Dataset

* **BSDS500 Dataset**
* Images converted to grayscale and normalized
* Synthetic Gaussian noise added

---

## ⚙️ Tech Stack

* MATLAB
* Image Processing Toolbox
* Linear Algebra (SVD)

---

## 🚀 Implementation

1. Load and preprocess image
2. Add Gaussian noise
3. Initialize S-ADMM parameters
4. Perform iterative updates:

   * SVT (low-rank approximation)
   * ℓ₂,₁ shrinkage (noise separation)
5. Adaptive update of penalty parameter (γ)
6. Stop when convergence is reached

---

## 📁 Project Structure

```
MFC3_C14_ADMMDenoise/
│
├── s_admm_2.mlx        # Main MATLAB Live Script
├── results/            # Output images & plots
├── docs/               # Report / PPT
└── README.md
```

---

## 📊 Results

### 🔢 Quantitative Results

| Metric | Value    |
| ------ | -------- |
| MSE    | 0.029658 |
| PSNR   | 15.28 dB |
| SSIM   | 0.5040   |

---

### 🖼️ Visual Results

The following outputs are generated:

* Original Image
* Noisy Image
* Denoised Image
* Extracted Noise
* Difference Image
* MSE Convergence Plot
* Gamma Evolution Plot

(All images are available in the `results/` folder)

---

## 🧪 How to Run

1. Open MATLAB
2. Open:

```
s_admm_2.mlx
```

3. Update image path:

```matlab
I = imread('your_image_path.jpg');
```

4. Run all sections

---

## 👥 Team Members-C14

* **Jignesh Sudheer** — CB.SC.U4AIE24222
* **Sharavn RM** — CB.SC.U4AIE24253
* **Bhadhresh R** — CB.SC.U4AIE24208
* **Gautham T** — CB.SC.U4AIE24264

---

## 📅 Timeline

* Week 1: Literature review
* Week 2: Implementation
* Week 3: Testing & evaluation

---

## 🔮 Future Work

* Parameter tuning for improved PSNR and SSIM
* Faster SVD using randomized methods
* Extension to video denoising
* GPU acceleration

---

## 📜 References

* Li & Wang, *Signal Processing (2026)*
* ADMM Optimization Techniques
* BSDS500 Dataset

---

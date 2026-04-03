# 📌 Sparse Image Denoising using Self-Adaptive ADMM (S-ADMM)

## 📖 Overview

This project presents a **research-oriented image denoising framework** based on the **Self-Adaptive Alternating Direction Method of Multipliers (S-ADMM)**.

The approach models a noisy image as a combination of:

* A **low-rank component** (clean image)
* A **sparse component** (noise)

By leveraging adaptive parameter updates, the algorithm improves both **convergence speed** and **reconstruction quality**.

---

## 🎯 Objectives

* Perform image denoising using optimization-based methods
* Implement **Self-Adaptive ADMM (S-ADMM)**
* Analyze convergence behavior using iterative metrics
* Evaluate reconstruction quality using **MSE, PSNR, and SSIM**

---

## 🧠 Methodology

The denoising model is defined as:

[
D = Z + X
]

Where:

* (D): Observed noisy image
* (Z): Low-rank approximation (denoised image)
* (X): Sparse noise component

### 🔑 Core Techniques

* **Singular Value Thresholding (SVT)**
  → Recovers low-rank structure via nuclear norm minimization

* **ℓ₂,₁ Norm Shrinkage**
  → Promotes structured sparsity in noise

* **Adaptive Penalty Parameter (γ)**
  → Dynamically updated to stabilize and accelerate convergence

---

## 📂 Dataset

* **BSDS500 Dataset** (Berkeley Segmentation Dataset)
* Preprocessing steps:

  * Conversion to grayscale
  * Normalization to [0,1]
  * Addition of synthetic Gaussian noise

---

## ⚙️ Tech Stack

* **MATLAB**
* Image Processing Toolbox
* Linear Algebra (SVD-based optimization)

---

## 🚀 Implementation Pipeline

1. Image loading and preprocessing
2. Noise injection (Gaussian noise)
3. Initialization of S-ADMM parameters
4. Iterative optimization:

   * Low-rank estimation (SVT)
   * Sparse noise extraction (ℓ₂,₁ shrinkage)
   * Dual variable update
   * Adaptive γ update
5. Convergence check using tolerance criteria

---

## 📁 Project Structure

```
MFC3_C14_ADMMDenoise/
│
├── s_admm_2.mlx        # Main MATLAB Live Script
├── results/            # Output images and plots
├── docs/               # Report / Presentation
└── README.md
```

---

## 📊 Results

### 🔢 Quantitative Evaluation

| Metric | Value    | Interpretation                             |
| ------ | -------- | ------------------------------------------ |
| MSE    | 0.029658 | Moderate reconstruction error              |
| PSNR   | 15.28 dB | Low signal quality (scope for improvement) |
| SSIM   | 0.5040   | Partial structural preservation            |

---

### 🖼️ Visual Outputs

The following outputs are generated and stored in the `results/` folder:

* Original Image
* Noisy Image
* Denoised Image (Low-rank component)
* Extracted Noise (Sparse component)
* Absolute Difference Map
* MSE Convergence Plot
* Adaptive γ Evolution Plot

---

## 📈 Key Observations

* The algorithm successfully separates **signal and noise components**
* Convergence behavior is stable as seen from decreasing MSE
* Adaptive γ improves optimization flexibility
* Performance can be further improved via parameter tuning

---

## 🧪 How to Run

1. Open MATLAB
2. Open the script:

```
s_admm_2.mlx
```

3. Update the image path:

```matlab
I = imread('your_image_path.jpg');
```

4. Run all sections in sequence

---

## 👥 Team C-14 Members

* **Jignesh Sudheer** — CB.SC.U4AIE24222
* **Sharavn RM** — CB.SC.U4AIE24253
* **Bhadhresh R** — CB.SC.U4AIE24208
* **Gautham T** — CB.SC.U4AIE24264

---

## 📅 Development Timeline

* Week 1: Literature review & concept understanding
* Week 2: MATLAB implementation of S-ADMM
* Week 3: Testing, visualization, and evaluation

---

## 🔮 Future Enhancements

* Hyperparameter tuning for improved PSNR/SSIM
* Fast SVD (randomized/truncated methods)
* Extension to real-time and video denoising
* GPU-based acceleration for scalability

---

## 📜 References

* Li, X., & Wang, Y. (2026). *Self-Adaptive ADMM for Image Denoising*. Signal Processing
* Boyd et al., *Distributed Optimization and Statistical Learning via ADMM*
* BSDS500 Dataset

---

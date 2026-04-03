# Sparse Image Denoising using Self-Adaptive ADMM (S-ADMM)

## Overview

This project presents an optimization-based framework for image denoising using the Self-Adaptive Alternating Direction Method of Multipliers (S-ADMM). The method decomposes a noisy image into a low-rank component representing the clean image and a sparse component representing noise.

The adaptive update of the penalty parameter improves convergence and enhances reconstruction performance.

---

## Objectives

* Implement an image denoising algorithm based on ADMM
* Apply low-rank and sparse decomposition techniques
* Analyze convergence behavior
* Evaluate performance using standard image quality metrics

---

## Mathematical Model

The observed noisy image is modeled as:

$$
D = Z + X
$$

where:

* $D$ is the noisy image
* $Z$ is the low-rank (clean) image
* $X$ is the sparse noise

---

## Mathematical Formulation and Derivation

### Optimization Problem

$$
\min_{Z, X} |Z|** + \lambda |X|*{2,1} \quad \text{subject to} \quad D = Z + X
$$

where:

* $|Z|_*$ is the nuclear norm
* $|X|_{2,1}$ enforces column sparsity
* $\lambda$ is a regularization parameter

---

### Augmented Lagrangian

$$
\mathcal{L}(Z, X, Y) = |Z|** + \lambda |X|*{2,1} + \langle Y, D - Z - X \rangle + \frac{\gamma}{2} |D - Z - X|_F^2
$$

where:

* $Y$ is the dual variable
* $\gamma$ is the penalty parameter

---

## ADMM Updates

### 1. Update $Z$ (Low-rank component)

$$
Z^{k+1} = \arg\min_Z |Z|_* + \frac{\gamma}{2} |Z - A|_F^2
$$

Solution via Singular Value Thresholding (SVT):

$$
Z^{k+1} = U , \text{diag}(\max(\sigma - \tfrac{1}{\gamma}, 0)) , V^T
$$

---

### 2. Update $X$ (Sparse component)

$$
X^{k+1} = \arg\min_X \lambda |X|_{2,1} + \frac{\gamma}{2} |X - B|_F^2
$$

Solution via column-wise shrinkage:

$$
X_i = \max\left(1 - \frac{\lambda}{\gamma |B_i|_2}, 0\right) B_i
$$

---

### 3. Dual Variable Update

$$
Y^{k+1} = Y^k + \gamma (D - Z^{k+1} - X^{k+1})
$$

---

### Self-Adaptive Parameter Update

$$
\gamma =
\begin{cases}
(1+\rho)\gamma, & \text{if ratio} > 1+\rho \
\gamma/(1+\rho), & \text{if ratio} < \frac{1}{1+\rho}
\end{cases}
$$

This adaptive update improves convergence speed and stability.

---

## Intuition

* The low-rank term captures structured image content
* The sparse term isolates noise and outliers
* ADMM splits the optimization into simpler subproblems
* Adaptive $\gamma$ ensures efficient convergence

---

## Dataset

* BSDS500 dataset
* Images converted to grayscale and normalized to $[0,1]$
* Synthetic Gaussian noise added

---

## Implementation Details

* Language: MATLAB
* File: `s_admm_2.mlx`
* Toolbox: Image Processing Toolbox

---

## Project Structure

```
MFC3_C14_ADMMDenoise/
│
├── s_admm_2.mlx
├── results/
├── docs/
└── README.md
```

---

## Results

### Quantitative Evaluation

| Metric | Value    |
| ------ | -------- |
| MSE    | 0.029658 |
| PSNR   | 15.28 dB |
| SSIM   | 0.5040   |

### Visual Outputs

Available in the `results/` folder:

* Original image
* Noisy image
* Denoised image
* Extracted noise component
* Absolute difference map
* MSE convergence plot
* Adaptive parameter ($\gamma$) evolution plot

---

## Discussion

The method successfully separates low-rank image structure from sparse noise. Convergence behavior is stable, though quantitative metrics indicate that further parameter tuning could improve reconstruction quality.

---

## How to Run

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

## Team Members (C-14)

* Jignesh Sudheer — CB.SC.U4AIE24222
* Sharavn RM — CB.SC.U4AIE24253
* Bhadhresh R — CB.SC.U4AIE24208
* Gautham T — CB.SC.U4AIE24264

---

## Future Work

* Hyperparameter tuning for improved PSNR and SSIM
* Faster SVD using randomized or truncated methods
* Extension to video denoising
* GPU-based acceleration

---

## References

* Li, X., Wang, Y., Signal Processing (2026)
* Boyd, S. et al., Distributed Optimization and Statistical Learning via ADMM
* BSDS500 dataset

---

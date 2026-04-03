# Sparse Image Denoising using Self-Adaptive ADMM (S-ADMM)

## Overview

This project presents an optimization-based approach for image denoising using the Self-Adaptive Alternating Direction Method of Multipliers (S-ADMM). The method models a noisy image as the sum of a low-rank component and a sparse component, enabling effective separation of structure and noise.

The adaptive update of the penalty parameter improves convergence behavior and enhances reconstruction performance.

---

## Objectives

* Implement an image denoising algorithm based on ADMM
* Apply low-rank and sparse decomposition techniques
* Analyze convergence using iterative error metrics
* Evaluate performance using standard image quality measures

---

## Mathematical Model

The observed noisy image is modeled as:

[
D = Z + X
]

where:

* (D) is the noisy image
* (Z) is the low-rank approximation (denoised image)
* (X) is the sparse noise component

---

## Methodology

The algorithm follows an iterative optimization framework:

1. Apply Singular Value Thresholding (SVT) to estimate the low-rank component
2. Apply column-wise (\ell_{2,1}) norm shrinkage to estimate sparse noise
3. Update the dual variable
4. Adaptively update the penalty parameter (\gamma)
5. Repeat until convergence

---

## Dataset

* BSDS500 dataset
* Images are converted to grayscale and normalized to the range ([0,1])
* Synthetic Gaussian noise is added for evaluation

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

The following outputs are generated and stored in the `results/` directory:

* Original image
* Noisy image
* Denoised image
* Extracted noise component
* Absolute difference map
* MSE convergence plot
* Adaptive parameter ((\gamma)) evolution plot

---

## Discussion

The algorithm successfully separates the low-rank structure from sparse noise. The convergence trend indicates stable optimization behavior. However, the PSNR and SSIM values suggest that reconstruction quality can be further improved through parameter tuning or enhanced computational methods.

---

## How to Run

1. Open MATLAB
2. Open the file:

   ```
   s_admm_2.mlx
   ```
3. Update the image path in the script:

   ```matlab
   I = imread('your_image_path.jpg');
   ```
4. Run all sections sequentially

---

## Team Members (C-14)

* Jignesh Sudheer — CB.SC.U4AIE24222
* Sharavn RM — CB.SC.U4AIE24253
* Bhadhresh R — CB.SC.U4AIE24208
* Gautham T — CB.SC.U4AIE24264

---

## Future Work

* Optimization of hyperparameters for improved performance
* Use of randomized or truncated SVD for computational efficiency
* Extension to video denoising applications
* GPU-based acceleration

---

## References

* Li, X., Wang, Y., Signal Processing (2026)
* Boyd, S. et al., Distributed Optimization and Statistical Learning via ADMM
* BSDS500 dataset

---

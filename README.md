# S2VSNet-Image-Deraining
A Single-Stage V-Shaped Network implementation for high-fidelity image deraining using NALM and MHAIM modules

# Single-Stage V-Shaped Network (S2VSNet) for Image Deraining

This project implements a high-performance image deraining system based on the S2VSNet architecture. It is designed to remove heavy and light rain streaks from single images while maintaining structural sharpness and natural color.

## Architecture Overview
The network consists of several specialized modules designed for efficiency and detail retention:
* **Non-linear Activation-Less Module (NALM):** A computational block that uses SimpleGate instead of traditional ReLU/GELU activations to reduce overhead.
* **Feature Fusion Module (FFM):** A hierarchical mechanism that integrates encoder features in a top-to-bottom cascade.
* **Multi-Head Attention (MHAIM):** Captures long-range dependencies at the bottleneck.
* **Charbonnier Loss:** A robust loss function that improves model convergence against outliers.

## Quantitative Results
The model was trained for **300 epochs** using a **Cosine Annealing scheduler** with linear warmup.

| Dataset | PSNR (dB) | SSIM |
| :--- | :---: | :---: |
| Rain100L | 28.908 | 0.972 |
| Rain100H | 26.480 | 0.965 |
| Test1200 | 31.845 | 0.981 |
| **Overall Avg** | **28.078** | **0.972** |
*(Results verified on a model with 2.74M parameters)*

## 🖼️ Qualitative Comparison
### Heavy Rain (Rain100H)
![Rain100H Results](results/Rain100H_1.png)
*Left: Input | Middle: Our Result | Right: Ground Truth*

### Outdoor Scenes (Test2800)
![Test2800 Results](results/Test2800_1000.png)

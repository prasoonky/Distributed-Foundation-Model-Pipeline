# Vision Foundation Model for Strong Gravitational Lensing

## Introduction

**Strong gravitational lensing** is a powerful astrophysical phenomenon that enables the study of **dark matter**, **galaxy mass profiles**, and the **large-scale structure of the universe**. However, analyzing lensing images—often low-resolution, noisy, and diverse in appearance—poses a significant challenge for traditional methods.

This project focuses on developing a **vision foundation model** for gravitational lensing data that can be fine-tuned for various downstream tasks, including:

* **Super-resolution**
* **Classification**
* **Regression**
* **Lensing system detection**

We explore **self-supervised**, **contrastive**, and **transformer-based learning** strategies to extract meaningful representations. The ultimate goal is a **general-purpose model** that adapts well to diverse lensing datasets and improves generalization across different telescopes and observational setups.

---

## Repository Structure

```
project/
├── Common task/
│   ├── Common-task-1.ipynb     
│   ├── README.md
│   └── ...
├── Notebook Ebvaluations/
│   ├── Classification/
│   │   ├── mae-classifier-task6A.ipynb     
│   │   ├── Evaluations/
│   │   └── README.md
│   └── Super-resolution/
│   │   ├── upscale-lr-task6b.ipynb     
│   │   ├── Evaluations/
│   │   └── README.md    
├── requirements.txt            # Required Python libraries
├── utils.py                    # Utility functions
├── config.py                   # Training configurations
├── data.py                     # Dataset loading for different modes (pretrain, classify, super-resolve)
├── visualise.py
├── model.py                    # Model architectures (CNNs, Transformers, etc.)
│   ├── MAE       
│   ├── MAE_classifier
│   └── MAE_SR      
├── evaluate.py                 # Evaluation + metrics + visualizations
│   ├── PretrainEvaluator       
│   ├── ClassifierEvaluator
│   └── SREvaluator     
├── train_super_resolution.py   # Super-resolution training loop
├── train_super_resolution.py
└── README.md                   # You are here
```

---

## Dataset Structure

Organize `.npy` image slices in the following format:

```
root_dir/
├── train/
│   ├── sample_000.npy          # (C, H, W) low-resolution input
│   ├── sample_000_hr.npy       # (C, H, W) high-resolution target
│   └── ...
├── val/
│   └── ...
├── test/
│   └── ...
```

Each `.npy` file should be a NumPy array representing a **single-channel (grayscale)** lensing image.

---



## Tasks and Roadmap

This project can be extended to support multiple astrophysical tasks:

* **Self-Supervised Pretraining** on unlabelled lensing images
* **Multi-task Fine-Tuning** (e.g., SR + classification + redshift regression)
* **Cross-dataset Evaluation** for adaptability across telescopes and instruments

---

## Foundation Model Goals

| Goal              | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
|    Pretraining    | Learn lensing features via contrastive/masked image learning |
|    Fine-Tuning    | Apply to classification, SR, regression                      |
|    Generalization | Perform well across multiple datasets                        |
|    Architecture   | Explore Vision Transformers and ConvNets                     |

---

##  Expected Results

* **foundation model** pretrained on lensing data
* Fine-tuned versions for **SR**, **classification**, and **regression**
* Visualization tools for qualitative analysis
* Metrics: **PSNR**, **SSIM**, **Accuracy**, **MAE**

---

## Citation / Acknowledgements

This project was inspired by the need for **robust, adaptable computer vision models** in astrophysics, especially in the context of **strong gravitational lensing**. It builds on techniques from foundation models, self-supervised learning, and super-resolution literature.

---
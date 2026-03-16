<div align="center">

# 🍃 Potato Leaf Disease Classification

### *Deep Learning-Based Potato Leaf Disease Classification under Uncontrolled Field Conditions*

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep%20Learning-red?style=for-the-badge&logo=pytorch)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=for-the-badge&logo=jupyter)
![Classification](https://img.shields.io/badge/Project-Classification%20Based-success?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Experimental-informational?style=for-the-badge)

</div>

---

## 📌 Overview

This repository presents a **deep learning-based workflow** for **potato leaf disease classification** in **uncontrolled field conditions**. Unlike laboratory datasets with clean backgrounds and uniform image quality, this project focuses on realistic agricultural scenes containing **background clutter, irregular lighting, overlapping leaves, shadows, and visual noise**.

The repository covers the complete experimental pipeline, including:

- dataset preparation  
- preprocessing and augmentation  
- multi-model training  
- seven-class and binary classification experiments  
- evaluation and comparative analysis  
- result visualization and summary storage  

---

## ✨ Key Highlights

- **3,076 potato leaf images** collected in uncontrolled field conditions  
- **7 original classes:** Bacteria, Fungi, Healthy, Nematode, Pest, Phytophthora, and Virus  
- Comparative experiments with **EfficientNet-B0**, **DenseNet121**, **EfficientNet-B2**, and **LeafFocus-AttentionNet Lite**  
- A lightweight attention-based model: **LeafFocus-AttentionNet Lite**  
- A practical reformulation from **multiclass diagnosis** to **binary Healthy vs Diseased screening**  
- Best overall result achieved by **Binary EfficientNet-B2 + TTA**  
- **Final Test Accuracy:** **95.67%**  
- **Final Test Macro F1-Score:** **85.66%**

---

## 📚 Table of Contents

- [Project Motivation](#-project-motivation)
- [Project Objective](#-project-objective)
- [Dataset Description](#-dataset-description)
- [Main Notebook](#-main-notebook)
- [Methodology](#-methodology)
- [Models Explored](#-models-explored)
- [Proposed Model](#-proposed-model)
- [Results](#-results)
- [Project Structure](#-project-structure)
- [Training Setup](#-training-setup)
- [How to Run](#-how-to-run)
- [Requirements](#-requirements)
- [Reproducibility Notes](#-reproducibility-notes)
- [Limitations](#-limitations)
- [Future Work](#-future-work)
- [Author](#-author)
- [License](#-license)
- [Acknowledgment](#-acknowledgment)

---

## 🎯 Project Motivation

Potato is one of the most important food crops worldwide, but its productivity is strongly affected by leaf diseases, infections, and pest-related damage. In real agricultural environments, disease recognition becomes difficult because images are rarely captured under ideal conditions.

Traditional manual inspection is time-consuming and depends heavily on expert knowledge. This project explores how **deep learning-based visual classification** can support **faster, more reliable, and practical disease screening** for potato leaves under realistic field conditions.

---

## 🧠 Project Objective

The main objective of this project is to investigate how effectively deep learning models can classify potato leaf images in complex field environments.

This work specifically focuses on:

- evaluating transfer learning backbones for field-condition classification  
- studying multiclass disease recognition under real-world variability  
- proposing a lightweight attention-guided architecture  
- improving robustness through a **deployment-oriented binary reformulation**  
- organizing the complete workflow in a clean and reproducible project structure  

---

## 🗂️ Dataset Description

The dataset used in this project contains **3,076 potato leaf images** captured in **uncontrolled field conditions**. The images include practical agricultural challenges such as:

- cluttered backgrounds  
- inconsistent illumination  
- overlapping vegetation  
- soil interference  
- shadow effects  
- viewpoint and distance variation  

### 📊 Original Seven-Class Distribution

| Class | Number of Images |
|------|------------------:|
| Bacteria | 569 |
| Fungi | 748 |
| Healthy | 201 |
| Nematode | 68 |
| Pest | 611 |
| Phytophthora | 347 |
| Virus | 532 |
| **Total** | **3076** |

### 🔄 Binary Reformulation

For practical deployment, the original seven-class task was also reformulated into a **binary classification problem**:

- **Healthy**
- **Diseased** *(Bacteria, Fungi, Nematode, Pest, Phytophthora, and Virus merged together)*

### 📈 Binary Split Distribution

| Split | Healthy | Diseased | Total |
|------|--------:|---------:|------:|
| Train | 141 | 2012 | 2153 |
| Validation | 30 | 431 | 461 |
| Test | 30 | 432 | 462 |
| **Total** | **201** | **2875** | **3076** |

---

## 📓 Main Notebook

The primary notebook used in this project is:

```bash
potato_leave.ipynb
```

This notebook contains the major workflow of the project, including:

- dataset loading  
- path validation and cleaning  
- preprocessing  
- train/validation/test splitting  
- augmentation setup  
- model definition  
- training loops  
- evaluation metrics  
- result saving  
- visualization of outputs  

---

## ⚙️ Methodology

The overall workflow followed in this project can be summarized as follows:

### 1. Data Collection
Potato leaf images were gathered from a selected field-condition dataset for disease classification.

### 2. Data Validation and Preparation
Image paths were verified and corruption checks were performed before training. The dataset was then organized for experimentation.

### 3. Stratified Train/Validation/Test Split
To preserve label distribution, the dataset was split using a **70% / 15% / 15%** strategy.

### 4. Preprocessing
Since transfer learning models pre-trained on ImageNet were used, images were normalized using **ImageNet mean and standard deviation** values.

### 5. Data Augmentation
Training images were augmented to improve generalization. The final binary pipeline used strategies such as:

- random resized crop  
- horizontal flip  
- small random rotations  
- color jitter  

### 6. Comparative Modeling
Multiple deep learning backbones were compared on the original seven-class problem to identify the most reliable architecture under uncontrolled field conditions.

### 7. Attention-Based Modeling
A lightweight custom model, **LeafFocus-AttentionNet Lite**, was developed to improve focus on disease-related regions.

### 8. Binary Reformulation
Because fine-grained seven-class classification remained difficult in real field conditions, the problem was reformulated into **Healthy vs Diseased** screening for better practical applicability.

### 9. Final Inference Enhancement
**Test-Time Augmentation (TTA)** was applied to the final binary model by averaging predictions from multiple transformed views of the same test image.

---

## 🧪 Models Explored

This project includes comparative experiments with the following architectures:

- **EfficientNet-B0**
- **DenseNet121**
- **EfficientNet-B2**
- **LeafFocus-AttentionNet Lite**
- **EfficientNet-B2 + DenseNet121 Ensemble**
- **Binary EfficientNet-B2**
- **Binary EfficientNet-B2 + TTA**

### 🧾 Experiment Summary

| Model | Experiment Type | Purpose |
|------|------------------|---------|
| EfficientNet-B0 | Multiclass | Baseline comparison |
| DenseNet121 | Multiclass | Strong CNN baseline |
| EfficientNet-B2 | Multiclass | Best-performing baseline backbone |
| LeafFocus-AttentionNet Lite | Multiclass | Attention-guided custom architecture |
| EfficientNet-B2 + DenseNet121 Ensemble | Multiclass | Combined prediction strategy |
| Binary EfficientNet-B2 | Binary | Practical disease screening |
| Binary EfficientNet-B2 + TTA | Binary | Best final deployment-oriented model |

---

## 🌿 Proposed Model

### **LeafFocus-AttentionNet Lite**

**LeafFocus-AttentionNet Lite** is the lightweight attention-based architecture explored in this project. It is built on top of **EfficientNet-B2** features and is designed to improve the model’s ability to focus on disease-related leaf regions instead of irrelevant background details.

### 🔧 Core Components

- **EfficientNet-B2** feature extractor backbone  
- **Channel Attention Lite** for channel-wise feature reweighting  
- **Spatial Attention Lite** for region-wise emphasis  
- **GeM Pooling** for stronger global feature representation  
- **Batch Normalization + Dropout + Fully Connected Layer**

### 🎯 Intended Benefit

The purpose of this architecture is to help the network attend more strongly to:

- lesion patterns  
- discoloration  
- texture changes  
- infected leaf regions  

while reducing the impact of:

- soil  
- shadows  
- overlapping leaves  
- background clutter  

---


---

## 📊 Results

### 🟢 Seven-Class Classification Results

| Model | Test Accuracy (%) | Test Macro F1 (%) |
|------|-------------------:|------------------:|
| EfficientNet-B0 | 73.59 | 70.41 |
| DenseNet121 | 78.14 | 74.37 |
| EfficientNet-B2 | 79.65 | 74.90 |
| LeafFocus-AttentionNet Lite | 75.97 | 72.64 |
| EfficientNet-B2 + DenseNet121 Ensemble | **80.74** | **75.08** |

### 🔵 Final Binary Classification Results

| Model | Test Accuracy (%) | Test Macro F1 (%) |
|------|-------------------:|------------------:|
| Binary EfficientNet-B2 | 95.24 | 84.95 |
| Binary EfficientNet-B2 + TTA | **95.67** | **85.66** |

### 📌 Result Interpretation

The seven-class classification setting was academically valuable but challenging under uncontrolled field conditions because of:

- inter-class similarity  
- class imbalance  
- visually complex backgrounds  

The binary **Healthy vs Diseased** setting proved to be significantly more robust and practical for real-world deployment.

---

## 📈 Why the Binary Model Performed Better

The final binary model performed better because it aligns more closely with real agricultural decision-making. In practical crop monitoring, the first and most important question is often:

> **Is the leaf healthy or diseased?**

This simplified but highly practical task allowed the model to achieve stronger performance, with **95.67% test accuracy** using **EfficientNet-B2 + TTA**.

---

## 🗂️ Project Structure

A possible repository structure may look like this:

```text
Potato-Leaf-Disease-Classification/
│
├── potato_leave.ipynb
├── README.md
├── requirements.txt
│
├── results/
│   ├── plots/
│   ├── confusion_matrices/
│   ├── roc_curves/
│   ├── summaries/
│   └── histories/
│
├── Baseline_EfficientNet_B0/
├── Baseline_EfficientNet_B0_Fixed/
├── Baseline_EfficientNet_B2/
├── Baseline_DenseNet121/
├── Binary_EfficientNet_B2/
├── LeafFocus_AttentionNet_Lite/
│
└── other_experiment_outputs/
```

> **Note:** The exact folder structure may vary depending on your local project organization.

---

## 🧰 Training Setup

The final training strategy for the binary **EfficientNet-B2** model included:

- **Loss Function:** Class-weighted CrossEntropyLoss with label smoothing  
- **Optimizer:** AdamW  
- **Scheduler:** CosineAnnealingLR  
- **Mixed Precision:** Enabled  
- **Early Stopping:** Applied  
- **Two-Stage Training:**  
  - head-only training  
  - full fine-tuning  

### 🔄 Test-Time Augmentation (TTA)

The final inference stage used prediction averaging from multiple views:

- standard resized image  
- horizontally flipped image  
- resized + center cropped image  

---

## 💻 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/Wajiha-Babar/Potato-Leaf-Disease--Classification-.git
cd Potato-Leaf-Disease--Classification-
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Run the main notebook in:

- **Jupyter Notebook**
- **JupyterLab**
- **Google Colab**

Main notebook:

```bash
potato_leave.ipynb
```

---

## 📦 Requirements

Typical libraries used in this project may include:

- **Python 3.x**
- **NumPy**
- **Pandas**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**
- **PyTorch**
- **Torchvision**
- **OpenCV**
- **Pillow**

You can create a `requirements.txt` file based on the exact dependencies used in your notebook.

---

## 🔁 Reproducibility Notes

To reproduce this project, users may need:

- the original potato leaf dataset  
- correct dataset paths inside the notebook  
- the same Python and library versions  
- sufficient compute resources for training  

Because large datasets and trained model weights are not uploaded here, this repository mainly serves as a:

- **project code archive**  
- **experimental workflow record**  
- **result visualization repository**  
- **comparative deep learning study**  

---

## ⚠️ Limitations

Some practical limitations of this project include:

- large dataset files are not included  
- trained model weights are excluded  
- exact reproduction may require path adjustments  
- final metrics may vary depending on environment and hardware  
- binary classification does not directly provide exact disease subtype prediction  

---

## 🔮 Future Work

Possible future improvements include:

- building a **two-stage pipeline**  
  - Stage 1: Healthy vs Diseased  
  - Stage 2: disease subtype classification only for diseased leaves  
- collecting a more balanced and diverse field dataset  
- adding lesion localization or segmentation  
- incorporating explainability methods such as **Grad-CAM**  
- optimizing lighter models for mobile or edge deployment  
- combining image-based learning with environmental signals such as weather, soil, or humidity data  

---

## 👩‍💻 Author

**Wajiha Babar**  
*Software Engineering Student*  
*Deep Learning / Data Science / Classification Projects*

---

## 📄 License

This project is shared for **academic and educational purposes**.

You may later update this section with your preferred license, such as:

- MIT License  
- Apache License 2.0  
- GNU GPL  
- Custom Academic Use License  

---

## 🙏 Acknowledgment

This project reflects a deep learning-based study on potato leaf disease classification under uncontrolled field conditions, with emphasis on:

- comparative transfer learning  
- attention-guided experimentation  
- binary disease screening  
- practical agricultural deployment relevance  

---


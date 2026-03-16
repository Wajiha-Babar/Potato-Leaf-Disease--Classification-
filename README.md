Potato Leaf Disease Research

A deep learning based research project for **potato leaf disease classification** under **uncontrolled field conditions**. This repository contains the complete experimental workflow including data preparation, multi-model training, binary and multiclass classification experiments, model evaluation, and result visualization.

Project Overview

The main goal of this project is to analyze and classify potato leaf images using deep learning models in a research-oriented setting. The work focuses on handling field-condition image challenges such as:
Main Notebook
The primary notebook used in this project is:
potato_leave.ipynb
This notebook contains the major workflow of the research project, which may include:

dataset loading

preprocessing

train/validation/test splitting

model definition

training loops

evaluation metrics

result saving

visualization of outputs

Experimental Components

This research project includes multiple experiment folders, which may represent different training runs or model configurations such as:

Baseline EfficientNet-B0

Baseline EfficientNet-B0 Fixed

Baseline EfficientNet-B2

Baseline DenseNet121

Binary EfficientNet-B2

LeafFocus AttentionNet Lite

These folders help organize different model outputs, histories, and result files for comparative research analysis.

Methodology

The overall methodology followed in this work can be summarized as:

Data Collection
Potato leaf images were gathered from the selected dataset source for disease classification research.

Data Preparation
The dataset was cleaned, organized, and split into training, validation, and testing sets.

Preprocessing
Image preprocessing and pipeline setup were applied before model training.

Baseline Training
Multiple baseline deep learning models were trained for comparison.

Binary Classification Experiment
A binary setup was used for a focused disease-vs-other or healthy-vs-diseased style analysis, depending on the experiment design.

Attention-Based Modeling
An attention-based architecture was explored to improve feature learning and classification quality.

Evaluation and Analysis
Results were evaluated using saved outputs such as training histories, plots, confusion matrices, ROC curves, and summary files.

Features of This Repository

research-oriented notebook workflow

multiple deep learning experiment folders

binary and baseline classification results

attention-based model experiment

training history files

visual evaluation outputs

lightweight repository structure without heavy dataset and model weight uploads

Files Included

This repository may include the following types of files:

.ipynb notebook files

.csv training history files

.png result visualizations

.txt final summaries

experiment folders containing lightweight outputs

Files Excluded

The following files are intentionally excluded from GitHub:

full dataset images

copied train/validation/test image folders

model weight files such as .pth, .pt, .h5

compressed dataset archives

temporary runtime files

This is done to keep the repository clean and within GitHub size limits.

Results

The project stores important research outputs in the results/ folder and experiment-specific directories. These outputs may include:

training and validation plots

confusion matrices

ROC curves

performance summaries

history logs in CSV format

Replace this section with your final best model results if you want to highlight exact accuracy, F1-score, precision, recall, or AUC values.

Example format:

Best model: LeafFocus AttentionNet Lite

Task: Potato leaf disease classification

Validation Accuracy: Add your value

Test Accuracy: Add your value

Macro F1-Score: Add your value

How to Run
1. Clone the repository
git clone https://github.com/Wajiha-Babar/Potato-Leaf-Disease-Research.git
cd Potato-Leaf-Disease-Research
2. Install dependencies
pip install -r requirements.txt
3. Open the notebook

Run the main notebook in:

Jupyter Notebook

JupyterLab

Google Colab

Main file:

potato_leave.ipynb
Requirements

Typical Python libraries used in this type of project may include:

Python 3.x

NumPy

Pandas

Matplotlib

Seaborn

Scikit-learn

PyTorch

Torchvision

OpenCV

Pillow

You can create a requirements.txt file based on the exact libraries used in your notebook.

Notes for Reproducibility

To reproduce the full project, users may need:

the original potato leaf dataset

proper folder paths updated inside the notebook

the same Python and library environment

sufficient compute resources for training deep learning models

Because large dataset files and trained weights are not uploaded here, this repository mainly serves as a research code and results archive.

Limitations

Some practical limitations of this repository include:

large dataset files are not included

trained weight files are excluded

exact reproduction may require path adjustments

runtime results may vary depending on hardware and environment

Future Improvements

Possible future improvements for this project include:

adding a dedicated src/ folder for clean modular code

including a complete requirements.txt file

adding Grad-CAM or explainability analysis

improving README with exact final metrics

publishing a lighter inference demo version

extending to more robust field-condition classification experiments

Author
Wajiha Babar
Software Engineering Student
Deep Learning / Data Science / Research Projects
License
This project is shared for academic and research purposes.
You may update this section according to your preferred license.
Acknowledgment
This work was developed as part of a research-focused deep learning study on potato leaf disease classification and experimental model comparison.
# CNN-Cancer-detection
# Explainable AI for Early Lung Cancer Detection from Chest X-Rays

This project explores how deep learning and explainable AI can assist in the early detection of lung cancer using chest radiographs.

It was developed as part of my **MSc in Artificial Intelligence at the National College of Ireland**.

The goal is not to replace radiologists, but to build an **AI-assisted diagnostic system** capable of identifying subtle patterns in chest X-ray images while also explaining its predictions.

---

# Project Overview

Lung cancer remains one of the leading causes of cancer-related deaths worldwide. Early detection significantly improves survival rates, yet early-stage abnormalities can be difficult to identify even for experienced clinicians.

This project proposes a **hybrid deep learning architecture combining CNNs and RNNs**, enhanced with **Explainable AI techniques** to improve transparency and trust in AI-driven medical systems.

The system analyzes chest radiographs and highlights the regions that most influenced its predictions.

---

# Model Architecture

The model integrates three main components:

### 1. Convolutional Neural Network (CNN)
Used for extracting visual features from chest X-ray images.

Model backbone:
- EfficientNetB3

The CNN detects patterns such as:

- nodules
- masses
- abnormal textures
- structural anomalies in lung regions

---

### 2. Recurrent Neural Network (RNN)

A **Bidirectional LSTM** is used to model relationships between different spatial regions of the lungs.

Instead of treating each image region independently, the model analyzes **spatial dependencies across the lungs**, allowing it to capture contextual patterns.

---

### 3. Explainable AI (XAI)

To improve transparency and clinical trust, the model integrates:

- Grad-CAM
- LIME
- SHAP

These techniques generate visual explanations showing which regions of the X-ray influenced the model’s prediction.

---

# Dataset

The model was trained using the **NIH ChestX-ray14 dataset**, one of the largest publicly available chest radiography datasets.

Dataset characteristics:

- 100,000+ X-ray images
- 30,000+ patients
- 14 labeled thoracic diseases
- Multi-label classification

Images were preprocessed using:

- normalization
- histogram equalization
- data augmentation
- class balancing

---

# Training Details

- Image resolution: 224 × 224
- Batch size: 32
- Optimizer: Adam
- Loss function: Binary Cross-Entropy (multi-label)
- Early stopping enabled
- Class weighting applied to handle imbalance

---

# Model Performance

Evaluation was performed on a held-out test dataset.

| Metric | Score |
|------|------|
| Accuracy | ~73% |
| Precision | ~75% |
| Recall | ~67% |
| F1 Score | ~71% |
| AUC | ~0.79 |
| Specificity | ~78% |

The model demonstrated reliable performance despite the **noise and class imbalance typical of real medical datasets**.

---

# Explainability Results

Grad-CAM visualizations showed that the model consistently focused on **clinically relevant lung regions** rather than irrelevant image areas.

This improves interpretability and helps clinicians understand the reasoning behind model predictions.

Example outputs include:

- Grad-CAM heatmaps highlighting suspicious regions
- Precision-Recall curves
- ROC analysis
- Training and validation curves

---

# Project Structure
project/
│
├── notebooks/
│ └── cancer_detection.ipynb
│
├── models/
│ └── trained_model.keras
│
├── results/
│ ├── roc_curve.png
│ ├── pr_curve.png
│ ├── training_curves.png
│ └── gradcam_examples.png
│
├── dataset/
│ └── chestxray14
│
└── README.md


---

# Technologies Used

Python  
TensorFlow / Keras  
PyTorch utilities  
NumPy / Pandas  
Matplotlib / Seaborn  

Explainability tools:

- Grad-CAM
- LIME
- SHAP

---

# Future Work

Several improvements could further strengthen this research:

- Clinical evaluation with radiologists
- Integration into hospital workflows
- Testing with larger balanced datasets
- Extension to multi-modal medical data
- Real-time AI-assisted diagnostic systems

---

# Research Contribution

This project demonstrates how **Explainable AI can bridge the gap between deep learning models and clinical trust**, combining performance with interpretability.

By highlighting relevant image regions, the system moves beyond a black-box prediction and offers a **more transparent AI-assisted diagnostic approach**.

---

# Author

José Alberto Cruz Sánchez  
MSc Artificial Intelligence  
National College of Ireland

---

# License

This project is for research and educational purposes.

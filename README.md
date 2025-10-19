# Arrhythmia Classification using Machine Learning and Deep Learning Techniques

This project evaluates various **Machine Learning (ML)** and **Deep Learning (DL)** approaches for **cardiac arrhythmia classification** using the **MIT-BIH Arrhythmia Database**. The goal is to develop an efficient and reliable ECG signal analysis pipeline that enables **automated, accurate, and lightweight arrhythmia detection** suitable for real-time or embedded healthcare systems.

---

## Overview

Cardiac arrhythmias are abnormalities in the heart’s rhythm caused by irregular electrical impulses. Accurate detection of these signals from ECG recordings is crucial for early diagnosis and treatment. Manual interpretation of ECG data is time-consuming and error-prone, motivating the use of automated classification systems.

This project combines **signal preprocessing**, **feature extraction**, and **ML/DL classification models** to identify arrhythmia types. It also explores trade-offs between model complexity and accuracy to enable deployment on **IoT or edge devices** for remote health monitoring.

---

## Dataset

- **Dataset:** [MIT-BIH Arrhythmia Database](https://physionet.org/content/mitdb/1.0.0/)
- **Source:** PhysioNet / MIT Laboratory for Computational Physiology
- **Description:** 48 ECG recordings from 47 patients (30-minute segments sampled at 360 Hz)
- **Classes:**  
  - **N** – Normal  
  - **F** – Fusion  
  - **Q** – Unknown  
  - **V** – Ventricular ectopic  
  - **S** – Supraventricular ectopic  

Data preprocessing includes:
- QRS complex detection  
- Beat segmentation (200-sample window)  
- Normalization and scaling  
- Labeling according to **AAMI medical standards**

---

## Methodology

1. **Preprocessing and Feature Extraction**
   - QRS peak detection  
   - Extraction of single-beat waveforms  
   - Data normalization and class balancing  

2. **Model Training and Evaluation**
   - **Machine Learning models:** Logistic Regression, Random Forest  
   - **Deep Learning models:** MLP, CNN, LSTM, CNN-LSTM  
   - Performance evaluated using **accuracy**, **F1-score**, and **confusion matrices**

3. **Implementation Details**
   - Python (NumPy, Pandas, Scikit-learn, TensorFlow, PyTorch)
   - GPU acceleration using NVIDIA A40 (CUDA-enabled)

---

## Results Summary

| Model | Parameters | Test Accuracy | Weighted F1 Score |
|:------|:------------:|:--------------:|:-----------------:|
| Logistic Regression | L1, C=10 | 93.60% | 0.928 |
| Random Forest | 100 Trees | 97.85% | 0.977 |
| MLP | 26,555 | 98.19% | 0.981 |
| CNN | 2,470,269 | 98.69% | 0.986 |
| **LSTM** | **72,205** | **98.73%** | **0.987** |
| CNN-LSTM | 706,133 | 98.66% | 0.986 |

**Key Findings:**
- **LSTM** achieved the best performance with minimal parameters, making it ideal for lightweight applications.
- **CNN** and **CNN-LSTM** also achieved high accuracy but required significantly larger model sizes.
- **Random Forest** remains an interpretable baseline model with strong results.

---

## Discussion

- Deep learning models outperform classical ML techniques due to their ability to capture temporal and spatial dependencies in ECG signals.
- **LSTM** networks, with their memory capability, efficiently learn long-term dependencies while remaining computationally efficient.
- The proposed models can be integrated into portable health monitoring devices for **real-time arrhythmia detection**.
- Future work includes exploring **Bi-LSTM** and **Transformer-based architectures**, as well as testing on larger datasets like **PTB-XL** or **CPSC 2018**.

---

## Report
This project was done as part of CSCI 5890 : Machine Learning for Healthcare curriculum. Find the complete project report here [link](https://github.com/1998anwesha/Arrythmia-classification-with-ML-DL-techniques/blob/main/Arrythmia_classification_report.pdf)

# Development-of-a-Deep-Learning-Based-EEG-Classifier-for-Early-Diagnosis-of-Dementia-

# EEG-Based Dementia Classification Using Deep Learning

This project implements deep learning models for classifying dementia types using EEG data. The goal is to detect Alzheimer's Disease (AD), Frontotemporal Dementia (FTD), and distinguish them from healthy controls (CN) based on resting-state EEG recordings.

## 🧠 Project Overview

- **Binary Classification (AD vs. CN)**:
  - Used **preprocessed EEG signals**
  - Implemented a **CNN model**
- **Multiclass Classification (AD vs. FTD vs. CN)**:
  - Used **raw EEG signals**
  - Implemented a **hybrid CNN-LSTM model** to capture both spatial and temporal features

This work is part of a research project exploring EEG-based biomarkers for early dementia diagnosis.

---

## 📁 Dataset

We used a publicly available dataset from [OpenNeuro](https://openneuro.org/datasets/ds004504/versions/1.0.7).  
It includes resting-state EEG recordings (eyes closed) for:

- Alzheimer's Disease (AD) patients
- Frontotemporal Dementia (FTD) patients
- Healthy Controls (CN)

The dataset includes `.set` files (EEGLAB format) and associated metadata (`participants.csv`).

> **Note**: Raw EEG data is not included in this repository due to size. Please download it separately from the source.

---

## 🧪 Methods

### Preprocessing (for binary classification):

- EEG data were filtered and segmented
- Non-artifact epochs were extracted
- Converted to time-domain feature arrays

### Model Architecture:

#### Binary (AD vs. CN):

- Convolutional Neural Network (CNN)
- Input: preprocessed EEG signals
- Output: binary softmax classification

#### Multiclass (AD vs. FTD vs. CN):

- CNN + LSTM hybrid
- Input: raw EEG signals
- CNN layers for spatial feature extraction
- LSTM layers for temporal dynamics
- Output: 3-class softmax

---

## 📊 Results (Optional Example Section)

| Task              | Model      | Accuracy |
| ----------------- | ---------- | -------- |
| Binary (AD vs CN) | CNN        | ~85%     |
| Multiclass        | CNN + LSTM | ~94%     |

---

## 📦 Project Structure

```plaintext
├── data/                      # EEG data folder (not uploaded)
│   └── preprocessed/          # Preprocessed EEG for binary
├── raw_data/                  # Raw .set EEG files
├── models/                    # Saved model weights (with the .h5 extensions)
├── notebooks/                 # Jupyter notebooks for training/evaluation
├── binary.ipynb             # Binary classification runner
├── multiclass.ipynb         # Multiclass classification runner
├── participants.csv           # Metadata
└── README.md
```

# 📚 Citaion

If you use this code or dataset, please cite the original dataset source:

Dataset Source: Open Neuro [https://openneuro.org/datasets/ds004504/versions/1.0.7]

## 🙌 Acknowledgements

This project was developed as part of a university course on deep learning and biomedical signal analysis.

Special thanks to our course supervisor and project team for guidance and support.

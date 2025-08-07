#  Lung Nodule Segmentation and Detection

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/Framework-TensorFlow%2FPyTorch-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

---

## � Project Overview

This project focuses on the automated detection of pulmonary nodules in CT scans using the LUNA16 dataset. We employ:

-  **U-Net** for precise segmentation of lung nodules.
-  **Convolutional Neural Networks (CNNs)** for classification and false positive reduction.

The goal is to build an **end-to-end pipeline** that accurately segments nodules and classifies candidates to aid in early lung cancer detection.

---

##  Dataset

We use the publicly available **LUNA16 (LUng Nodule Analysis 2016)** dataset:

- [LUNA16 Part 1 – Zenodo](https://zenodo.org/record/3723295)
- [LUNA16 Part 2 – Zenodo](https://zenodo.org/record/3723295)

> Please download both parts and extract them before running the preprocessing and training notebooks.

---

##  How to Proceed

-  You can use **VS Code** for local development and training.
-  For faster training, **Google Colab with TPU** is used for U-Net segmentation.

---

## � Architecture Overview

###  Pipeline Diagram

```mermaid
graph TD;
    A[Raw CT Scans] --> B[Preprocessing & Normalization]
    B --> C[Patch Extraction & Dataset Prep]
    C --> D[U-Net Model for Segmentation]
    D --> E[Mask Extraction]
    E --> F[ROI Selection]
    F --> G[Candidate Generation for FPR]
    G --> H[CNN Training for False Positive Reduction]
    H --> I[Final Evaluation]
````

---

##  Notebooks Breakdown

| Step | Notebook                     | Description                     |
| ---- | ---------------------------- | ------------------------------- |
| 1    | `01_prepro.ipynb`            | Initial CT scan preprocessing   |
| 2    | `01_data_prep.ipynb`         | Patch extraction and formatting |
| 3    | `01_data_analysis.ipynb`     | Exploratory Data Analysis       |
| 4    | `01_unet_train.ipynb`        | U-Net training for segmentation |
| 5    | `02_maskextract.ipynb`       | Extracting binary masks         |
| 6    | `03_ROI.ipynb`               | Selecting regions of interest   |
| 7    | `01_FPR_candidate_roi.ipynb` | Generating FPR candidates       |
| 8    | `02_FPR_dataset.ipynb`       | Building dataset for CNN        |
| 9    | `03_FPR_TRAIN.ipynb`         | CNN model training              |
| 10   | `04_FPR_CNN_eval.ipynb`      | Evaluating FPR model            |
| 11   | `LND_FINALE.ipynb`           | Final evaluation of pipeline    |

---

##  Evaluation Metrics

* **Segmentation**: Dice Score, Intersection-over-Union (IoU)
* **Classification (FPR)**: Accuracy, Precision, Recall, F1-score, Confusion Matrix

---

##  Installation

```bash
git clone https://github.com/Anshul-ydv/LungNoduleSegmentationAndDetection.git
cd LungNoduleSegmentationAndDetection
pip install -r requirements.txt
```

---

##  How to Run

> Follow the notebooks in sequence:

1. Start with `01_prepro.ipynb` to preprocess CT scan data
2. Train U-Net using `01_unet_train.ipynb`
3. Extract masks and define ROIs
4. Generate candidate ROIs and train CNN for FPR
5. Final evaluation in `LND_FINALE.ipynb`

---

##  Results Summary

| Metric | U-Net Dice Score | CNN Accuracy (FPR) |
| ------ | ---------------- | ------------------ |
| Value  | \~0.82           | \~0.91             |

---

##  Citation

If you use this repository for your research or project, please cite:

```bibtex
@misc{lungnodule2025,
  title={Lung Nodule Detection and False Positive Reduction using Deep Learning},
  author={Anshul Yadav},
  year={2025},
  howpublished={\url{https://github.com/Anshul-ydv/LungNoduleSegmentationAndDetection}},
  note={GitHub Repository}
}
```

---

##  Contact

For issues, suggestions, or collaboration, feel free to open an issue or contact via GitHub.
Or email - anshulyadav802@gmail.com

---

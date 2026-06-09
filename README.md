# Dog Breed Image Classification

Image classification of five dog breeds using three convolutional neural networks
(ResNet50, DenseNet121, and MobileNetV3) with transfer learning.

**Course:** Principle of Artificial Intelligence (ISB46703) — UniKL MIIT
**Domain:** Animal Subspecies (Dog Breeds)
**Classes:** Bulldog, Chihuahua, German Shepherd, Golden Retriever, Siberian Husky

## Team

> Check the names, student IDs, and roles below are correct before submitting.

| Name | Student ID | Role | Phase |
|---|---|---|---|
| Muhammad Harith bin Taufik | 52215123441 | Data Engineer | Part 1 — Data Preparation |
| Fahmie Firdaus bin Abdul Razak | 5221512XXXX | Data Scientist | Part 2 — Data Modelling |
| Muhammad Hakiem bin Taufik | 52215123442 | Data Analyst | Part 3 — Data Visualisation & Evaluation |

## Repository structure

```
.
├── README.md
├── .gitignore
├── Group_Project_Report.ipynb    The full report (opens on GitHub with all graphs visible)
├── Group_Project_Report.html     A read-only copy you can open in any web browser
├── models/                       The three trained models
│   ├── ResNet50.keras
│   ├── DenseNet121.keras
│   └── MobileNetV3.keras
├── metrics/                      Saved training results, read by the report
│   ├── results.json              Accuracy, mAP, parameters, and training time per model
│   ├── histories.json            Per-epoch training/validation accuracy and loss
│   └── class_names.json          The five class labels
├── outputs/                      Charts and the comparison table
│   ├── model_comparison.csv
│   ├── curves_*.png              Accuracy and loss graphs per model
│   ├── confusion_*.png           Confusion matrix per model
│   ├── compare_accuracy_map.png
│   └── efficiency.png
└── dataset/                      The cleaned image dataset
    ├── train/
    ├── val/
    └── test/
```

## How to read the report

Open `Group_Project_Report.ipynb` here on GitHub — it displays with every graph
already visible — or open `Group_Project_Report.html` in any web browser. Nothing
to install.

## How to re-run the analysis

The notebook reads its input files (the models, the JSON files, and the dataset)
from the **same folder it sits in**. In this repository those files are sorted into
folders for clarity, so to re-run the notebook:

1. Download the repository (Code -> Download ZIP, or `git clone`).
2. Copy the three `.keras` files from `models/` and the three `.json` files from
   `metrics/` into the same folder as `Group_Project_Report.ipynb`. The `dataset/`
   folder is already in the right place.
3. Open the notebook in Jupyter (Anaconda) or Google Colab.
4. Run cell `3.0` once to install the libraries, then run the cells from `3.1`
   onward.

> **Note:** Part 1 (image collection) and Part 2 (model training) are included for
> documentation only — they take hours to run and the trained models are already
> provided, so start at Part 3.

**Requirements:** Python 3.10+ with `tensorflow`, `scikit-learn`, `matplotlib`, and
`pandas`. Cell `3.0` installs these automatically. A GPU is not required for Part 3.

## Results

| Model | Test accuracy | mAP | Parameters | Training time |
|---|---|---|---|---|
| ResNet50 | 0.9131 | 0.9645 | 23.6 M | 619 s |
| DenseNet121 | **0.9313** | **0.9698** | 7.0 M | 587 s |
| MobileNetV3 | 0.9157 | 0.9657 | 3.0 M | 193 s |

**Conclusion:** DenseNet121 is the most suitable model for this task, giving the
highest accuracy and mAP at a moderate model size. MobileNetV3 is the best choice
when a small, fast model is needed, such as on a mobile device, at the cost of a
slightly lower accuracy.

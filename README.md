# EEG-Based Advertising Recall Prediction

**When Does Model Complexity Pay Off?**
A comparison of temporal and aggregated EEG representations for predicting unaided advertising recall.

> by: Amirhossein Jandaghian
>
> MSc Thesis in Management Engineering
>
> [Politecnico di Milano](https://www.polimi.it/), A.Y. 2025–26
>
> Supervised by Prof. Lucio Lamberti | Co-supervised by Marc-Antoine Fortin

---

## Abstract

This repository contains the end-to-end machine learning pipeline developed for my master's thesis. The goal: **predict whether a TV advertisement will be remembered by viewers — using EEG brain signals recorded during exposure.**

The research question is focused on the choice of **EEG representation**:

> does a complex temporal embedding (TS2Vec, FEMBA) outperform a simple aggregated feature set (Classic Mean) for recall prediction?

The pipeline includes data cleaning, feature engineering, model training, and comparative evaluation under consistent conditions. All three feed the same downstream classifier (Gradient Boosting) under identical train/test conditions, enabling a fair comparison of representation quality rather than modeling choices.

**Key result:**
- All three hit ~90% ROC-AUC.
- The simpler approach wins on discrimination.
- TS2Vec leads on recall (sensitivity).
- Model complexity does not automatically pay off; but temporal embeddings can offer practical advantages in this contexts.

---

## Repository Structure

- `analysis_notebooks/` — end-to-end notebooks (cleaning → features/embeddings → modeling/reporting)
  - `data_cleaning/` — survey + EEG preprocessing pipelines
  - `feature_engineering/` — exploration + feature/embedding preparation
  - `modeling/` — baseline + final report + embedding training report
- `data/` — raw/processed datasets, keys, and exports used by the notebooks
- `models/` — saved model artifact
- `report/`  — thesis manuscript and supporting material

---

## Data

> ⚠️ **Raw data is not included in this repository.**

The EEG recordings and participant questionnaire data were collected under a controlled experimental protocol at the Lab of Politecnico di Milano. Distribution is restricted by NDA agreement.

If you are a researcher interested in the dataset, contact eighter me to connect you with the supervisors or the Lab of Politecnico di Milano directly.

---

## Setup & Installation

### Requirements

- Python `3.12`
- Conda (Miniconda or Anaconda)

### Environment setup

```bash
git clone https://github.com/Ajandaghian/msc_advertising_recall_prediction_eeg.git
cd msc_advertising_recall_prediction_eeg

conda env create -f analysis_notebooks/thesis_env.yml
conda activate thesis_env
```

### How to Run

Open the notebooks in `analysis_notebooks/` and run them in order (the folder READMEs indicate the intended sequence).

```bash
jupyter notebook notebooks/
```

---

## Results

All three representations were evaluated on the same held-out test set using a fixed Gradient Boosting classifier.

| Representation | ROC-AUC | F1 | Recall | Precision | Accuracy | Total Time (s) | Interpretability |
|---|---|---|---|---|---|---|---|
| **Classic Mean** | **0.898** | 0.877 | 0.939 | 0.823 | 0.836 | **6.3** | ✅ High |
| **TS2Vec** | 0.893 | **0.885** | **0.956** | **0.825** | **0.845** | 385.3 | ✗ Low |
| **FEMBA** | 0.894 | 0.876 | 0.943 | 0.817 | 0.832 | 39.1 | ✗ Low |

**Bottom line:**
- All three approaches substantially outperform the prior benchmark (~80% accuracy) on the same experimental data
- Classic Mean achieves the highest ROC-AUC
- TS2Vec leads on recall — relevant when the cost of missing a high-performing ad is high such as this context.

---

## Contact

For questions or feedback, please connect and reach out to me on; I’d be happy to discuss the work, share insights, or explore collaborations!

**👓 Am. Jandaghian**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amirh-jandaghian/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Ajandaghian)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:amirh.jandaghian@gmail.com)
[![Website](https://img.shields.io/badge/Website-000000?style=for-the-badge&logo=About.me&logoColor=white)](https://jandaghian.me)

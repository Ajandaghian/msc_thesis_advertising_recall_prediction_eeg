# Analysis Notebooks

This folder contains the end-to-end analysis workflow, from cleaning raw data to feature design and final modeling reports.

## Folder Structure

```text
analysis_notebooks/
├── README.md
├── data_cleaning/
│   ├── README.md
│   ├── 1_survey_data_cleaning.ipynb
│   ├── 2_segments_bins_EEG_cleaning.ipynb
│   └── 0_raw_eeg_preprocessing_pipelines/
│       ├── README.md
│       ├── 0_imotions_raw_eeg_preprocessing.ipynb
│       └── 1_preprocessed_eeg_feature_preparation.ipynb
├── feature_engineering/
│   ├── README.md
│   ├── 0_data_exploration.ipynb
│   └── 1_feature_engineering.ipynb
└── modeling/
    ├── README.Md
    ├── 0.baseline_modeling.ipynb
    ├── 1.final_report.ipynb
    └── 2.embedding_training_report.ipynb
```

## Process Architecture

```text
Raw EEG + Survey
      |
      v
data_cleaning
  - EEG preprocessing and signal-level cleaning
  - Survey cleaning and score preparation
  - Segment/bin alignment and final merge
      |
      v
feature_engineering
  - EDA and data quality checks
  - Feature creation, transformation, and split strategy
      |
      v
modeling
  - Baseline benchmarking
  - Representation comparison
  - Training-time and cost analysis
```

Due to NDA constraints, parts of the original data assets, identifiers, and notebook-specific configuration details are intentionally excluded from this repository. As a result, these notebooks are shared primarily as a transparent showcase of the analytical methodology, code structure, and workflow logic, rather than as a fully executable end-to-end package. The process remains methodologically reproducible at the design level, while protected content is withheld to preserve confidentiality obligations.

## What Happens In Each Folder

### data_cleaning

- Cleans EEG and survey sources.
- Builds analysis-ready records by aligning participants, stimuli, segments, and bins.
- Includes both the core cleaning notebooks and the dedicated raw EEG preprocessing pipeline.

**data_cleaning/0_raw_eeg_preprocessing_pipelines**

- Handles low-level EEG preparation steps.
- Transforms raw sensor streams into stable EEG features used by later notebooks.
- Adds derived EEG metrics used in integration and modeling.

### feature_engineering

- Explores distributions, relationships, and consistency before modeling.
- Designs and refines model features.
- Defines preprocessing logic needed for robust training and evaluation.

### modeling

- Trains baseline models to establish a reference performance.
- Compares classic and embedding-based representations.
- Summarizes predictive performance and computational trade-offs.

## Overall Workflow Summary

The analysis follows a linear workflow:

1. Clean and align data in `data_cleaning`.
2. Explore and engineer features in `feature_engineering`.
3. Train, compare, and report models in `modeling`.

This structure keeps data preparation, feature design, and model evaluation clearly separated while preserving a single end-to-end process.
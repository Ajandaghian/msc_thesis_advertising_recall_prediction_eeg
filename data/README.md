# Data Directory

This folder contains the project data lifecycle, from original inputs to modeling-ready datasets and supporting reference materials.

## Folder Structure

```text
data/
├── README.md
├── raw/
│   ├── experiment_and_survey/
│   └── sample_sensor_data/
│
├── processed/
│   ├── eeg/
│   │   ├── preprocessed/
│   │   └── separated/
│   └── ad_break_level_meta/
│
├── final_for_modeling/
│
│
└── other/
```


Due to NDA constraints, selected source assets and sensitive identifiers are intentionally restricted. This repository therefore shares the data organization, transformation logic, and analytical structure as a professional showcase of the pipeline, while excluding protected material that would be required for full end-to-end re-execution.

## What Happens In Each Folder

### raw

- Stores original experiment and survey inputs.
- Serves as the immutable starting point for all downstream processing.

### processed

- Contains cleaned and standardized outputs derived from raw inputs.
- Organizes EEG data, ad-break-level metadata, and key-linking tables used across the pipeline.

### final_for_modeling

- Provides final, join-ready datasets used for training and evaluation.
- Includes consistency checks and temporary cached artifacts supporting modeling workflows.

### other

- Holds auxiliary materials such as stimuli assets and reference tables.
- Supports interpretation and diagnostics without being the core modeling input layer.

## Overall Workflow Summary

The data pipeline follows a linear flow:

1. Ingest and preserve sources in `raw`.
2. Clean and harmonize data in `processed`.
3. Prepare train/evaluation-ready datasets in `final_for_modeling`.
4. Track benchmark and timing evidence through top-level reporting files.

This structure keeps source control, transformation stages, and modeling readiness clearly separated while maintaining a consistent and auditable data workflow.
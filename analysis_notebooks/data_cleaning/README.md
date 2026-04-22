# Data Cleaning

This folder prepares EEG and survey data into clean, merge-ready tables for feature engineering and modeling.

## Process (in order)

1. [0_raw_eeg_preprocessing_pipelines/0_imotions_raw_eeg_preprocessing.ipynb](analysis_notebooks/data_cleaning/0_raw_eeg_preprocessing_pipelines/0_imotions_raw_eeg_preprocessing.ipynb)
   Clean raw iMotions EEG, segment by events, bin time windows, extract PSD band features, and flag bad channels.

2. [0_raw_eeg_preprocessing_pipelines/1_preprocessed_eeg_feature_preparation.ipynb](analysis_notebooks/data_cleaning/0_raw_eeg_preprocessing_pipelines/1_preprocessed_eeg_feature_preparation.ipynb)
   Build final EEG-derived features from preprocessed segments.

3. [1_survey_data_cleaning.ipynb](analysis_notebooks/data_cleaning/1_survey_data_cleaning.ipynb)
   Clean survey responses, encode scales, and reshape to long format by participant-stimulus.

4. [2_segments_bins_EEG_cleaning.ipynb](analysis_notebooks/data_cleaning/2_segments_bins_EEG_cleaning.ipynb)
   Merge cleaned EEG and survey data, remove invalid/missing values, and apply final outlier checks.

## Main Outputs

- EEG preprocessing outputs in [data/processed/eeg/preprocessed](data/processed/eeg/preprocessed):

- EEG quality metrics in [data/processed/eeg/metrics.txt](data/processed/eeg/metrics.txt) and [data/processed/eeg/metrics.pkl](data/processed/eeg/metrics.pkl)

- Survey-cleaning outputs (from notebook 3):
  - ad-break-level metadata parquet table
  - separated parquet tables: surveys, participants, experiments, experiments_long, targets_long

- Segment-cleaning parquet outputs (from notebook 4):
  - segments_obt.parquet
  - bin5s_obt.parquet
  - temporal_ad_break_level_PESR_data.parquet

- Segment-survey join outputs (from notebook 4):
  - segment_and_survey_final_keys.csv
  - final_segments_keys.csv


## Notes

Run notebooks top-to-bottom.
Outputs are timestamped to preserve run history.
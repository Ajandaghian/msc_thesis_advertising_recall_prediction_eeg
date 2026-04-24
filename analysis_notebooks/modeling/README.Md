# Modeling

This folder contains the final modeling notebooks used to train, evaluate, and report ad-recall prediction performance from engineered EEG representations.

## Notebooks

1. [0.baseline_modeling.ipynb](0.baseline_modeling.ipynb)
	Build and evaluate baseline models on the prepared modeling tables, with a focus on classic feature-based pipelines.

2. [1.final_report.ipynb](1.final_report.ipynb)
	Consolidate final model comparisons, summarize metrics, and generate report-ready tables/figures for the thesis.

3. [2.embedding_training_report.ipynb](2.embedding_training_report.ipynb)
	Analyze embedding generation and model training time/performance trade-offs and export timing summaries.

## Main Inputs

- Final modeling-ready data from [../../data/final_for_modeling](../../data/final_for_modeling)
  - `train_ad_break_level_data.parquet`
  - `test_ad_break_level_data.parquet`
  - `segment_df.parquet`
  - `bin_ts2vec_emb_df.parquet`
  - `bin_femba_emb_df.parquet`

- Shared key file from [../../data/final_ad_break_session_keys.csv](../../data/final_ad_break_session_keys.csv)

## Main Outputs

- [../../data/model_training_report.csv](../../data/model_training_report.csv)
- [../../data/embedding_time_report.csv](../../data/embedding_time_report.csv)
- Final performance summaries and comparison plots rendered in the notebooks.

## Notes

- Run notebooks from top to bottom and keep the same execution order for reproducibility.
- Start this folder only after the data cleaning and feature engineering pipelines are complete.

# Feature Engineering

This folder prepares the study tables and EEG-derived features for downstream modeling. The notebooks first inspect the available variables and then transform them into compact, model-ready representations at session, segment, and bin level.

## Notebooks

1. [0_data_exploration.ipynb](0_data_exploration.ipynb)
	Explore the structure of the available tables, check target balance, review timing and session patterns, inspect participant-level variables, and assess relationships among survey-based measures and the target.
	- Load the main study tables and compare their available fields and keys.
	- Review the distribution of the target and the most relevant categorical and numerical variables.
	- Check session timing, repeated exposure patterns, participant coverage, and sequence consistency.
	- Inspect survey-based measures with descriptive statistics, correlation analysis, and simple statistical tests.
	- Summarize the findings that motivate feature selection and later modeling choices.

2. [1_feature_engineering.ipynb](1_feature_engineering.ipynb)
	Build the final feature tables by creating stable session keys, deriving session-level and participant-level variables, consolidating related survey items into composite indices, selecting informative EEG feature families, and comparing alternative sequence representations.
	- Create a unique session key and filter tables to the aligned sessions used in modeling.
	- Derive session-level variables such as ad position, exposure order, duration categories, and repetition flags.
	- Convert survey items into composite indices to reduce dimensionality and keep the most meaningful constructs.
	- Apply participant-aware train/test splitting to avoid leakage across subjects.
	- Standardize the selected numerical inputs and recode ordinal values where needed.
	- Select EEG feature groups, compare candidate transformations with statistical tests, and retain the most informative feature families.
	- Build segment-level and bin-level representations, then generate averaged and embedding-based outputs for downstream experiments.

## Main Outputs

- Cleaned and enriched session-level metadata ready for modeling.
- Segment-level EEG feature tables with selected feature families and derived indicators.
- Bin-level EEG sequences prepared for aggregation and embedding-based representations.
- Group-aware train/test splits designed to avoid leakage across participants.
- Final model-ready tables that can be joined through the shared session key.

## Notes

- Run the notebooks from top to bottom.
- The workflow is designed to keep feature construction, selection, and export steps reproducible.
- The final tables are organized so they can be combined consistently in later modeling notebooks.

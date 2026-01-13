Project Scope



Goals

Prepare the Pokémon with stats dataset for machine learning by cleaning, validating, and transforming it into a model-ready feature set. Document every major decision (missing values, feature engineering, encoding, splitting) in a reproducible Jupyter Notebook. Produce a final processed dataset and training/testing splits that could be used directly for modeling.



Dataset

Pokemon with stats.csv (Kaggle). Unit of observation: one row per Pokémon (including forms if present). Expected fields include base stats (HP, Attack, Defense, Sp. Atk, Sp. Def, Speed), typing (Type 1, Type 2), Generation, and a Legendary flag.



ML Problem (Chosen)

Binary classification: predict whether a Pokémon is Legendary using stats + type information. Target variable: Legendary.



Planned Analysis Steps

Load and validate schema and data types.

Check missing values, duplicates, and inconsistent categories.

Clean and standardize columns (names, types, categories).

Handle missing Type 2 and any other missingness with explicit rules.

Perform exploratory data analysis: distributions, correlations, class imbalance, and key comparisons between Legendary vs non-Legendary.

Build a preprocessing pipeline to generate model-ready features (one-hot encoding for categorical features, optional scaling for numeric features).

Split into train/test (and optionally validation) with a fixed random seed and stratification on the target.



Outputs

A notebook: notebooks/01\_data\_prep.ipynb showing the full workflow and reasoning.

A saved processed dataset file in data/processed/ (e.g., pokemon\_processed.csv).

Final X\_train, X\_test, y\_train, y\_test objects created in the notebook.



Evaluation / Success Criteria

Processed dataset has no unexpected nulls in required features.

All feature columns are numeric after preprocessing.

Train/test split is reproducible (fixed seed) and preserves class balance (stratified).

Notebook is readable and explains the “why” behind decisions.


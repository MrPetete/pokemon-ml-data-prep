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



Data Analysis Problem

Can we prepare a clean, model-ready dataset to predict whether a Pokémon is Legendary using its base stats and typing information?



Target (y)

Legendary (boolean / 0–1)



Initial Features (X)

Numeric: HP, Attack, Defense, Sp. Atk, Sp. Def, Speed (and optionally Total)

Categorical: Type 1, Type 2, Generation



Assumptions / Notes

Type 2 can be missing and will be treated as “None”.

We will avoid leakage: do not use columns that directly encode “Legendary” or obvious identifiers that leak target.

We will keep one row per Pokémon entry as given in the dataset (no external merges).



RESULT



Results and Key Insights

Data quality: only Type 2 had missing values; filled missing Type 2 with “None”. No duplicates found.

Class balance: Legendary is imbalanced (65 Legendary vs 735 non-Legendary).

Stat differences: Legendary Pokémon have much higher average Total stats (~637 vs ~417) and higher averages across all individual stats.

Generation pattern: Legendary counts vary by generation, with Gen 3 highest in this dataset.



\### Visuals



\*\*Total stats by Legendary\*\*

!\[Total stats by Legendary](reports/figures/total\_by\_legendary.png)



\*\*Legendary count by generation\*\*

!\[Legendary by generation](reports/figures/legendary\_by\_generation.png)



\*\*Top 10 Type 1 distribution\*\*

!\[Top 10 Type 1](reports/figures/top10\_type1.png)




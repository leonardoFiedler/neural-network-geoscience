# Neural Network And Geoscience

The objective of this study is to use Neural Network`s with PyTorch to classify over 12 classes a rock type.

## Types of Rock

Based on column `FORCE_2020_LITHOFACIES_LITHOLOGY`

• 30000: Sandstone

• 65030: Sandstone/Shale

• 65000: Shale

• 80000: Marl

• 74000: Dolomite

• 70000: Limestone

• 70032: Chalk

• 88000: Halite

• 86000: Anhydrite

• 99000: Tuff

• 90000: Coal

• 93000: Basement

## How to Execute the project

```
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Study

The study is dividided in:

1. Analyse data
2. Baseline With Decision Tree Classifier
3. 3 Different Arquitetures teste
4. Generate predictions of a hidden file

### Analyse Data and Baseline With Decision Tree Classifier

The analysis and Decision Tree can be found on `Base_Analyze.ipynb`. This file load data and analyse based on Decision Tree algorithm with unbalanced and balanced Data.

In Unbalanced data, the result was `92.35%` and with balanced data with SMOTE (Sinthetic Minotiry Oversampling Technique) was `98.88%`.



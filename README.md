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
3. Different Neural Network Architectures test
4. Generate predictions of a hidden file

### Analyse Data and Baseline With Decision Tree Classifier

The analysis and Decision Tree can be found on `Base_Analyze.ipynb`. This file load data and analyse based on Decision Tree algorithm with unbalanced and balanced Data.

In Unbalanced data, the result was `92.35%` and with balanced data with SMOTE (Sinthetic Minotiry Oversampling Technique) was `98.88%`.

### Different Neural Network Architectures test

The table below describe the tests made with Neural Network. The objective was to start with just few data and add more or change model according to the results.

| Number | Model Name                            | Max Num Samples Per Class | SMOTE? | Num Epochs | Train Acc | Train Loss | Val Acc | Val Loss | Test Precision | Test Recall | Test F1-Score |
|--------|---------------------------------------|---------------------------|--------|------------|-----------|------------|---------|----------|----------------|-------------|---------------|
| 1      | single_layer                          | 10000                     | False  | 100        | 77.390%   | 0.65312    | 74.709% | 0.68731  | 0.79           | 0.75        | 0.76          |
| 2      | multi_layer                           | 10000                     | False  | 100        | 72.729%   | 0.84311    | 72.398% | 0.75672  | 0.76           | 0.72        | 0.73          |
| 3      | multi_layer                           | 50000                     | False  | 1000       | 59.464%   | 1.14423    | 64.466% | 1.02543  | 0.67           | 0.64        | 0.63          |
| 4      | multi_layer_relu                      | 10000                     | False  | 100        | 88.023%   | 0.39305    | 87.399% | 0.40415  | 0.88           | 0.87        | 0.87          |
| 5      | multi_layer_relu_batch_norm           | 10000                     | False  | 100        | 92.029%   | 0.21409    | 91.749% | 0.19964  | 0.92           | 0.92        | 0.92          |
| 6      | multi_layer_relu_batch_norm           | 10000                     | True   | 100        | 93.801%   | 0.17439    | 94.958% | 0.13612  | 0.95           | 0.95        | 0.95          |
| 7      | multi_layer_3_relu_batch_norm_dropout | 20000                     | True   | 300        | 69.476%   | 0.75197    | 72.979% | 0.60935  | 0.74           | 0.73        | 0.72          |

#### Table Definition

1. Number: Test Number

2. Model Name: Name of the model

3. Max Num Samples Per Class: The maximum number of classes per class for all, train/valid/test

4. SMOTE? Boolean that indicates if the test used augmented data or not

5. Num Epochs: Number of epochs

6. Train Acc: Last epoch train accuracy

7. Train Loss: Last epoch train loss

8. Val Acc: Last epoch valid accuracy

9. Val Loss: Last epoch valid loss

10. Test Precision: Weighted test precision

11. Test Recall: Weighted test recall

12. Test F1-Score: Weighted test F1-Score

Important: Some of models were exectued more than once and some values may vary a little.

### Generate predictions of a hidden file

As the result above, we save 2 models in `data/model` folder:

1. Test 5 with 92% of test precision (unbalanced data)
2. Test 6 with 95% of test precision (balanced data)

The inferences were executed in `Inference_Model.ipynb` file. The result generates are in `data/output` folder.

### Conclusion

In this homework I could learn more about PyTorch, unbalanced and balanced data and multiple kind of test. Unfortunatelly, for a higher results, more data should be added in some classes to balance and with more analysis on each variable, some of them could be removed (or outliers and others).
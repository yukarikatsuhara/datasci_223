# Explain your choices, process, and outcomes.
# List of collablrators
Wu Hailiang

# How to run
1. Open excercise.ipynb (https://github.com/yukarikatsuhara/datasci_223/blob/main/exercises/4-classification/exercise.ipynb)
2. Clear outputs (if any)
3. Run all in a fresh virtual enviroment (no dependencies other than jupyter)

# Overview of this project
1. Classify all symbols
    1. Model: XGBoost
    2. Process
        1. Load train and valid datasets from emnist.
        2. (If the preliminary analysis is needed) Sample down the train and valid datasets.
        3. Devide the train data to train and test datasets. The test datasets is used for invastigating subsets and improving the performance.
        4. Build the XGBoost model
        5. Investigate subsets, O and 0 etc.
        6. Improve the model's performance using cross-validation.
        7. Report the best model's performance using the valid dataset.
    3. Outcome

       The sampled train and valid datasets are used because my computational resources are not enough to analyze the all data. (Sampled test data: 5000, Sampled valid data: 2000) are used. Regarding the investigation of the subsets, the XGBoost model is not fitted for the classification of O vs 0 and l vs 1. After improving the performance using 3-fold cross-validation, the best model is built ('learning_rate': 0.05, 'max_depth': 3, 'min_child_weight': 2, 'n_estimators': 100, 'subsample': 0.8). The performance of the best model in the sampled valid data is below.

       **Accuracy: 0.64, Precision: 0.60, Recall: 0.64, F1: 0.60**

2. CLassify digits or letters
    1. Model: XGBoost and Logistic Regression
    2. Process
        1. Load train and valid datasets from emnist.
        2. (If the preliminary analysis is needed) Sample down the train and valid datasets.
        3. Create a column for whether each row is a digit(=0) or a letter(=1) in train and valid datasets
        3. Choose an evaluation metric: F1
        4. Build the XGBoost and Logistic Regression models using the train dataset with 5-fold cross-validation.
        5. Improve the models' performance using the 3-fold cross-validation.
        6. Choose the winning model with the highest F1 score.
        7. Report the winning model's performance using the valid dataset.
    3. Outcome

       The sampled train and valid datasets are used because my computational resources are not enough to analyze the all data. (Sampled test data: 5000, Sampled valid data: 2000) are used. After improving the performance using 3-fold cross-validation, the winning model is chosen based on the F1 score. The winning model is the XGBoost model ('learning_rate': 0.1, 'max_depth': 5, 'min_child_weight': 2, 'n_estimators': 200, 'subsample': 0.8). The performance in the sampled valid dataset is below.

       **Accuracy: 0.83, Precision: 0.83, Recall: 0.83, F1: 0.83**

# Notes on any difficulties encountered
## Learning the Analysis Flow of Supervised Learning
This assignment was instrumental in teaching me the analysis flow of supervised learning. It highlighted the importance of practical experience alongside theoretical knowledge in the field.

## Data Sampling Issues
One significant challenge I faced was during the preliminary analysis phase, where the sample size was too small, leading to incomplete analysis. This issue was critical because it directly impacted the reliability and validity of the analysis results.

### Solution: Stratified Sampling
To address this, I implemented stratified sampling to ensure that all labels were adequately represented in the subsets. This approach allowed for a more balanced and comprehensive analysis, improving the robustness of the findings.

## Hyperparameter Tuning for XGBoost Model
Determining the best hyperparameters for the XGBoost model presented another significant challenge. Despite creating code similar to that used for classifying digits, the analysis process was exceedingly time-consuming and failed to complete, even after downsampling the data.

### Insight: Importance of Computational Resources
This experience underscored the crucial role of appropriate computational resources in efficient machine learning. It became evident that having access to powerful computing environments is as vital as possessing the requisite knowledge in machine learning. This realization has profound implications for my future projects, highlighting the need to balance technical skills with the right tools and resources.

# Assignment link
https://github.com/yukarikatsuhara/datasci_223/blob/main/exercises/4-classification/exercise.ipynb

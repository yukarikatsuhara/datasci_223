# Assignment 4-5

# List of collablrators
Wu Hailiang

# How to run
1. Open excercise.ipynb (https://github.com/yukarikatsuhara/datasci_223/blob/main/exercises/4-classification/exercise4-5.ipynb)
2. Clear outputs (if any)
3. Run all in a fresh virtual enviroment (no dependencies other than jupyter)

# Overview of this project
1. Classify letters
    1. Model: XGBoost
    2. Process
        1. Load train and valid datasets from emnist.
        2. Build the subset including a,b,c,d,e,f,g.
        3. (If the preliminary analysis is needed) Sample down the subset.
        4. Devide the subset to train and validation datasets. The test datasets is used for invastigating subsets and improving the performance.
        5. Build the XGBoost model.
        6. Investigate subsets, a vs b etc.
        7. Improve the model's performance using cross-validation. (Evaluation metic: F1)
        8. Train the best model on the full train dataset
        9. Report the best model's performance using the validation dataset.
    3. Outcome

       The sampled train and valid datasets are used because my computational resources are not enough to analyze the all data. (Sampled test data: 5600, Sampled validation data: 2400) Regarding the investigation of the subsets, the XGBoost model is not fitted for the classification of c vs d although a vs b and c vs e is well classified. After improving the performance using 3-fold cross-validation, the best model is built ('max_depth'=5, 'min_child_weight'=3, 'n_estimators'=700, 'learning_rate': 0.2, 'subsample': 0.5,'gamma': 5). The performance of the best model in the validation data is below.

       **Accuracy: 0.93, Precision: 0.92, Recall: 0.93, F1: 0.92**

2. CLassify upper or lowercase
    1. Model: XGBoost and Logistic Regression
    2. Process
        1. Load train and valid datasets from emnist.
        2. Build the subest including a, b, c, x, y z, A, B, C, X, Y and Z.
        3. (If the preliminary analysis is needed) Sample down the subset.
        4. Devide the subset to train and validation datasets. The test datasets is used for invastigating subsets and improving the performance.
        5. Choose an evaluation metric: F1
        6. Build and improve the XGBoost and Logistic Regression models using the train dataset with 3-fold cross-validation.
        7. Choose the winning model with the highest F1 score.
        8. Train the best model on the full train dataset
        9. Report the winning model's performance using the valid dataset.
    3. Outcome

       The sampled train and validation datasets are used because my computational resources are not enough to analyze the all data. (Sampled test data: 5600, Sampled validation data: 2400) are used. After improving the performance using 3-fold cross-validation, the winning model is chosen based on the F1 score. The winning model is the XGBoost model ('max_depth'=5, 'min_child_weight'=3, 'n_estimators'=700, 'learning_rate': 0.2, 'subsample': 0.5,'gamma': 5). The performance in the sampled valid dataset is below.

       **Accuracy: 0.81, Precision: 0.82, Recall: 0.81, F1: 0.81**
       
# Notes on any difficulties encountered
## Learning the Analysis Flow of Supervised Learning
This assignment was instrumental in teaching me the analysis flow of supervised learning. It highlighted the importance of practical experience alongside theoretical knowledge in the field.

## Data Sampling Issues
One significant challenge I faced was during the preliminary analysis phase, where the sample size was too small, leading to incomplete analysis, especially in the original question 1: classyfy all symbols including upper and lowercase letters. This issue was critical because it directly impacted the reliability and validity of the analysis results.

### Solution: Stratified Sampling
To address this, I implemented stratified sampling and set the appropriate case number to ensure that all labels were adequately represented in the subsets. This approach allowed for a more balanced and comprehensive analysis, improving the robustness of the findings.

## Hyperparameter Tuning for XGBoost Model
Determining the best hyperparameters for the XGBoost model presented another significant challenge. When I tried to search parameters broadly, the analysis process was exceedingly time-consuming and failed to complete in Google colab, even after downsampling the data.

### Insight: Importance of Computational Resources
Wynton server is used to get the results. However, I needed to narrow down the candidate parameters to complete the analysis to reduce the calculation time even if I used the Wynton server. This experience underscored the crucial role of appropriate computational resources in efficient machine learning. It became evident that having access to powerful computing environments is as vital as possessing the requisite knowledge in machine learning. This realization has profound implications for my future projects, highlighting the need to balance technical skills with the right tools and resources.

# Assignment link
https://github.com/yukarikatsuhara/datasci_223/blob/main/exercises/4-classification/exercise4-5.ipynb

# Predicting-Credit-Risk

## Overview
The purpose of this analysis is to utilize supervised machine learning algorithms to predict credit risk. Data was sourced from LendingClub. The dataset was for over 100,000 applications from Q1 2019. This analysis was conducted on the ~69,000 issued loans. Over 80 [variables](https://help.lendingclub.com/hc/en-us/articles/215488038-What-do-the-different-Note-statuses-mean-) were used as features in the machine learning models. The LendingClub dataset has an unbalanced classification problem, since high risk loans are far outnumbered by low risk loans. Because of this, the models used throughout this analysis aim to accommodate that limitation. Algorithms used include: RandomOverSampler, SMOTE, ClusterCentroids (for Undersampling), SMOTEENN, Balanced Random Forests, and Easy Ensemble Classifier. 

Required dependencies: Pandas, Sci-kit learn, imbalanced learn, numpy.

## Results
### Preview of the Data
The following is a preview of the training and testing data after preprocessing for all models in this analysis. Stratification was used due to the imbalance between classes of the target variable, loan status.

![image](https://user-images.githubusercontent.com/93338132/165002563-3a67a52f-043a-4492-a876-2b233c996e53.png)

### Results Summary 

Results for the models are measured with three main metrics in this analysis: [Balanced Accuracy Score](https://datascience.stackexchange.com/questions/73974/balanced-accuracy-vs-f1-score), Precision (true positives/true positives+false positives), and Recall (true positives/true positives+false negatives). A true positive in this analysis is a high risk loan correctly predicted by the model.

Example confusion matrix
![image](https://user-images.githubusercontent.com/93338132/165003923-3bc84231-fe61-48bb-a9b4-083ede746e19.png)

The following table summarizes results by model. Precision and Recall (sensitivity) are shown for high risk loan identification, as that is what this model is ultimately trying to identify. Detailed results for each model are in following sections.


| Model | Balanced Accuracy Score | Precision (for high risk) | Recall (for high risk)
| --- | --- | --- | --- |
| Random Oversampling | 64.56% | 0.01 | 0.61 |
| SMOTE Oversampling | 62.34% | 0.01 | 0.61 |
| Cluster Centroid Undersampling | 52.19% | 0.01 | 0.59 |
| SMOTEENN | 63.96% | 0.01 | 0.70 |
| Balanced Random Forest  | 78.78% | 0.04 | 0.67 |
| Easy Ensemble | 92.54% | 0.07 | 0.91 |

### Random Oversampling 
![image](https://user-images.githubusercontent.com/93338132/165003228-52606587-ad5a-43c7-a633-607b836d0c8f.png)

The first model gives us a good starting point, though our balanced accuraxy score suggests room to improve.

### SMOTE Oversampling
![image](https://user-images.githubusercontent.com/93338132/165003247-88e8347b-5fac-49af-8aaa-4dfa349e89c3.png)

SMOTE does not improve on the results of the Random Oversampling (OS) model.

### Cluster Centroid Undersampling
![image](https://user-images.githubusercontent.com/93338132/165003281-1688bd95-eb4a-4c0a-8ae7-79ebe5b6c993.png)

CC Undersampling produces worse results than either OS models.

### SMOTEEN 
![image](https://user-images.githubusercontent.com/93338132/165003311-d874aa11-a68b-4fe2-b357-4416c1f38328.png)

SMOTEEN produces similar results to the first two OS models for Balanced Accuracy Score (BAS) and Precision, and improves Recall.

### Balanced Random Forest
![image](https://user-images.githubusercontent.com/93338132/165003378-1147f63a-ef8b-4860-88e3-2986862ae682.png)

The Balanced Random Forest model produces better results than all previous models on all three metrics.

### Easy Ensemble 
![image](https://user-images.githubusercontent.com/93338132/165003414-ced51d44-25c4-450b-a0a1-e063e10d9a17.png)

The Easy Ensemble model improves further on all three metrics! Only 8 of 87 high risk loans were misclassified as low risk.

## Summary and Recommendations

Here are the summarized results, shown again.

| Model | Balanced Accuracy Score | Precision (for high risk) | Recall (for high risk)
| --- | --- | --- | --- |
| Random Oversampling | 64.56% | 0.01 | 0.61 |
| SMOTE Oversampling | 62.34% | 0.01 | 0.61 |
| Cluster Centroid Undersampling | 52.19% | 0.01 | 0.59 |
| SMOTEENN | 63.96% | 0.01 | 0.70 |
| Balanced Random Forest  | 78.78% | 0.04 | 0.67 |
| Easy Ensemble | 92.54% | 0.07 | 0.91 |

The Easy Ensemble model correctly identifies 91% of high risk loans, and has a balanced accuracy score of 92.5%, suggesting that there are minimal low risk loans erroneously classified as high risk. In short, the model succeeds at minimizing losses from high risk loans, and maximizes revenue by correctly identifying low risk loans. 

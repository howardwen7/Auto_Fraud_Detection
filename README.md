# Auto Fraud Detection
## Project Background
According to one statistic, an estimate of more than 10% of all property/casualty insurance claims may be fraudulent. When these cases go undetected, insurance companies have to pass down excess losses as increased premiums to consumers. Even though comprehensive investigation can be implemented for each claim to identify fraud, it is a manual process that costs a lot and results in longer processing time. 

## Project Goals
My goal is to predict whether a given claim with vehicle and demographic characteristics is fraudulent or not. My main metric is the F-score, defined as the harmonic mean of precision and recall. We are also interested in identifying features important in predicting frauds.

## Data Description
The dataset consists of ~18000 claims and 23 features. The target is binary yes/no fraudulent.

## Methodology
### ML Techniques
I compared the performance of the following five algorithms: logistic regression, random forest, adaptive boosting, naïve Bayes, and KNN. The first three yield better performance than the rest and a stacked model was built based on the three models. 

### Sampling Techniques
Since only about 15% of claims are fraudulent, the dataset is moderately imbalanced. I experimented with no sampling, undersampling, and oversampling. I found undersampling to perform a lot better than no sampling. 

## Performance Evaluation
With minimum preprocessing, a simple XGBoost model yields an F-score of 0.33. After some preprocessing, each of the three models (logistic regression, random forest, and adaptive boosting) yields an F-score of 0.36-0.37. However, a stacked model selecting the most frequently predicted outcome out of the three models produces an F-score of 0.39, an 8% increase as compared with using just any one of the three models only. 


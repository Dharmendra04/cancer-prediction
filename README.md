# cancer-prediction---using-logistic-regression-and-naive-bayes

# Introduction
This data set is obtained from Kaggle datasets, it’s about predicting whether a patient has breast cancer or not using different physical properties related to characteristics of tumours, such as their size, shape, and texture. There are 30 features in the datasets and each feature are continuous variables.

For Logistic regression, the average accuracy score for k_folds in range of 3 -20 is almost similar, for most of the k_folds. Though k_folds like 7,8,12,15,16 and 18 has the highest average accuracy score. As we need to consider about the amount of data in each fold (near to 100 datasets in each fold), 7 or 8 is chosen as the optimum k_folds (569/8 = 72). Then with the help of standard deviation, 7 is chosen as the optimum k_fold as the standard deviation of 7 is less than 8.

When considering the Naive bayes model the average accuracy score of k_folds like 8 and 18 is the highest when comparing with other k_folds. So, 8 is chosen considering that there should be sufficient amount of data in each split while training. There is no need of plotting standard deviation as the decision can be made only from average accuracy score

# Analysis

<p align="center">
  <img src="https://github.com/Dharmendra04/cancer-prediction---using-logistic-regression-and-naive-bayes/blob/main/Screenshot%202023-06-02%20at%2002.10.36.png">
  <br />
  <em>Figure 3: Dfferent Metrics used  </em>
</p>

Based on the comparison, it appears that the naive Bayes model may be more suitable for predicting breast cancer. This is because the naive Bayes model has a higher precision, accuracy, specificity, and AUC for both the precision-recall curve and the ROC curve, which generally indicates better performance.
In this case, it is important to carefully consider the implications of false negatives and false positives. A false negative, where the model predicts that a person does not have breast cancer when they actually do, could have serious consequences as the person may not seek treatment. On the other hand, a false positive, where the model predicts that a person has breast cancer when they actually do not, could lead to unnecessary stress and potentially harmful follow-up procedures.
In general, a model with a higher precision and a lower false positive rate may be more suitable for predicting breast cancer, as it is important to minimize the number of false positives. However, it is also important to consider the recall of the model and the consequences of false negatives. It may be necessary to consider other factors, such as the cost of follow-up procedures and the overall prevalence of breast cancer in the population, when deciding about which model to use.
A better way to solve all this problem is to use ensemble learning technique and use these models as base classifiers, so a better model can be achieved.

# Mathematical Resons for the results
The feature values are continuous (no Bernoulli) and the outcome simply binary (cancer or no cancer, so no multivariate), so according to these properties it can be easily identified that gaussian distribution will fit on the naïve bayes classifier for this dataset. Neither Bernoulli nor multivariate cannot be chosen as the distribution here.

The AUC value of ROC curve is 0.48 for logistic regression and accuracy is less: This can be due to the incapability of this logistic regression model to find the complex relationships between the features and the target variable.
Another reason for this can the effect of a single predictor variable on the outcome is analysed while holding all other predictor variables constant. This can be useful for understanding the individual contribution of each predictor variable to the outcome, but it may not accurately capture the complexity of real-world data, where multiple predictor variables may be correlated and interact with each other in complex ways.
For example, let’s consider two feature variables, radius means, and smoothness means. The effect of radius mean on the outcome will be analysed separately from the effect of smoothness mean, and any potential interactions between these variables will not be captured by the model.
In case of naïve bayes model though it gives good value for most of the metrics, its values are not reaching 90% or more in any of the metrics. Since this is a probabilistic model that assumes that the predictor variables are independent, which means that the presence or absence of one predictor variable does not affect the probability of the other predictor variables. Specially cancer dataset is having some correlation between features.
For example, in a study of breast cancer, the risk of developing breast cancer may be higher for higher radius means and low smoothness mean patient compared to those with low radius means and high smoothness person. This dependency may not be captured by the naïve bayes model. These can be a reason for the slightly reduced metric value than the best classifiers.


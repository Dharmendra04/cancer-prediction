# cancer-prediction---using-logistic-regression-and-naive-bayes

# Introduction
This data set is obtained from Kaggle datasets, it’s about predicting whether a patient has breast cancer or not using different physical properties related to characteristics of tumours, such as their size, shape, and texture. There are 30 features in the datasets and each feature are continuous variables.

For Logistic regression, the average accuracy score for k_folds in range of 3 -20 is almost similar, for most of the k_folds. Though k_folds like 7,8,12,15,16 and 18 has the highest average accuracy score. As we need to consider about the amount of data in each fold (near to 100 datasets in each fold), 7 or 8 is chosen as the optimum k_folds (569/8 = 72). Then with the help of standard deviation, 7 is chosen as the optimum k_fold as the standard deviation of 7 is less than 8.

When considering the Naive bayes model the average accuracy score of k_folds like 8 and 18 is the highest when comparing with other k_folds. So, 8 is chosen considering that there should be sufficient amount of data in each split while training. There is no need of plotting standard deviation as the decision can be made only from average accuracy score

<p align="center">
  <img src="https://github.com/Plymouth-University/2023-comp5013-gp-neural_ninjas/blob/main/Picture_work_flow.png">
  <br />
  <em>Figure 3: Flow chart of the work </em>
</p>



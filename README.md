# Beta Banks Customer Churn Prediction

## Introduction
Beta Banks has noted a gradual decline in its customer base and has recognized the importance of retaining existing customers rather than acquiring new ones. To address this challenge, I have been assigned the task of predicting whether a customer is likely to leave the bank based on historical data.

## Goal
The primary goal of this project is to develop a predictive model that can identify potential churn customers. The evaluation metric for this task is the F1 score, with a target of achieving an F1 score of at least 0.59. The secondary metric used for evaluation is the ROC-AUC score.

## Methods
To improve the prediction quality of the random forest model, I employed several techniques to handle the class imbalance issue. The following methods were used:

1. Upsampling: The minority class (churned customers) was randomly replicated to achieve a balanced distribution.
2. Oversampling: Synthetic instances were generated using the SMOTE algorithm to increase the number of minority class instances.
3. Downsampling: The majority class (non-churned customers) was randomly reduced in size to balance the class distribution.
4. Undersampling: Random instances from the majority class were removed to achieve a balanced dataset.
5. Class Weight - 'balanced': The class_weight parameter of the random forest model was set to 'balanced' to automatically adjust class weights during training.

## Results
After evaluating the performance of the different methods, the following results were obtained:

- **Upsampling**: F1 score - 0.5830, ROC-AUC score - 0.8353
- **Oversampling**: F1 score - 0.5585, ROC-AUC score - 0.8333
- **Downsampling**: F1 score - 0.5607, ROC-AUC score - 0.8341
- **Undersampling**: F1 score - 0.5616, ROC-AUC score - 0.8316
- **Class Weight - 'balanced'**: F1 score - 0.5605, ROC-AUC score - 0.8323

## Final Model Results
Further analysis was conducted on the "Up Sampled" method, and the final model achieved an F1 score of 0.6093 and an ROC-AUC score of 0.8622 during training.


## Final Conclusion
Based on the final model results, the "Up Sampled" method performed the best for churn prediction, achieving the highest F1 score of 0.6093 during training. The model's performance on the validation set showcased an F1 score of 0.6059 and a ROC-AUC score of 0.8455, which met the company's performance standard. The model demonstrated a balanced trade-off between precision and recall, indicating its ability to accurately identify a substantial portion of potential churn customers. This outcome is significant for the company's churn prediction efforts, highlighting the effectiveness of the "Up Sampled" technique in capturing and addressing class imbalance to improve churn prediction accuracy.

## Final Notes for Further Improvement
To further enhance the prediction quality of the model, two effective methods can be utilized: SMOTE (Synthetic Minority Over-sampling Technique) and Cluster Centroids.

SMOTE generates synthetic samples by interpolating feature vectors of minority class instances, thus increasing the diversity of the dataset. This technique helps to address class imbalance and can improve the model's ability to capture important patterns within the minority class.

Cluster Centroids, on the other hand, identifies clusters within the majority class and generates synthetic samples by replacing each cluster centroid with a randomly selected instance from the cluster. This approach helps in reducing the majority class instances and achieving a more balanced dataset.

By incorporating these techniques into the model training process, it is possible to further improve the model's ability to handle class imbalance and enhance its prediction quality.

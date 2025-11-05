# Open-Ended-Lab 22F-BSAI-96

# Diabetes Prediction Model Analysis

## Data Analysis Key Findings

* The dataset initially contained 0 values in 'Glucose', 'BloodPressure', 'SkinThickness', 'Insulin', and 'BMI' columns, which were treated as missing and imputed with the mean.
* Numeric features were normalized using MinMaxScaler.
* The data was split into training (614 samples) and testing (154 samples) sets, with an 80/20 ratio.

## Model Performance Metrics

### SVM Test Set Metrics

* Accuracy: 0.7597
* Precision: 0.6957
* Recall: 0.5818
* F1-score: 0.6337

### Decision Tree Test Set Metrics

* Accuracy: 0.7208
* Precision: 0.6071
* Recall: 0.6182
* F1-score: 0.6126

## Overfitting Discussion

Overfitting occurs when a model learns the training data too well, including noise and outliers, leading to poor performance on unseen data. Potential overfitting can be inferred by comparing training and testing performance. A significant drop in metrics from training to testing indicates overfitting.

### Potential Overfitting Analysis

* The Decision Tree shows slightly lower accuracy and F1-score than the SVM.
* Higher recall but lower precision in the Decision Tree may suggest it is prone to classifying instances as positive, possibly capturing noise from training data.
* If the Decision Tree's training accuracy was significantly higher than 0.7208, it would indicate strong overfitting.
* The SVM demonstrates more balanced performance across precision and recall, suggesting better generalization.

## Accuracy and Metric Trade-offs

* Accuracy measures overall correctness, but for imbalanced datasets or scenarios with unequal costs of false positives and negatives, precision and recall are crucial.
* In diabetes prediction, false negatives (missing an actual diabetes case) are more critical than false positives.
* Recall minimizes false negatives, while precision minimizes false positives.

### Model-specific Trade-offs

* **SVM:** Higher precision (0.6957) and F1-score (0.6337) suggest it is better at avoiding false positives while maintaining reasonable recall (0.5818). Trade-off is slightly lower recall.
* **Decision Tree:** Higher recall (0.6182) identifies more actual diabetes cases, but lower precision (0.6071) leads to more false positives.

## Summary and Insights

* SVM shows slightly better overall accuracy, precision, and F1-score.
* Decision Tree has higher recall but at the cost of lower precision, indicating more false positives.
* Conclusive overfitting assessment requires comparison of training and testing metrics.
* Further tuning or regularization for the Decision Tree could reduce overfitting while retaining its ability to identify positive cases, which is crucial in medical diagnosis.
* Model choice should consider the clinical importance of minimizing false negatives versus false positives.


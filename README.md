# Supervised Learning Approach for Age Prediction

## Introduction
Supervised learning involves building predictive models by training on a large set of labeled examples, where the labels represent the ground truth outputs. This training process enables the model to generalize and make accurate predictions on new, unseen data. For our analysis, we used an 80/20 train-test split to balance model training and evaluation on unseen data.

## Methodology

### Lasso Regression
Lasso Regression is a linear technique with L1 regularization, which drives some coefficients to zero, enhancing model simplicity and interpretability (Ranstam et al., 2019). It is well-suited for our dataset, as it handles high dimensionality and potential multicollinearity among features related to age prediction.

### Evaluation Metrics
To assess the performance of our model, we utilized three key evaluation metrics:

1. **R-squared (R²)**: The proportion of variance in age explained by the model. A high R² value suggests that the model captures most of the relevant information in the data.
2. **Root Mean Squared Error (RMSE)**: Quantifies the standard deviation of the residuals (prediction errors). A lower RMSE indicates better predictive accuracy.
3. **Mean Absolute Error (MAE)**: Provides the average absolute difference between predicted and actual values.

## Results

### Performance of Models
The performance of five supervised learning methods is summarized in Table 4.1. Lasso Regression achieved the highest performance across all evaluated metrics, outperforming Ridge and Linear Regression. Its accuracy was also considerably superior to that of the Decision Tree and Random Forest models.

Table 4.1 Performance of Five Supervised Methods
| Model              | R² Score | RMSE   | MAE    |
|--------------------|----------|--------|--------|
| **Lasso Regression** | 0.8988   | 5.0654 | 6.4407 |
| Linear Regression  | 0.8981   | 5.0654 | 6.4618 |
| Ridge Regression   | 0.8981   | 5.0832 | 6.4609 |
| Decision Tree      | 0.8604   | 5.0825 | 7.5628 |
| Random Forest      | 0.8902   | 5.2919 | 6.7094 |

### Feature Selection
The coefficients of the Lasso Regression method show that many features have coefficients of zero, indicating that they are not significant predictors of age in this dataset. This highlights a key advantage of Lasso Regression, as it simplifies the model by eliminating less relevant predictors.

### Key Predictors
- **Positive Correlations**:
  - Higher Systolic BP, Diastolic BP, Cholesterol, and Blood Glucose levels are associated with an older predicted age.
- **Negative Correlations**:
  - Lower bone density correlates with older age.
  - Better cognitive function and never having smoked are linked to a younger predicted age.

## References
- Dataset source: Human Age Prediction Synthetic Dataset (kaggle.com)
- Ranstam, J., & Cook, J., 2018. LASSO regression. British Journal of Surgery, 
105. https://doi.org/10.1002/bjs.10895.

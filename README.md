# California Housing: An Experimental Study of Regression Models

## Research Question

How do feature selection, feature scaling, and model complexity
affect the generalization performance of regression models for
California housing price prediction?

## Objectives

- Investigate relationships between housing features and house value.
- Establish a Linear Regression baseline.
- Study the effect of feature scaling on Gradient Descent.
- Investigate the effect of feature selection.
- Analyze the effect of increasing model complexity.
- Study whether regularization improves generalization.

## Research Hypotheses

Based on the findings from exploratory data analysis, the following
hypotheses will be investigated during the experimental stage.

### H1: Effect of Training Data Size

Increasing the amount of training data will improve out-of-sample
performance, although the improvement is expected to diminish as the
amount of available training data increases.

### H2: Effect of Feature Information

Increasing the number of informative features will improve predictive
performance, while adding weakly informative or redundant features may
provide diminishing returns.

### H3: Feature Selection and Redundancy

Removing highly redundant predictors may reduce model complexity while
preserving or improving out-of-sample predictive performance.

### H4: Geographic Information

Adding `latitude` and `longitude` may improve out-of-sample prediction
because the EDA revealed spatial patterns in housing prices that are not
captured by their individual Pearson correlations with the target.

### H5: Feature Scaling and Optimization

Feature scaling will improve the convergence behavior of Gradient
Descent when predictor variables have substantially different scales.

### H6: Model Complexity and Generalization

Increasing model complexity will initially improve predictive performance,
but excessive complexity may lead to overfitting and poorer performance
on unseen data.

### H7: Regularization

Regularization will reduce the influence of model complexity and may
improve generalization, particularly when correlated or redundant
predictors are present.

### H8: Sensitivity to Extreme Observations

Extreme observations may have a measurable influence on regression model
parameters and predictive performance.

## Experimental Roadmap

The experiments are designed to investigate how different aspects of the
data, preprocessing, and model design affect regression performance and
generalization.

| Hypothesis / Question | Experiment | Main Evaluation |
|---|---|---|
| **H1: Training Data Size** | Evaluate model performance using different proportions of the training data | Validation RMSE, MAE, R² |
| **H2: Number of Features** | Evaluate how predictive performance changes as the number of input features increases | Validation RMSE, MAE, R² |
| **H3: Feature Selection** | Compare the full feature set with reduced/selected feature sets | Validation RMSE, MAE, R² |
| **H4: Geographic Information** | Compare models with and without `latitude` and `longitude` | Validation RMSE, MAE, R² |
| **H5: Feature Scaling** | Compare Gradient Descent with and without feature scaling | Convergence speed, loss, validation performance |
| **H6: Model Complexity** | Compare models with increasing levels of complexity | Training vs validation performance |
| **H7: Regularization** | Compare unregularized and regularized regression models using different regularization strengths | Validation RMSE, MAE, R² |
| **H8: Outlier Sensitivity** | Compare model performance with different approaches to handling extreme observations | Validation RMSE, MAE, R² |

## Evaluation and Experimental Strategy

The project will evaluate models primarily based on their ability to
generalize to previously unseen data.

The dataset will be divided into a development set and a held-out test
set. The development set will be used for model training, validation,
feature selection, and experimental comparisons, while the test set will
be reserved for final evaluation.

The experiments will investigate how different factors affect model
performance, including:

- Training dataset size
- Number and selection of input features
- Feature scaling
- Geographic features
- Model complexity
- Regularization
- Potential sensitivity to extreme observations

Model performance will be evaluated using:

- **RMSE:** Measures the typical prediction error while giving greater
  weight to larger errors.
- **MAE:** Measures the average absolute prediction error and is easier
  to interpret in the original target units.
- **R²:** Measures the proportion of variance in the target explained by
  the model.

Training and validation performance will also be compared where
appropriate to investigate overfitting and underfitting.

For experiments involving multiple model or preprocessing choices,
cross-validation on the development set will be used where appropriate.
The held-out test set will be used only for final evaluation.
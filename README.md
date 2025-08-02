# Machine-Learning

# Model Evaluation and Variable Selection Techniques in Economic Data Analysis

This repository presents a comprehensive application of model selection and evaluation techniques using micro-level economic data. The analysis is situated in the field of **health economics** and leverages data from the **National Sample Survey Office (NSSO) 75th Round** on *Social Consumption: Health*. The primary aim is to assess the predictive and explanatory performance of alternative regression models to estimate inpatient medical expenditure (`In_TotMedicalExp`) using individual- and household-level characteristics.

## Objectives

- Estimate and compare multiple linear regression models
- Evaluate models using AIC, BIC, R², Adjusted R², and Mallow’s Cp
- Apply single-split and K-fold cross-validation to assess prediction error
- Implement variable selection techniques such as best subsets and stepwise regression
- Demonstrate shrinkage methods (Ridge and Lasso) as regularized alternatives

## Data

The empirical analysis is based on data from the **NSSO 75th Round** (2017-18), specifically the schedule on *Social Consumption: Health*. The primary outcome of interest is:

- `In_TotMedicalExp`: Total inpatient medical expenditure

Selected explanatory variables include:

- `Age`: Age of the respondent
- `Household_Size`: Number of household members
- `MPCE_Euro`: Monthly per capita consumption expenditure (converted to Euro)

## Key Components

### 1. Model Comparison Using Information Criteria

Eight nested regression models are constructed using all possible combinations of the three predictors. For each model, the following metrics are computed:

- **Akaike Information Criterion (AIC)**
- **Bayesian Information Criterion (BIC)**
- **R-squared and Adjusted R-squared**
- **Mallow’s Cp**

These metrics assist in evaluating trade-offs between model complexity and goodness of fit.

### 2. Cross-Validation

- **Single-split cross-validation** is performed using an 80% training and 20% testing partition.
- **5-fold cross-validation** is implemented to mitigate the variability due to random splits and to assess the stability of MSE estimates.

Mean Squared Error (MSE) is computed for each fold, and the average and standard deviation of the MSE across folds are reported for all models.

### 3. Best Subset and Stepwise Selection

- **Best Subset Selection** evaluates all possible predictor combinations and selects the model that minimizes test MSE.
- **Stepwise Regression** (forward selection) iteratively adds variables that most improve model fit until no further improvement is observed.

These methods facilitate model parsimony without compromising predictive accuracy.

## Implementation Details

All analysis is conducted in **Python**, using the following libraries:

- `pandas`, `numpy`: Data handling and manipulation
- `statsmodels`, `sklearn`: Regression modeling and evaluation
- `matplotlib`, `seaborn`: Visualization

## Academic Context

This repository is designed for applied econometric analysis in the domain of **public health and risk protection**, focusing on the **economic burden of healthcare expenditures**. The methodologies are tailored to national survey data and emphasize model interpretability and policy relevance.

## Repository Structure


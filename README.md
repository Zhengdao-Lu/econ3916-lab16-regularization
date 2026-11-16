# econ3916-lab16-regularization
## Regularization: Buying Bias to Sell Variance
# Objective
I compared OLS, LASSO, and Ridge to see how regularization affects prediction and variable selection when most predictors are noise.
# Methodology
- I simulated 200 predictors, with 5 real predictors and 105 training rows, then fitted all three models.
- I traced the LASSO coefficient path and chose a penalty using 5-fold cross-validation, fitting the scaler inside each fold.
- I compared LASSO’s selected variables with the known truth and tested LASSO and Ridge on two near-duplicate predictors.
- I wrote prompts for an AI-generated cross-validation loop and checked its results over 2 rounds.
# Key findings
OLS had a test MSE of 12.9587, Ridge 10.1128, and LASSO 1.4219. On the LASSO path, all 5 real predictors had entered by step 6; the first noise variable entered at step 17. Cross-validation chose a penalty of 0.1995 with a CV MSE of 1.5502.

LASSO found all 5 real predictors and selected 11 false positives. With the near-duplicate predictors, it put 4.462 on one and 0.000 on the other. Ridge split the weight between them, at 1.618 and 1.609. In both AI rounds, the chosen penalty and CV MSE matched the lab’s checks.

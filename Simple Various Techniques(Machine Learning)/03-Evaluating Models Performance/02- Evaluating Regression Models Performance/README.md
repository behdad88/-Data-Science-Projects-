## Evaluating Regression Models Performance
The various metrics used to evaluate the results of the prediction are :
- Mean Squared Error(MSE)
- Root-Mean-Squared-Error(RMSE).
- Mean-Absolute-Error(MAE).
- R² or Coefficient of Determination.
- Adjusted R²

**Mean Squared Error**: MSE or Mean Squared Error is one of the most preferred metrics for regression tasks. It is simply the average of the squared difference between the target value and the value predicted by the regression model. As it squares the differences, it penalizes even a small error which leads to over-estimation of how bad the model is. It is preferred more than other metrics because it is differentiable and hence can be optimized better.

**Root Mean Squared Error**: RMSE is the most widely used metric for regression tasks and is the square root of the averaged squared difference between the target value and the value predicted by the model. It is preferred more in some cases because the errors are first squared before averaging which poses a high penalty on large errors. This implies that RMSE is useful when large errors are undesired.

**Mean Absolute Error**: MAE is the absolute difference between the target value and the value predicted by the model. The MAE is more robust to outliers and does not penalize the errors as extremely as mse. MAE is a linear score which means all the individual differences are weighted equally. It is not suitable for applications where you want to pay more attention to the outliers.

**R² Error**: Coefficient of Determination or R² is another metric used for evaluating the performance of a regression model. The metric helps us to compare our current model with a constant baseline and tells us how much our model is better. The constant baseline is chosen by taking the mean of the data and drawing a line at the mean. R² is a scale-free score that implies it doesn't matter whether the values are too large or too small, the R² will always be less than or equal to 1.

<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2019/05/Screenshot-2019-05-16-at-7.06.18-PM-300x88.png">

<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2019/05/Screenshot-2019-05-16-at-7.08.20-PM-768x307.png">

MSE(model): Mean Squared Error of the predictions against the actual values

MSE(baseline): Mean Squared Error of  mean prediction against the actual values

**A good question is can R-squared ever be negative?**
The answer is yes of course R-squared can be negative and that is if your for instance MSE of your model actually fits your data worse then your average life.


**Adjusted R²**: Adjusted R² depicts the same meaning as R² but is an improvement of it. R² suffers from the problem that the scores improve on increasing terms even though the model is not improving which may misguide the researcher. Adjusted R² is always lower than R² as it adjusts for the increasing predictors and only shows improvement if there is a real improvement.

<img src="https://cdn.analyticsvidhya.com/wp-content/uploads/2019/05/Screenshot-2019-05-16-at-7.14.36-PM-300x95.png">

k: number of features

n: number of samples

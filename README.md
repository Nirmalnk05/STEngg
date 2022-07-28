# STEngg assessment 

## 1. RUL Prediction 

In order to define the target variable, calculated remaining cycle using unit and time features of given dataset.

In terms of parmaetric assumptions, checked the distribution target variable "Remaining cycle" . It seems in gaussian distribution.

In terms of data quality, there is no missing data and all features are in proper datatype formats.

Regarding feature selection, we checked the correlation on independent variiables and checked multi collinearity.
Due to high VIF, we considered dimensionality reduction technique - PCA method as one of the approach for the model. 
For this case, we stantdadised the data using MinMaxScaler approach.

So, if you see we developed model based on two type of features.
  
    1. Raw sensor data (removed highly correlated features)
    2. PCA features (with 2 components)
    
    
![image](https://user-images.githubusercontent.com/71075637/181470081-f7d3ec23-4652-4d94-ac6a-04f98320b85c.png)

    
In terms of Model development, we tried with different models such as Linear Regression, Lasso, Ridge, Random Forest and XGBoost regression.
Out of which, RF regressor performs very well (verified with cross validation) since it has high R-Squared and low RMSE compared to other models.


In terms of feature engineering, we could have tried moving average, fft, and other statistical/temporal/spectral features extraction.
 But, with current approach we're able to obtain the desirable results.

Additionaly, performed cross validation and hyper parameter tuning, to verify the model results are more robust and consistent.

In terms of EDA, performed various plots such as all the sensors of single unit and tried to understand the patterns.
Then, analysed one specific sensor (in our case PhysCore Speed)  of all units how the variation happens in each unit.
Later, performed the boxplot to see the overall distribution of data points of considering all sensors and for all units.

Here, we can see the plot shows the prediction results of RUL for Unit 1

![image](https://user-images.githubusercontent.com/71075637/181468921-7b62f51a-7b41-4c2c-a47e-874f3578efe9.png)


Performed feature importance to understand important features for the model predicitons.
Feature Importance

![image](https://user-images.githubusercontent.com/71075637/181469288-f83df2bf-ea15-43b3-bca7-6b034c05da01.png)


## 2. Anomaly Detection

In terms of anomaly detection, we tried with different approaches such based upon distance, clustering, SVM, nural networks such as IQR, Once class SVM, K-Means, Isolation Forest and auto encoders.

Here, to make the predictions more robust, we didn't simply rely on one model results. Instead, we took a majority voting of all models prediction.
This could results us a better relaible predictions.

![image](https://user-images.githubusercontent.com/71075637/181469948-2cfe65bf-aa54-4543-a53c-26d7c6186cf7.png)



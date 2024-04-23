# SC1015_FDDB_Team4
# Mobile Price Mini-Project
### Austin Teo Yuan Xuan, Cai Xubin, Tan Wei Jin Ranen
#Overview:
Our group aims to predict mobile phone prices based on the phone’s specifications.

# Table of Contents:
- Introduction
- Problem Statement
- Data Description
- Data Preprocessing
- Model Used
- Evaluation Metrics
- Conclusion
- Contribution

# Introduction:
Consumers are faced with a plethora of options when it comes to selecting their next device. With each new release, manufacturers tout a myriad of features and specifications, promising improved performance, enhanced camera capabilities, and innovative designs.Spoiled for choices, consumers may not be able to identify the phone that has the best value for money, based on the specifications of the hardware. Additionally, social media influences, opinions of others, and personal favouritism of a brand may not lead to consumers choosing the most optimal phone

#Problem Statement:
How do we estimate the Price of a mobile phone, based solely on its specifications?

# Data Description:
### Our Data is from: https://www.kaggle.com/datasets/pratikgarai/mobile-phone-specifications-and-prices
- Unnamed:0: Sequential Id of the phone
- Name: Name of the phone
- Brand: Brand name of the phone
- Model: Model of the phone
- Battery Capacity (mAh): Battery Capacity of the phone in milliampere-hour
- Screensize (inches): Screen size in inches across opposite corners
- Touchscreen: Whether the phone is touchscreen supported or not
- Resolution x: The resolution of the phone along the width of the screen
- Resolution y: The resolution of the phone along the height of the screen
- Processor: Number of processor cores
- RAM (MB): RAM available in phone in MB
- Internal Storage (GB): Internal Storage of phone in GB
- Rear Camera: Resolution of rear camera in MP (0 if unavailable)
- Front Camera: Resolution of front camera in MP (0 if unavailable)
- Operating system: OS used in the phone
- Wi-Fi: Whether the phone has WiFi functionality
- Bluetooth: Whether the phone has Bluetooth functionality
- GPS: Whether the phone has GPS functionality
- Number of SIMs: Number of SIM card slots in the phone
- 3G: Whether the phone has 3G network functionality
- 4G/LTE: Whether the phone has 4G/LTE network functionality
- Price: Price of the phone in INR

# Data Preprocessing:
We renamed the columns of the data, then checked that there were no duplicates, and removed the following columns: "gps", "wifi", "bluetooth", "touchscreen", "name", "brand", "model". We converted dual sim to a categorical variable.
We split the data into numerical predictor, categorical predictor, and response variable. We converted price into SGD.
We investigated the correlation coefficients of the numerical predictors and response variables. We removed columns: "resolution_x", "battery_capacity", "processor" and "front_camera",  which had little correlation with price(coefficient lower than 0.3). We also dropped resolution_x which is highly correlated with resolution_y to prevent multicollinearity. 
For categorical variables, we looked at the distribution of price in the different categories and removed  “3g” which had a similar distribution of price for phones with or without 3G. We converted the remaining categorical predictor into dummies and dropped one column from each predictor to prevent multicollinearity.

# Model Used:
Linear Regression
Linear Regression with log transformation of the response
Decision Tree Regressor
Decision tree
Random Forest
There were 2 type of Model, Regression Model and Classification Model GridSearchCV is used to find the best Hyper-Parameter

# Evaluation Metrics:
For the regression model, we looked at MSE and Explained Variance. For the Classification Model, we look at accuracy.

#Conclusion:
Regression models provide numerical predictions while Classification Models provide categorical predictions. For users looking for a rough range, the Random forest model can be used as it has higher accuracy than the decision tree model. For users looking for a numerical prediction, the linear regression model with log transformation can be used as it has highest explained variance

# Contributions:

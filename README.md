# Avi

In our project, we want to predict the danger class levels of avalanches in the canton of Grisons. Avalanches cause 22 fatalities on average each year in Switzerland, therefore we want to provide the resorts a model with which they can predict the danger class levels, thereby facilitating the protection of its visitors and reducing the number of lives lost each year.

The dataset we found on EnviDat.ch (Weather, Snowpack and Danger Ratings Data for Automated Avalanche Danger Level Predictions, n.d.) had over 290’000 rows. After deleting NaNs and subsetting the data to only look at stations in Grisons, we had the final data set that we proceeded to work with. Firstly, we ran a principal component analysis on it, which retained the information but reduced the dimensionality to two, thereby making it possible to plot our data and get first impressions on it. After dividing the danger class levels into two, one for high danger and one for low danger, we ran a logistic regression on it.

In order to predict the individual danger levels, we used three models, a neural network, decision tree, and random forest. The neural network gave us an accuracy of 74% on the test data. We wanted to further improve our accuracy by using decision trees and random forests. In a first step we created a decision tree and later optimized the max depth and the minimum samples leaf to improve our results. Subsequently, we used random forests to further improve our accuracy. Since we got lower recall values for the higher danger levels, we oversampled the higher danger levels and were able to improve their recall value while achieving an accuracy of 76%. 
Lastly, we performed time series analysis by using Auto-Arima, PyAF and NeuralProphet as forecasting models. Auto-Arima and Pyaf resulted in the prediction being the mean value while NeualProphet showed that there was a tendency for higher danger levels during the peak ski season of December, January and February.

Original data set source: https://www.envidat.ch/dataset/weather-snowpack-danger_ratings-data

df_p1 – df_p8 : 2/3 of original data after removing NaNs

df_t1datum and df_t2datum: Grisons subset including the column "datum"

df_t1new and df_t2new: Grisons subset excluding the column "datum"



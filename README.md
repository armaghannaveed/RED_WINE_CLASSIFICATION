# RED_WINE_CLASSIFICATION
DSCI-100, Section 002

Group Project Report

Authors: Armaghan Naveed, Isabelle Partovi, Shijia Su, and Tanya Thandi


Red Wine Classification Report
By DSCI 100, Group 39
Introduction
The Wine Quality Dataset contains information about White Wine and Red Wine variants of Vinho Verde, Portugal. Portugal is a top ten wine exporting country which holds 3% of the market share (FAOSTAT, 2019). The Portuguese wine market is dominated by still wines, specifically red wine. (Romo-Muñoz, Monje-Sanhueza, Garrido-Henríquez, & Gil, 2020) Therefore, for our project we will be looking at the quality of red wine and the factors that create balance.

A higher-quality wine has all of its components balanced, whereas a lower-quality wine has an element that stand out more than the rest. The question we are trying to answer is **“Can we use the physicochemical properties of red wine to objectively predict whether the quality of a future unknown wine will be poor, satisfactory, or excellent?”** We will be using a dataset collected from 1599 samples of the red variant of Vinho Verde. The dataset contains 12 elements: fixed quality, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, pH, sulfates, alcohol, and quality. Our output variable is “quality” which the classification model would try to accurately predict. The quality score is measured on a scale from 1 (bad) to 10 (good).

As seen, there is no data regarding the wine brand, grape types, fertilizers/insectides used, or retail price due to policy and logistical issues. The original number of observations in each class are imbalanced, with more satisfactory wines than excellent or poor wines. The original research used a regression model to preserve the order of the wine scores and derive distinct accuracy results.

Our goal is to create an efficient classification model capable of generating accurate predictions for the red wine grown in Vinho Verde. Our classification model could then be used to improve production efficiency and certification criterias. (Rodrigues et al., 2011)


accuracy	multiclass	0.8345865
kap	multiclass	0.3700904
              Truth
Prediction     Excellent Poor Satisfactory
  Excellent           24    2           21
  Poor                 0    2            2
  Satisfactory        29   12          307
Methods and Results
We will conduct our data analysis using all variables because they all matter for red wine quality, and we want to know how to balance the variables for excellent quality. We will have quality as the prediction result. All factors, except quality, are collected using physicochemical tests. We will be creating a model that allows us to classify the wine's quality in three categories, given its other eleven properties. The three types are:

Excellent: score of 7 and 8
Satisfactory: score of 5 and 6
Poor: score of 3 and 4
To conduct the analysis, we will first split our data into training and testing data to avoid violating the golden rule. Next, we split the training data into validation sets for 10-fold cross-validation. By looking at multiple validation sets, we can find their average for our cross-validation accuracy. We tuned the K-nearest neighbors of our classification model to maximize our cross-validation accuracy estimates. We predicted the result of our model on the testing data and compared it to our true quality to see our model's accuracy. The data is visualized using a line graph that shows estimate accuracy vs. the K nearest neighbors to see how K affects our prediction accuracy.

Discussion
Using the cross-validation method, we found that the k-value of 6 computed a classifier with the highest accuracy, although accuracies of k-values were not significantly differnt than k = 1 as shown in the graph. We also found that our classifier was 83.5% accurate on the test data compared to 83.3% on the training data. The model accurately predicted 2 poor quality wines, 24 excellent quality wines, and 307 statisfactory quality wines, while also inaccurately predicting 2 poor quality wines, 23 excellent quality wines, and 43 satisfactory quality wines.

We expected our model to have a bit higher accuracy than 83.5% as we used 11 chemcial properties as predictors in our classifer. We scaled and centered all predictors so that each variable had an equal effect on the classifier by making each predictor's mean equal to 0 and standard deviation equal to 1. We also tuned our classifier by performing cross-validation to choose a k-value that would help us maximize accuracy along with other measures taken.

Our model helped classify quality of red wine depending on 11 factors: fixed quality, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, pH, sulfates and alcohol. a wine label can use the model we have created to see which qualities and their quantities lead to a wine of a good quality and use that information to change their wine production. The wine labels can modify their product by changing its chemical properties accordingly to increase their sales as well as receive positive feedback from wine critics and customers which could help the label establish itself as a reputable brand. This model also brings a more analytical testing for wine in order to pass the certification phase by Portuguese law rather than relying on human wine testers.

Some of the questions we can ask is if this model is accomodating towards different wine labels since we don't know the wine labels of the samples and we don't know if this sample was a good representative of all red wine from different brands. We can also We can also ask if there are any other factors that can help us increase the accuracy of our tester such that eventually, there will be no need of human testers as we can rely complete on this analytical test for the quality of the wine dependent on its chemical properties as sometimes wine critics can be biased and simply rank a wine on the higher quality spectrum simply because of its label. We can also ask ourselves whether we can use similar models to assess other foods and drinks as well.

References
Food and Agriculture Organization of the United Nations (FAOSTAT). (2019, October 9). Food and Agriculture Organization Agriculture Trade Domain Statistics. Retrieved from http://faostat.fao.org/site/535/DesktopDefault.aspx?PageID=535

Rodrigo Alejandro Romo-Muñoz, Rodrigo Monje-Sanhueza, Héctor Garrido-Henríquez, José M Gil. (2020) Key market values for bottled wine in an emerging market: product attributes or business strategy?. Applied Economics 52:34, pages 3669-3679.

Rodrigues, S., Otero, M., Alves, A., Coimbra, J., Coimbra, M., Pereira, E., & Duarte, A. (2011, January 18). Elemental analysis for categorization of wines and authentication of their certified brand of origin. Retrieved April 09, 2021, from https://www.sciencedirect.com/science/article/pii/S0889157511000184?casa_token=QhrKN4X-rToAAAAA%3Ann9L8HocNfoGCjcMHTcvbScsF4ZZ2VsT-xTyDHfv5fa--TZ7UMjhgxsANsfKHAwSApCvuTLe0g

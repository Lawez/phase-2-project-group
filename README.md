# Phase 2 Project Description

![house%20price](https://github.com/Lawez/phase-2-project-group/blob/main/images/house%20price.jpg)


## Project Overview

Mzalendo ltd is a housing stakeholder that gives advice to homeowners so that they can buy or sell homes.
The company wants to help homeowners to be able to predict the current and future prices of their houses depending on different features.

### Business Problem

The business problem for this project is to provide guidance to homeowners to determine house prices based on the house descriptions.

### Data 

The project uses this he King County House Sales dataset, which can be found in kc_house_data.csv in the data folder in this assignment's GitHub repository. 

The following approaches were used;
* Univariate analysis where we explored certain columns in the dataset to display their counts as well as plot visualizations accordingly so as to get a better understanding of the values present in the columns
* Correlation heatmap was plotted and the correlation results analyzed
* A new data set was created to look into the effect of house renovation 
* Price and location of houses were plotted in tableau
* OUtliers were checked and ploted by boxplot
* Linearity assumption was cheaked between various variables
* Bivariate Analysis was performed where there seems to have a linear relation between squarefoot living, price and bedrooms seems to be a descrete variable having an average of between 4 and 5

### visualization

visualizations between different features were then plotted to understand how different features affect one another

![distribution%20of%20sqrt](https://github.com/Lawez/phase-2-project-group/blob/main/images/distribution%20of%20sqrt.png)

*This histogram shows the distribution of sqft_living which is normally distributed, with a mean around 12.5 and a standard deviation around 0.5*

![price](https://github.com/Lawez/phase-2-project-group/blob/main/images/price.png)

*This histogram shows the distribution of house prices in the King County House Sales dataset, the majority of house prices in the dataset fall in the range of $0 to $1 million, with a peak around $500,000.There are a small number of houses with very high prices (above $3 million), which are likely to be outliers or luxury properties.The distribution of house prices is right-skewed, which means that there are more houses with lower prices than with higher prices.*

![price%20vs%20sqft](https://github.com/Lawez/phase-2-project-group/blob/main/images/price%20vs%20sqft_liv.png)

 *Scatter plot of the living area (in square feet) versus the price of the houses in the King County House Sales dataset. Each point in the scatter plot represents a different house in the dataset,there is a positive linear relationship between the living area and the price of the houses. This suggests that larger houses tend to sell for higher prices. However, there is also a lot of variability in the data, with some houses having a high price despite a relatively small living area, and vice versa. This suggests that there are other factors beyond just the living area that are influencing the price of the houses.*


![price%20vs%20bedrooms](https://github.com/Lawez/phase-2-project-group/blob/main/images/price%20vs%20bedrooms.png)

*A scatter plot of the number of bedrooms versus the price of the houses in the King County House Sales dataset. It appears that there is a positive linear relationship between the number of bedrooms and the price of the houses, although the relationship is not as strong as the relationship between living area and house prices. The regression line has a positive slope, which means that as the number of bedrooms increases, the price of the house tends to increase as well, although there is still quite a bit of variability in the data.*




### Methods

After exploring and preprocessing the data; 

* *Simple linear regression model were built in OLS statsmodels, with price as the dependent variable.*
* *Multiple linear regression models were built in OLS statsmodels, with price as the dependent variable.*
* *Log transformed model of the multiple linear regression model*
* *Multiple one hot coded model of grade column*

### Results

* Simple linear regression model is statistically significant and explains about 47% of the variance in price.The  model is off by about $160,438.91.The intercept is at about 34k.the coefficient for square foot living is about 239 more.The model explains 47% of the variance in price but we can improve the model to 50% by doing a multi regression model

* Mutiple regression model is statistically significant and explains about 53% of the variance in price.The model is off by about $149,576.71 and intercept is at about $5,114,000.The coefficient for square foot living is about 73110, one rating of average condition is 16690, very good condition $51530 and the model explains 53% of the variance in price but we can improve the model to 60% by doing log transformation on the multi regrssion model

* Log model is statistically significant the model explains about 50% of the variance in price. However the model has a lower adjusted r squared value compared to the previous model to improve the model, we one hot code the grade of the house column to get to the model to 60%

* Multiple one hot coded model of grade column Overall this model is statistically significant and explains about 63% of the variance in price.The model is off by about $130,794.15.The intercept is at about $6,956,000 and the coefficient for square foot living is about 
58970, grade of low grade is 
18260, low average 
147700, good 
430000 , very good 
789100, luxury 1519000.The model explains 63% of the variance in price which has attained our target of a model explaining 60% of variance.


# Conclusion

We have performed extensive analysis on the housing dataset, exploring its features, identifying patterns and trends, and building multiple linear regression models to predict housing prices. We found that the most significant predictors of housing prices were the square footage of living space, the number of bedrooms, and the number of bathrooms. Additionally, we found that using a log transformation of the target variable improved the performance of our model.

The multiple regression model is better than the simple regression model since it has a higher Rsquared value than the simple linear regression model.
From this we gathered the categorical variables have a positive effect on the preices predictor variable.
The agency should consider the sqft_living variable when selling since it has a high linear relationship to the prices predictor

# Recomendations

* Based on our findings, we recommend that prospective homebuyers focus on properties with larger living spaces and more bedrooms and bathrooms, as these tend to have higher values. Additionally, we recommend that real estate agents use our model to help set appropriate listing prices for homes, taking into account the features of the property.

# Limitations

* Limited variables: The dataset used in this analysis only included a limited number of variables. There could be other variables that could also impact housing prices that were not included in the dataset.

* Data quality: The dataset used in this analysis is assumed to be accurate, complete, and representative of the population. However, there may be errors or biases in the data that were not detected.

* Model assumptions: The regression models used in this analysis make certain assumptions, such as linearity, independence, and normality. Violations of these assumptions could impact the accuracy and reliability of the results.

* Limited geographic scope: The dataset used in this analysis only covers housing prices in King County, Washington. The results may not be generalizable to other locations.

* Timeframe: The dataset used in this analysis only covers housing prices from May 2014 to May 2015. Housing prices may have changed since that time, and the results may not be applicable to the current housing market.

# Next steps

* Feature engineering: try creating new variables based on domain knowledge or statistical analysis to see if they improve the model performance.

* Collect more data: gather additional data on housing characteristics or socioeconomic factors that could be included in the model to improve its accuracy.

* Deploy the model: if the model proves to be accurate and useful, it could be deployed in a web application or integrated into a larger data pipeline to provide real-time predictions for potential home buyers or sellers.

**Repository Structure:**
```
├── data                                                   <- Data folder location of our study
├── images                                                 <- images folder of our notebook 
├── presentation.pdf                                       <- PDF version of project presentation 
├── .canvas                                                <- canvas extention 
├── .gitignore                                             <- gitignore 
├── CONTRIBUTING                                           <- Conribution logs
├── LISENCE.md                                               <- LICENCE of the project
├── README.md                                              <- The top-level README for reviewers of this project                  
└── student.ipynb                                          <- Narrative documentation of analysis in Jupyter notebook
```

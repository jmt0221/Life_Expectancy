# Life_Expectancy
Life Expectancy Predictions by Country

Justin Tennenbaum, Paul Kruger 


# Project Goals

To determine which factors are most influential on average life expectancy in years and to build a multiple linear regression model to predict average life expectancy in specific countries.

# Data Collection

We used a robust dataset from the World Health Organization that included statistics on health and socio-economic factors for all the nations of the world.

# Data Cleaning

We chose to drop the following variables due to multi-collinearity:  Adult Mortality, Infant Deaths, Thinness (age 5-9), Diptheria, Polio.  We chose to drop the following variables due to missing values or bad data:  Hepatitis B, BMI, Country Developing Status.  We also dropped twenty countries due to excessive missing values.  We performed backwards elimination where we ran the model each time and dropped the following variables due to high P-values:  Total Expenditure on Health, Deaths under 5 years old, and Measles. We were left with 

# Feature Engineering

In order to avoid having over 150 dummy variables, we mapped countries to their corresponding continents.  We then created n-1 dummy variables for the continents.  HIV and Thinness were both significantly positively skewed.  So, in order to normalize the distributions we performed log transformations on these two variables.  We experimented with Standardization and Min-Max Scaling, however they failed to improve our model.

# Model


### OLS Regression

<p>
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/MLR.png" width="300" height="100">
</p>

<p align="center">
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/reg_table.png" width="400" height="600">
</p>

### QQ Plot

<p align="center">
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/QQ.png" width="450" height="300">
</p>

### Regression Plots for Schooling

<p align="center">
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/regression_plot.png" width="800" height="500">
</p>

### Polynomial and Ridge Regression

<p align="center">
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/poly_ridge.png" width="300" height="100">
<img src="https://github.com/jmt0221/Life_Expectancy/blob/master/Images/poly.png" width="300" height="100">
</p>

# Final Conclusions

Our best result was in our polynomial regression (RMSE 2.89 years).  However, we used nonpolynomial multiple linear regression (RMSE 4.40 years) as it allowed us to better understand how eeach feature impacted our dependent variable of life expectancy.  We found that the two best predictors of Life Expectancy proved to be:
Schooling:  Average years of education completed per person
HIV-AIDS:  Infections per 100,000 people

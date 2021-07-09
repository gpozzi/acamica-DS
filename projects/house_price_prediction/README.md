# Project at a glance: Real estate market analysis 🏡

I have recently joined the Data team of a large real estate company. The first task assigned is to help appraisers value properties, as it's a difficult and sometimes subjective process. To do this, I propose to create a Machine Learning model that, given certain characteristics of the property, predicts its sale price.

## Motivation
Housing is one of human life's most essential needs, along with other fundamental needs such as food, water, and much more. Demand for houses grew rapidly over the years as  people's living standards improved. While there are people who make their house as an investment and property, yet most people around the world are buying a house as their shelter or as their livelihood.

An increase in house demand occurs each year, indirectly causing house price increases every year. The problem arises when there are numerous variables that may influence the house price, thus most stakeholders including buyers and developers, house builders and the real estate industry would like to know the exact attributes or the accurate factors  influencing the house price to help investors make decisions and help house builders set the house price.

There  are many  benefits that  home buyers,  property investors, and house builders can reap from the house-price model. A good model would provide a lot of information and knowledge to home buyers, property investors and house builders, such as the valuation of house prices in the present market, which will help them determine house prices.  Meanwhile, this model can help potential buyers decide the characteristics of a house they want according to their budget

## Data description
Dataset has been provided by [Properati](https://www.properati.com.ar/data), it contains 1 file: `DS_Proyecto_01_Datos_Properati.csv`
The parameters included are:

- `start_date`: Date of registration of the property publication. (numerical)
- `end_date`: Date in which the publication has been withdrawn. (numerical)
- `created_on`: Date in which the publication has been created. (numerical)
- `lat`: Latitude of the property. (categorical)
- `lon`: Longitude of the property. (categorical)
- `l1`: First administrative level: country. (categorical)
- `l2`: Second administrative level: province. (categorical)
- `l3`: Third administrative level: city. (categorical)
- `rooms`: Amount of rooms. (numerical)
- `bedrooms`: Amount of bedrooms. (numerical)
- `bathrooms`: Amount of bathrooms. (numerical)
- `surface_total`: Total surface of the property (squared meters). (numerical)
- `surface_covered`: Total covered surface of the property (squared meters). (numerical)
- `price`: Price of the property. (numerical)
- `currency`: Currency in which the price is published. (categorical)
- `title`: Publication title. (categorical)
- `description`: Description of the property. (categorical)
- `property_type`: Type of property (house, apartment, PH). (categorical)
- `operation_type`: Type of operation (buy, rent). (categorical)

## Requirements
All the requirements will be given in the requirements.txt file. To install, run pip install -r requirements.txt

## Project description
This project was made for [Acámica's](https://www.acamica.com/data-science) bootcamp and consists of two iteration:
- **Iteration one**: it starts with a comprehensive `EDA` and applying some simple `data cleaning` techniques to end up building a `machine learning regression model` that performs better than a linear regression. Two models have been tried in this project: `decisionTreeRegressor` and `kNeighborsRegressor`
- **Iteration two**: in this version, a more thorough analysis has been performed, performing `data transformation` (imputation, encoding, outliers removal and data scaling) techniques and finally applying more advanced `machine learning regression models` (`XGBRegressor`, `Decision tree optimized with RandomSearchCV`, `XGBRegressor optimized with RandomSearchCV`, `RandomForest regressor`, `RandomForest optimized with RandomSearchCV`, `ADABoost optimized with RandomSearchCV` and `Polynomial regressor`))


- Project tools:
  - `Jupyter Notebook`
  - `Numpy`
  - `Pandas`
  - `Seaborn`
  - `Matplotlib`
  - `Scikit Learn`


- Scope
- Factors that influence house price
- EDA and data cleaning
  - Feature selection
  - Additional analysis: correlation between population density and apartment size
- Machine Learning
  - Selection of measurement of error
  - Setting predictor and target variables
  - Setting benchmark model
  - Comparing benchmark with other models
  - Optimization of the best performing one
- Conclusions




# Some exploratory data analysis

![img](https://i.imgur.com/TQUSCsM.png)

![img](https://i.imgur.com/6EJ0IsP.png)

![img](https://i.imgur.com/ZncBweE.png)

![img](https://i.imgur.com/No65L68.png)

![img](https://i.imgur.com/oYR0MF9.png)

![img](https://i.imgur.com/JW7TDxE.png)

# Conclusions

Although the analysis carried out so far makes it possible to select the best regression model by comparing relative errors, the feasibility of performing price predictions should be taken into account, which is the objective of this document. It should be noted that US $ 138,384, which is the value of the RMSE, is also the value of some apartments, so an error of this magnitude is inadmissible.

This model presents some opportunities for improvement, such as:

- Better handling of missing values, such as imputation, could be done instead of removing these instances from the dataset
- Categorical variables such as the neighborhood or perhaps the presence of some keywords within the description could be introduced to the analysis
- Data external to the dataset could be used such as the location of some points of interest (such as subway stations, hospitals, schools or bus stops) relative to the properties using the coordinates
- As a future improvement of the dataset and taking into account that the pricing of a property (and more so in a real estate market such as Argentina) can present large variations in a short period of time, a binary variable "`sale_status`" (with values like `sold` / `not sold`) could be added. This categorical variable would be easy to collect, and at the same time penalize excessively high prices, resulting in an improvement in the predictive capacity of the model.
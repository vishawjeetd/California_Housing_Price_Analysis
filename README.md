![Logo](https://github.com/vishawjeetd/California_Housing_Price_Analysis/blob/main/img/logo.png?raw=true)





# California Housing Price Analysis

This repository contains the Analysis and implementation of a linear regressor on the California Housing Dataset.




## Implementation Details

### Dataset Details
- **Dataset:** California Housing Dataset from SKLEARN
- **Data Granularity:** Block level
- **Input:** Location, Age of house, Income, Number of rooms & bedrooms, Occupancy of household members, Population
- **Output:** House Prices
- **Source:** 1990 U.S. census
- **Number of Instances:** 20640

### Technical Details
- **Programming Language:** Python
- **Jupyter Notebook:** Google Colab
- **Model:** Linear regressor
- **Packages Used:** sklearn, pandas, numpy, ydata_profiling
- **Code file:** [California_house_price_analysis.ipynb](https://github.com/vishawjeetd/California_Housing_Price_Analysis/blob/main/src/California_house_price_analysis.ipynb)



## Dependancies

Install ydata-profiling to perform EDA

```bash
  pip install ydata-profiling
```

## How to Run

The code is built on Google Colab on an iPython Notebook. 

```bash
Simply download the repository, upload the notebook and dataset on colab, and hit play!
```
    
## Code Architecture

- Data Loading

- EDA(Exploratory data analysis) using ydata_profiling (refer to [california_housing_report.html](https://github.com/vishawjeetd/California_Housing_Price_Analysis/blob/main/src/california_housing_report.html))

- Data Pre-Processing

- Data Modelling on Linear Regression

- Prediction and Evaluation of Linear Regression model with different experiment and KPIs





## Data insights

### Correlation Matrix

![Correlation Image](https://github.com/vishawjeetd/California_Housing_Price_Analysis/blob/main/img/Correlation_matrix.png?raw=True)

### Insights

 - Target is correlated with MedInc
 - Longitude and Latitude is highly correlated, to remove this multi-colinearity we will remove Longitude and keep Latitude as it is more correlated with Target variable.
 - AveRooms, AveOccup, AveBedrms are highly skewed feature, we can apply log transformations and check correlation with target variable
 - Since Target is not highly correlated with HouseAge and Population, we can remove them.
 - We can observe sudden high spike in number of blocks in Target variable for 5 which shows that California is one of the costly real estate.

### Feature Engineering Options

 - As observed in maps, all the important cities, are near the coastal area. The distance from coast can be an additional variable derived longitude and latitude can help to improve model accuracy.
 - Demographic Features:
    - Population density (calculated from Population)   
    - Average household size (calculated from AveOccup) 
    - Bedroom-to-room ratio (calculated from AveBedrms and AveRooms)
    - Logarithmic transformation for skewed data like AveOccup,AveBedrms,AveRooms




## Experiments and results with Linear Regression

I have conducted few experiments with Linear Regression for which I have tracked R2 and MSE KPI

| Experiment Number | Experiment                                                      | R2 of Traning Set | MSE  |
|--------------------|-----------------------------------------------------------------|-------------------|------|
| 1                  | All input variables without any Transformation                  | 0.611             | 0.54 |
| 2                  | Removed Populationa and Longitude                              | 0.549             | 0.632|
| 3                  | Exp No 2 + Log Transformation of AveOccup, AveRooms, AveBedrms| 0.611             | 0.545|
| 4                  | Exp No 3 + Removed House Age                                   | 0.582             | 0.574|
| 5                  | Only MedInc                                                     | 0.481             | 0.725|



## FAQ

#### How does the linear regression model work?

Linear regression is a statistical method used to model the relationship between a dependent variable and one or more independent variables by fitting a straight line to the observed data points. The model aims to minimize the difference between the observed values and the values predicted by the linear equation, allowing for prediction and understanding of the dependent variable's behavior based on the independent variables.


#### What is R2 or R-sqared?

The coefficient of determination (R-squared) in linear regression represents the proportion of the variance in the dependent variable that is predictable from the independent variables. It ranges from 0 to 1, with higher values indicating a better fit of the regression model to the data.

#### What is MSE?

Mean Squared Error (MSE) is a measure of the average squared difference between the actual values and the predicted values produced by a regression model. It provides a quantitative assessment of the model's performance, with lower MSE values indicating better predictive accuracy.


## License

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)

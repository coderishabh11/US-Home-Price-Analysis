# US Home Prices Analysis

This repository contains an analysis of the factors affecting US home prices over the last 20 years. The project involves data collection, exploratory data analysis (EDA), model building, and predictive analytics, all conducted within a Jupyter Notebook.

## Table of Contents
- [Introduction](#introduction)
- [Data Collection and Integration](#data-collection-and-integration)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Model Building](#model-building)
- [Results and Conclusion](#results-and-conclusion)
- [Future Work](#future-work)
- [Requirements](#requirements)
- [Usage](#usage)

## Introduction
This project explores the impact of various economic factors on US home prices using publicly available data. The goal is to identify key drivers of home price changes and build predictive models to understand their influence.

## Data Collection and Integration

### Data Sources
Data was collected from the following sources:
- **Home Price Index**: Federal Reserve Bank of St. Louis (FRED)
- **GDP**: Federal Reserve Bank of St. Louis (FRED)
- **Inflation Rate**: US Inflation Calculator
- **Unemployment Rate**: Federal Reserve Bank of St. Louis (FRED)
- **Population Growth**: World Bank

### Data Integration
Data from each source was integrated based on the date of the Home Price Index, ensuring consistency across all variables.

## Exploratory Data Analysis

### Descriptive Statistics
Descriptive statistics were generated for each variable to understand their distribution, central tendency, and spread.

### Data Visualization
- **Heat Map**: A heat map was used to visualize correlations between the Home Price Index and other economic factors.
- **Time Series Plots**: Time series plots were generated for each variable to observe trends over time. Data was normalized using `StandardScaler` to bring all metrics into a similar range.

## Model Building

### Linear Regression
A Linear Regression model was initially built with the following performance:
- **Mean Squared Error (MSE)**: 492.33
- **R-squared**: 0.91

### Advanced Techniques
- **Feature Selection**: Random Forest was used for feature selection, identifying GDP as a key predictor.
- **XGBoost**: An XGBoost model was tuned using `GridSearchCV` with the following best parameters:
  - Learning Rate: 0.2
  - Max Depth: 6
  - N Estimators: 200
  - Subsample: 0.7

  Performance:
  - **MSE**: 67.57
  - **R-squared**: 0.99

- **Ensemble Methods**: An ensemble model combining Random Forest and XGBoost was tested, achieving:
  - **MSE**: 80.37
  - **R-squared**: 0.99

- **Advanced Hyperparameter Tuning**: Bayesian Optimization was used for further fine-tuning XGBoost parameters, leading to:
  - **MSE**: 64.64
  - **R-squared**: 0.99

### Feature Importance
The final model identified GDP as the most important feature affecting the Home Price Index.

## Results and Conclusion
The analysis revealed that GDP is a significant predictor of the Home Price Index. The advanced models provided improved performance, with Bayesian Optimization yielding the best results.

## Future Work
- Explore additional features and incorporate more granular data.
- Investigate the impact of other economic indicators on home prices.
- Experiment with different modeling techniques and ensembling strategies.

## Requirements
- Python 3.x
- pandas
- numpy
- scikit-learn
- XGBoost
- matplotlib
- seaborn
- jupyter

## Usage
1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/us-home-prices-analysis.git
    ```

2. Open the Jupyter Notebook:
    ```sh
    jupyter notebook US_Home_Prices_Analysis.ipynb
    ```

3. Run the notebook cells to reproduce the analysis and results.

---

Feel free to contribute to the project by submitting issues or pull requests. For any questions, contact me at [coderishabh0411@gmail.com](mailto:coderishabh0411@gmail.com).

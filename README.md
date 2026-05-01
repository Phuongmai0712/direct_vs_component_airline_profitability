# Airline Profitability Prediction: Comparing Direct vs. Component-Based Approaches

## Project Overview

This project focuses on analyzing and predicting the profitability of airline routes using machine learning techniques. The core objective is to compare two different approaches for forecasting **profit margins**:

- **Direct Approach**: Predicting the profit margin directly using machine learning models.
- **Indirect (Component-Based) Approach**: Predicting key components of profit (revenue and cost) separately and then computing the final profit margin.

We aim to determine which approach performs better for predicting profitability in the airline sector, with a particular focus on model evaluation, interpretability, and real-world applicability.

## Key Features

- **Data Preprocessing**: Handling missing values, feature engineering, and preparing the dataset for modeling.
- **Modeling Approaches**: Comparison of **Linear Regression**, **Random Forest**, and **XGBoost** models.
- **Performance Metrics**: Evaluation based on **RMSE**, **MAE**, and **R²**.
- **Explainability**: Use of **SHAP** values to explain the contributions of different features to the model predictions.

## Dataset

The dataset used in this project is from Kaggle: [Airline Route Profitability and Cost Analysis](https://www.kaggle.com/datasets/waleedfaheem/airline-route-profitability-and-cost-analysis). It contains operational and financial data of airline routes, including information about ticket sales, costs, and profitability across different routes.

Key attributes include:
- **Revenue-related variables**: Ticket revenue, ancillary revenue, total revenue.
- **Cost-related variables**: Fuel cost, maintenance cost, crew cost, and more.
- **Operational variables**: Load factor, aircraft capacity, flight hours.

## Methodology

1. **Data Preprocessing**: 
    - Missing data imputation using logic calculation and medians.
    - Feature engineering to create meaningful derived variables (e.g., revenue per passenger, cost per passenger).

2. **Modeling**: 
    - **Direct Approach**: Profit margin is predicted directly using a machine learning model.
    - **Indirect Approach**: Revenue and cost are predicted separately using machine learning, and the profit margin is calculated from these components.
    - Models compared include **Linear Regression**, **Random Forest**, and **XGBoost**.

3. **Evaluation**: 
    - Metrics such as **RMSE**, **MAE**, and **R²** are used to assess model performance.
    - **SHAP** values are used to provide insights into the feature importance for each model.

## How to Run the Code

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/username/project-name.git
    cd project-name
    ```

2. **Install Dependencies**:
    Ensure you have **Python 3.x** installed and then use the following command to install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. **Run the Analysis**:
    - Navigate to the `notebooks/` directory and open `analysis_notebook.ipynb`.
    - Follow the steps in the notebook to load the data, perform the analysis, train the models, and evaluate performance.

4. **Model Training and Evaluation**:
    - The models are trained and evaluated within the notebook. You can use different approaches by running the respective cells and viewing the results.

## Results

- **Best Model**: The **Linear Regression** model performed the best for **direct prediction** of the profit margin.
- **Model Performance**: Results are evaluated based on **RMSE**, **MAE**, and **R²**, with the **XGBoost** model performing well for indirect predictions (component-wise prediction).
- **SHAP Analysis**: SHAP values provide insights into the contribution of each feature, highlighting the most influential factors for profitability.

## Files in the Repository

- `/data`: Contains the raw dataset used for analysis.
- `/notebooks`: Jupyter notebooks for data analysis and model building.
- `/src`: Python scripts for preprocessing, training, and evaluating models.
- `/results`: Contains model results, including evaluation metrics and SHAP plots.
- `README.md`: This file providing an overview of the project.
- `requirements.txt`: Python dependencies needed to run the project.

## Contributing

If you would like to contribute to this project, feel free to fork the repository, make changes, and create a pull request. Please ensure that all code adheres to the style guidelines, and include explanations for any changes made.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- **Kaggle** for providing the dataset [Airline Route Profitability and Cost Analysis](https://www.kaggle.com/datasets/waleedfaheem/airline-route-profitability-and-cost-analysis).
- **SHAP** for model explainability.
- **Scikit-learn**, **XGBoost**, **LightGBM**, and other libraries for machine learning tools.

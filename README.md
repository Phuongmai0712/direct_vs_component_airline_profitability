# Airline Profitability: Direct vs. Component-Based Prediction

A machine learning project comparing two ways to estimate airline route profit margin:

- **Direct:** predict profit margin directly.
- **Component-based:** predict total revenue and total cost separately, then reconstruct profit margin.

The aim is not only to compare predictive accuracy, but also to understand whether modelling the financial components separately produces a more useful profitability estimate.

## Dataset

The analysis uses the Kaggle [Airline Route Profitability and Cost Analysis](https://www.kaggle.com/datasets/waleedfaheem/airline-route-profitability-and-cost-analysis) dataset with **7,974 rows and 33 variables** covering route characteristics, demand, aircraft operations, revenue and costs.

The workflow includes consistency checks, missing-value treatment, exploratory analysis and feature engineering before modelling.

## Approach

Three regression models were compared:

- Linear Regression
- Random Forest
- XGBoost

Models use route and operational information such as destination, aircraft type, season, route category, demand level, aircraft capacity, load factor and flight hours.

Performance was evaluated using **RMSE, MAE and R²**.

For interpretability, the analysis also uses:

- Linear Regression coefficients
- SHAP analysis for XGBoost profit-margin, revenue and cost models

## Key Results

| Model | Direct RMSE | Direct R² | Component RMSE | Component R² |
|---|---:|---:|---:|---:|
| Linear Regression | **21.16** | **0.698** | 63.26 | -1.701 |
| XGBoost | 21.51 | 0.688 | **21.75** | **0.681** |
| Random Forest | 22.23 | 0.667 | 22.61 | 0.655 |

**Main finding:** direct profit-margin prediction performed better than the component-based approach for all three model families.

Linear Regression produced the strongest direct result, while XGBoost produced the strongest component-based result. The component models were able to predict revenue and cost relatively well, but reconstructing profit margin from two separate predictions introduced additional error. This was particularly visible for Linear Regression.

## Repository Structure

```text
.
├── data/
│   └── airline_route_profitability.csv
├── notebooks/
│   └── airline_profitability_analysis.ipynb
├── requirements.txt
├── .gitignore
├── LICENSE
└── README.md
```

## Run Locally

```bash
git clone https://github.com/Phuongmai0712/direct_vs_component_airline_profitability.git
cd direct_vs_component_airline_profitability
pip install -r requirements.txt
jupyter notebook notebooks/airline_profitability_analysis.ipynb
```

> **Note:** the notebook should load the dataset using the repository-relative path `../data/airline_route_profitability.csv` when run from the `notebooks/` directory.

## Tools

Python · pandas · NumPy · SciPy · scikit-learn · XGBoost · SHAP · Matplotlib · Seaborn

## License

MIT License.
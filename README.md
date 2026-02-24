# GDP-prediction-based-on-tourism-RapidMinor-
predicting the economic effects of global tourism using a tourism and economy dataset.   The analysis is implemented in **RapidMiner** and follows the **CRISP-DM methodology**.
## Problem Statement
Tourism has a strong impact on national economies, but the relationship between tourism indicators and GDP can vary across countries and years.

This project aims to:
- analyze tourism and economic data,
- clean and prepare the dataset,
- build regression models to predict **GDP**,
- compare model performance,
- provide insights and recommendations for tourism/economic planning.

---

## Objectives
- Understand the relationship between tourism-related variables and GDP
- Prepare a clean dataset suitable for modeling in RapidMiner
- Build and compare regression models
- Evaluate model performance using appropriate metrics
- Support evidence-based policy and planning decisions

---

## Methodology
This project uses **CRISP-DM (Cross-Industry Standard Process for Data Mining)**:

1. **Business Understanding**
2. **Data Understanding**
3. **Data Preparation**
4. **Modeling**
5. **Evaluation**
6. **Deployment / Reporting**

---

## Dataset
- **Source:** Kaggle (Tourism and Economic Impact dataset)
- **Dataset link:** https://www.kaggle.com/datasets/bushraqurban/tourism-and-economic-impact

### Target Variable
- `gdp`

### Predictor Variables (used)
- `tourism_arrivals`
- `tourism_receipts`
- `tourism_exports`
- `tourism_expenditures`
- `tourism_departures`
- `inflation`
- `unemployment`
- `year`

### ID / Reference Fields
- `country_code` (used as ID)
- `country` (kept for interpretation/reporting)

---

## Data Preparation (RapidMiner)
The preprocessing stage includes:
- Attribute selection (keeping only relevant fields)
- Setting roles:
  - `gdp` as **label**
  - `country_code` as **id**
- Filtering rows with unusable records (where required)
- Handling missing values (imputation in RapidMiner)
- Creating missing-value indicator attributes (`miss_...`) to preserve missingness information
- Generating additional derived features (e.g., engineered variables such as ratios/net flow, depending on process version)
- Exporting/storing the cleaned dataset for modeling

> Note: Missing indicator attributes were created because imputation hides the fact that a value was originally missing. These flags help the model learn whether missingness itself carries useful information.

---

## Models Used
This assignment uses regression models to predict GDP:

- **Linear Regression**
- **Decision Tree Regression**
- **Random Forest Regression**
- *(Optional / advanced, depending on final group process)* Gradient Boosted Trees / GBR

---

## Evaluation Metrics
Model performance is evaluated using regression metrics in RapidMiner, such as:
- **Root Mean Squared Error (RMSE)**
- **Absolute Error (MAE)**
- **Squared Correlation (R²-related metric in RapidMiner output)**

Cross-validation is used to compare models fairly.

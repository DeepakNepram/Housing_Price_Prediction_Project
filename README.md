# California Housing Price Prediction

## Project Overview

This project tackles a regression problem: predicting median house values for districts in California based on features such as location, median income, housing age, and proximity to the ocean.[file:36]

The goal is to build a machine learning model that can estimate house prices and help stakeholders like real estate analysts, investors, or policy makers understand what drives housing values.

## Dataset

- **Name:** California Housing Prices dataset
- **Source:** Kaggle dataset `camnugent/california-housing-prices` (originally based on the California Housing dataset used by the StatLib repository).[file:36]
- **Rows:** ~20,640
- **Columns:** 10, including `longitude`, `latitude`, `housing_median_age`, `total_rooms`, `total_bedrooms`, `population`, `households`, `median_income`, `median_house_value`, and `ocean_proximity`.[file:36]
- **Target variable:** `median_house_value` (continuous).

> Note: The notebook uses the `opendatasets` library and Kaggle API to download the dataset directly. You can also download it manually from Kaggle if you prefer.[file:36]

## Objectives

1. Understand the distribution of housing prices and key features across California.
2. Perform EDA to explore relationships between median house value and other variables.
3. Build a regression model to predict house prices.
4. Evaluate model performance using suitable regression metrics and interpret the model’s behaviour.

## Methods and Workflow

The notebook `Housing_price_project.ipynb` follows these steps:[file:36]

1. **Data acquisition**
   - Use `opendatasets` to download the California housing prices dataset directly from Kaggle.
   - Copy the CSV (`housing.csv`) to Google Drive / project folder for easier access.[file:36]

2. **Data loading and inspection**
   - Load `housing.csv` into a pandas DataFrame.
   - Inspect the head of the dataset and check its shape (around 20,640 rows × 10 columns).[file:36]
   - Review data types and basic statistics.

3. **Preprocessing**
   - Handle missing values (e.g., in `total_bedrooms`).
   - Encode the categorical variable `ocean_proximity` using `LabelEncoder` or one‑hot encoding.
   - Split data into training and test sets using `train_test_split`.

4. **Modeling**
   - Train a **Linear Regression** model (from `sklearn.linear_model`) on the training data.[file:36]
   - Predict `median_house_value` on the test set.

5. **Evaluation**
   - Use regression metrics such as Mean Squared Error (MSE) and R² score to evaluate model performance (`mean_squared_error`, `r2_score`).[file:36]
   - Interpret coefficients and feature influence where appropriate.

6. **Insights**
   - Discuss how variables such as `median_income` and `ocean_proximity` affect house prices.
   - Highlight practical usage, e.g., rough price estimation, identifying high‑value areas, or studying affordability.


## How to Run the Notebook

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/data-analytics-projects.git
   cd data-analytics-projects/california-housing-prices
   ```

2. Install dependencies:

   ```bash
   pip install -r ../requirements.txt
   ```

3. Download the dataset:
   - Either sign in to Kaggle and set up your API credentials, then let the notebook download the dataset using `opendatasets`.
   - Or download `housing.csv` from the Kaggle dataset page and place it in this folder.

4. Open the notebook in Jupyter or Google Colab and run all cells.

## Future Improvements

- Try more advanced models like Random Forest Regressor, Gradient Boosting, or XGBoost.
- Add feature engineering (e.g., rooms per household, bedrooms per room, population per household).
- Integrate geospatial visualizations (maps) to show geographic patterns in house prices.

# From Pitch to Price: A Machine Learning Approach to Football Player Valuation

This repository contains the code and analysis for a project aimed at building a predictive model to estimate the market value of professional football players. The model leverages a dataset of personal, technical, and financial attributes to provide accurate valuations.

The core of this project is a Gradient Boosting Regressor, chosen for its ability to capture complex, non-linear relationships in the data. A significant emphasis was placed on creating a model that is not only accurate but also robust and relevant for real-world scenarios.

## 📄 In-Depth Analysis

For a comprehensive explanation of the project, including detailed discussions on feature selection, model evaluation, and interpretation of the results, **please read the full project report:**

➡️ **[FROM PITCH TO PRICE.pdf](FROM%20PITCH%20TO%20PRICE.pdf)**

## 🚀 Key Features & Methodology

*   **Feature Engineering:**
    *   Player positions were grouped into ten broader tactical categories and one-hot encoded.
    *   A binary feature was created to identify players in Europe's top 5 leagues.
    *   A `years_to_end_contract` feature was calculated to capture contract length.

*   **Thoughtful Feature Selection:**
    *   To maintain causal and temporal validity, financially-derived features like `release_clause_eur` and `wage_eur` were intentionally excluded from the final model. These are often *results* of a player's valuation, not predictors of it.
    *   Highly correlated technical attributes (e.g., `dribbling`, `short_passing`) were removed to avoid multicollinearity, retaining the most informative feature (`overall`) from each group.

*   **Robust Modeling & Validation:**
    *   A **Gradient Boosting Regressor** was selected as the final model.
    *   **5-fold cross-validation** was used throughout the process to ensure the model's performance is stable and generalizes well to new data, preventing overfitting.
    *   Hyperparameter tuning was performed using `GridSearchCV` to find the optimal model configuration.

*   **Data Handling:**
    *   Skewed monetary features were log-transformed to create more normal distributions.
    *   Missing values were handled systematically, using median imputation for features with a low percentage of missing data.

## 📊 Results

The final optimized model demonstrated strong predictive performance on the test set:

-   **Root Mean Squared Error (RMSE):** ~€450,000
-   **R² Score:** 0.9964

The feature importance analysis revealed that `overall` rating, `potential`, and `age` are the three most influential factors in determining a player's market value, aligning with real-world football industry valuation practices.

## 📂 Repository Content
-   **`data/`**: This folder should contain the dataset used for the analysis.
-   **`from_pitch_to_price.ipynb`**: The Jupyter Notebook containing all the Python code for data preprocessing, exploratory data analysis, feature engineering, model training, and evaluation.
-   **`FROM PITCH TO PRICE.pdf`**: The detailed project report.

## ⚙️ How to Use

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/From-Pitch-to-Price-Football-Player-Valuation.git
    ```
2.  **Install the necessary libraries:**
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn jupyter
    ```
3.  **Place your dataset** in the `data/` folder.
4.  **Launch Jupyter Notebook** and open `from_pitch_to_price.ipynb` to explore the code.

# Anti-Money Laundering (AML) Detection System

## Description

This project is an advanced Anti-Money Laundering (AML) detection system developed to identify potentially fraudulent financial transactions. Using the SAML-D dataset, this system employs a variety of machine learning models to classify transactions as either legitimate or indicative of money laundering. The project includes comprehensive data preprocessing, sophisticated feature engineering, and a comparative analysis of several models to ensure high accuracy and reliability in detecting illicit activities.

## Dataset

The analysis is performed on the **SAML-D (Synthetic Anti-Money Laundering Transaction Data)** dataset. This dataset is designed to simulate real-world financial transactions and includes a wide range of attributes, such as:

- Transaction amounts and currencies
- Sender and receiver account details
- Bank locations and payment types
- Timestamps of transactions

A key characteristic of this dataset is its significant class imbalance, with fraudulent transactions being a very small fraction of the total volume, which is a common challenge in fraud detection.

## Methodology

The project follows a structured approach to building the AML detection system:

1.  **Data Loading and Preprocessing**: The SAML-D dataset is loaded, and initial data cleaning is performed. This includes handling duplicates and converting date and time columns into a usable format.
2.  **Advanced Feature Engineering**: To improve model performance, new features are created, such as transaction timing indicators (e.g., late-night transactions), amount-based features (e.g., logarithmic and square root transformations), and account-based aggregations (e.g., transaction counts and average amounts for senders and receivers).
3.  **Handling Class Imbalance**: The significant class imbalance is addressed using the **Synthetic Minority Over-sampling Technique (SMOTE)**. This technique generates synthetic samples for the minority class (money laundering transactions) to create a more balanced dataset for training the models.
4.  **Model Training and Evaluation**: Several machine learning models are trained on the preprocessed and balanced data. The models are evaluated based on key performance metrics such as **AUC-ROC, F1-Score, Precision, and Recall**.

## Models Used

The following machine learning models were implemented and compared:

-   **Logistic Regression**
-   **Random Forest**
-   **XGBoost**
-   **LightGBM**

## Results

The models demonstrated exceptional performance in detecting money laundering activities. Here is a summary of the key metrics:

| Model               | AUC-ROC | F1-Score | Precision | Recall |
| :------------------ | :------ | :------- | :-------- | :----- |
| **Random Forest** | 0.9998  | 0.8524   | 1.0000    | 0.7427 |
| **XGBoost** | 1.0000  | 1.0000   | 1.0000    | 1.0000 |
| **LightGBM** | 1.0000  | 1.0000   | 1.0000    | 1.0000 |
| **Logistic Regression** | 1.0000  | 1.0000   | 1.0000    | 1.0000 |

**XGBoost**, **LightGBM**, and **Logistic Regression** all achieved perfect scores across all metrics, indicating their high effectiveness in this classification task.

## Visualizations

The project includes several visualizations to provide deeper insights into the data and model performance:

-   **Class Distribution**: A pie chart showing the proportion of normal versus money laundering transactions.
-   **Amount Distribution by Class**: Histograms comparing the distribution of transaction amounts for both classes.
-   **Transactions by Hour**: A bar chart illustrating the frequency of transactions at different hours of the day.
-   **ROC and Precision-Recall Curves**: Plots comparing the trade-offs between true positive and false positive rates for each model.
-   **Feature Importance**: A bar chart highlighting the most influential features in the Random Forest model's predictions.

## How to Run the Code

To run this project on your local machine, follow these steps:

1.  **Clone the repository**:
    ```bash
    git clone [https://github.com/your-username/aml-detection-system.git](https://github.com/your-username/aml-detection-system.git)
    ```
2.  **Navigate to the project directory**:
    ```bash
    cd aml-detection-system
    ```
3.  **Install the required libraries**:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost lightgbm shap
    ```
4.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```
5.  **Open and run the `Final (1).ipynb` notebook.**


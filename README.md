# Laptop Price Predictor (Regression)

## Project Overview
Buying a laptop is complex due to the hundreds of specifications available. This project uses **Machine Learning** to predict the price of a laptop based on features like Brand, RAM, Weight, CPU, and Operating System. 

The goal was to build a robust **Regression model** that can estimate prices with high accuracy, helping both buyers and sellers understand market value.

---

## Data Science Workflow

### 1. Data Cleaning & Preprocessing
* **Unit Removal:** Extracted numeric values from columns like `Ram` (8GB -> 8) and `Weight` (1.5kg -> 1.5).
* **Memory Extraction:** Cleaned the `Memory` column to extract the primary storage capacity (SSD/HDD).
* **Log Transformation:** Applied a Logarithmic transformation to the target variable (`Price`) to handle skewness and improve model convergence.

### 2. Feature Engineering
* **CPU/GPU Categorization:** Reduced the high cardinality of CPU and GPU models by grouping them into primary brands (Intel i3, i5, i7, AMD, etc.).
* **One-Hot Encoding:** Converted categorical text data into a numerical format that the model can interpret.

### 3. Machine Learning Pipeline
I implemented a **Scikit-Learn Pipeline** to streamline the process:
* **Step 1:** `ColumnTransformer` for One-Hot Encoding and numeric passthrough.
* **Step 2:** `RandomForestRegressor` (An ensemble method that uses multiple decision trees to reduce variance and improve accuracy).

---

## Results & Performance
By shifting from a simple Linear Regression to a **Random Forest Regressor**, the model performance improved significantly:

* **R2 Score:** ~0.88 (The model explains 88% of the price variation).
* **Mean Absolute Error (MAE):** Minimal log-error, indicating highly reliable predictions.



---

## Tech Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn
* **ML Framework:** Scikit-Learn
* **Environment:** Google Colab

---

## Repository Structure
```text
├── laptop_data.csv        # Raw dataset
├── Laptop_Price_ML.ipynb  # Structured Google Colab Notebook
└── README.md              # Project Documentation

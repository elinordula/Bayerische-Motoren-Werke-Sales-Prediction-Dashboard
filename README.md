# Bayerische-Motoren-Werke-Sales-Prediction-Dashboard

## Overview
This project is an AI-powered **sales prediction system** designed for **BMW vehicles**.  
It analyzes key attributes of a car — such as **model, year, region, mileage, and price** — to determine the likelihood of a successful sale.  
The tool uses **machine learning (Random Forest Classifier)** and provides an **interactive Gradio dashboard** for car dealerships and sellers to get actionable insights before listing their cars.

---

## Dataset Used
The dataset used in this project is **BMW_Car_Sales_Classification.csv**.

It contains detailed information such as:
- **Model**
- **Year**
- **Region**
- **Color**
- **Fuel type**
- **Transmission**
- **Engine size (L)**
- **Mileage (KM)**
- **Price (USD)**
- **Sales Classification** (High or Low)

The target column is `sales_classification`, where:
- **High (1)** → Car likely to be sold quickly  
- **Low (0)** → Car unlikely to be sold quickly  

---

## Features Used in the Prediction
The current model uses the following features for predictions:
- **model** (Car model name)
- **year** (Year of manufacture)
- **region** (Geographic region of sale)
- **color** (Car color)
- **fuel_type** (Petrol, Diesel, Hybrid, Electric)
- **transmission** (Manual or Automatic)
- **engine_size_l** (Engine size in liters)
- **mileage_km** (Distance driven in kilometers)
- **price_usd** (Listing price in USD)

---

## How It Works

### 1. Data Cleaning
- Removed unnecessary columns (`sales_volume`)
- Renamed columns to lowercase and replaced spaces with underscores
- Mapped `sales_classification` to binary values (0 for Low, 1 for High)

### 2. Preprocessing
- **One-hot encoding** for categorical features
- **Standard scaling** for numerical features

### 3. Handling Class Imbalance
- Used **SMOTE (Synthetic Minority Oversampling Technique)** to balance the dataset

### 4. Model Training
- Model: **Random Forest Classifier**
- Parameters:
  - `n_estimators = 200`
  - `max_depth = 10`
  - `min_samples_split = 5`
- Trained on the resampled dataset

### 5. Evaluation
- Evaluated using **classification report** (precision, recall, f1-score)
- Extracted **feature importances** for interpretability

### 6. Gradio Interface
- Built an interactive **dashboard** using Gradio’s `Blocks`
- Allows users to input car details and get:
  - **Prediction**: "Car Likely to be SOLD" or "Car Likely NOT to be Sold"
- Styled with **custom CSS** for a modern, BMW-themed UI

---

## Example Inputs & Outputs

| Model   | Year | Region     | Color  | Fuel Type | Transmission | Engine Size (L) | Mileage (KM) | Price (USD) | Output                         |
|---------|------|------------|--------|-----------|--------------|-----------------|--------------|-------------|--------------------------------|
| 3 Series| 2018 | Europe     | White  | Petrol    | Automatic    | 3.2             | 100000       | 75000       | Car Likely to be SOLD          |
| X5      | 2015 | Asia       | Black  | Diesel    | Manual       | 2.5             | 150000       | 50000       | Car Likely NOT to be Sold      |

---

## Tools and Libraries Used
- **Python**
- **Pandas**, **NumPy**
- **Scikit-learn** (RandomForestClassifier, preprocessing, train-test split)
- **Imbalanced-learn** (SMOTE)
- **Gradio** (Interactive dashboard)
- **Matplotlib** / **Seaborn** (optional, for feature importance visualization)

---



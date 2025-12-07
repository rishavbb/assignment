# Late Delivery Prediction

Predict whether a delivery trip is late (`is_late_delivery`) using trip metadata. Includes EDA, preprocessing (impute + one-hot + scaling), and two models: Logistic Regression and XGBoost.

## Data
Input: `data/delivery_trips.csv.xlsx`  
Target: `is_late_delivery` (1 = late, 0 = on-time)

> Note: `actual_duration_min` is post-trip and should be excluded for pre-trip prediction (leakage).

## Setup
```bash
pip install -r requirements.txt
```

## Run
Open `notebooks/analysis.ipynb` and run:
1) EDA & sanity checks  
2) Stratified train/test split  
3) Preprocess via `ColumnTransformer`:
   - numeric: median impute + `StandardScaler`
   - categorical: mode impute + `OneHotEncoder(handle_unknown="ignore")`
4) Train Logistic Regression + XGBoost  
5) Evaluate: Average Precision (PR AUC), ROC AUC, F1 (+ confusion matrix)

## Metrics Used
- **Average Precision (PR AUC)**
- **ROC AUC** 
- **Confusion Matrix**
- **F1** 

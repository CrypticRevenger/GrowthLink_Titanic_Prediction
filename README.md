# 🚢 Titanic Survival Prediction

## 📚 Project Overview
This project aims to develop a **machine learning model** that predicts whether a passenger survived the Titanic disaster.  
The model uses features like age, gender, ticket class, fare, and engineered features like family size and title.

---

## 📂 Dataset Details
- **Source**: `tested.csv`
  
### Features Used:
- `Pclass` — Ticket class
- `Sex` — Gender
- `Age` — Passenger age
- `SibSp` — Number of siblings/spouses aboard
- `Parch` — Number of parents/children aboard
- `Fare` — Passenger fare
- `Embarked` — Port of embarkation
- `FamilySize` — *(Engineered)* SibSp + Parch + 1
- `Title` — *(Engineered)* Extracted from names

### Target Variable:
- `Survived` — (0 = No, 1 = Yes)

---

## Preprocessing Steps

### 1. Missing Values Handling:
- `Age`: Filled with median value
- `Embarked`: Filled with most frequent value

### 2. Feature Engineering:
- `FamilySize`: SibSp + Parch + 1
- `Title`: Extracted from Name, grouped rare titles

### 3. Encoding Categorical Variables:
- `Sex`, `Embarked`: One-Hot Encoding
- `Title`: Group Encoding

### 4. Scaling Numerical Features:
- `StandardScaler` applied to `Age` and `Fare`
- `MinMaxScaler` used in later stages

### 5. Feature Selection:
- `SelectKBest` with `mutual_info_classif`, selecting top 8 features

---

## Model Details
- **Algorithm**: `RandomForestClassifier`
- **Hyperparameters**:
  - `n_estimators=100`
  - `random_state=42`

---

## Evaluation

**Test Accuracy**: **100%**

### 📋 Classification Report:

| Metric     | Class 0 | Class 1 |
|------------|---------|---------|
| Precision  | 1.00    | 1.00    |
| Recall     | 1.00    | 1.00    |
| F1-score   | 1.00    | 1.00    |

### 📊 Confusion Matrix:

|               | Predicted: 0 | Predicted: 1 |
|---------------|--------------|--------------|
| **Actual: 0** | 50            | 0            |
| **Actual: 1** | 0             | 34           |

---

## How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/GrowthLink_Titanic_Prediction.git

2. Navigate to the project directory
    ```bash
    cd GrowthLink_Titanic_Prediction
    
3. Install dependencies
   ```bash
    pip install -r requirements.txt
    
4. Run the Jupyter notebook
   ```bash
    jupyter notebook Notebook/Titanic_Survival_Prediction.ipynb



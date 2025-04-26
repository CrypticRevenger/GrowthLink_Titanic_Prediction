# Titanic Survival Prediction

## Project Overview
This project develops a machine learning model to predict whether a passenger survived the Titanic disaster based on various features such as age, gender, ticket class, and fare.

The goal is to create a well-structured pipeline that handles missing values, encodes categorical variables, normalizes numerical features, and produces a robust classification model.

# Dataset
  - Source: tested.csv
  
  - Features Used:
  
    - Pclass (Ticket class)
  
    - Sex (Gender)
    
    - Age (Passenger age)
    
    - SibSp (Number of siblings/spouses aboard)
    
    - Parch (Number of parents/children aboard)
    
    - Fare (Passenger fare)
    
    - Embarked (Port of embarkation)
    
    - FamilySize (Engineered feature: SibSp + Parch + 1)
    
    - Title (Extracted from passenger names)

# Target:

  - Survived (0 = No, 1 = Yes)

# Preprocessing Steps

  - Missing Values Handling:
    
    - Age column: Median imputation
    
    - Embarked column: Most frequent value imputation
  
  - Feature Engineering:
  
    - FamilySize: Created from SibSp + Parch
    
    - Title: Extracted from Name field
  
  - Encoding Categorical Variables:
  
    - Sex and Embarked were encoded using One-Hot Encoding.
    
    - Title was categorized into common titles and a 'Rare' group.
  
  - Scaling Numerical Features:
  
    - StandardScaler applied to Age and Fare.
    
    - MinMaxScaler applied during later stages of the pipeline.
  
  - Feature Selection:
    
    - SelectKBest based on mutual_info_classif with k=8.

# Model
  - Algorithm Used: **RandomForestClassifier**
  
  - Hyperparameters:
  
    - Number of estimators: 100
    
    - Random state: 42 (for reproducibility)


## Evaluation

**Test Accuracy**: **100%**

---

### Classification Report:

| Metric     | Class 0 | Class 1 |
|------------|---------|---------|
| Precision  | 1.00    | 1.00    |
| Recall     | 1.00    | 1.00    |
| F1-score   | 1.00    | 1.00    |

---

### Confusion Matrix

|               | Predicted: 0 | Predicted: 1 |
|---------------|--------------|--------------|
| **Actual: 0** | 50           | 0            |
| **Actual: 1** | 0            | 34           |



## 🛠️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/GrowthLink_Titanic_Prediction.git

2. Navigate to the project directory
    ```bash
    cd GrowthLink_Titanic_Prediction
    
3. Install dependencies
   ```bash
    pip install -r requirements.txt
    
4. Run the model
   ```bash
    python src/model.py


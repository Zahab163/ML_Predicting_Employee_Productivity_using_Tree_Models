
# 🧵 Predicting Employee Productivity Using Tree-Based Models

This project analyzes employee productivity in a garment manufacturing setting using machine learning techniques. Implemented in **Google Colab**, it applies **Decision Tree** and **Random Forest** models, validated through **Cross-Validation**, to predict actual productivity based on operational and behavioral features.

## [Live Demo](https://youtu.be/nsJjcOGfSFE?si=b8NbYxxL8tQV_Lkb)

## 🎯 Objectives

- Explore and preprocess real-world productivity data.
- Train a Decision Tree model to predict `actual_productivity`.
- Evaluate model performance using multiple metrics and cross-validation.
- Apply Random Forest for improved accuracy and generalization.
- Analyze feature importance to understand key productivity drivers.

## 📁 Project Structure
├── employee_productivity.ipynb   # Main Colab notebook ├── employee_productivity.csv     # Dataset (uploaded manually or via Google Drive) ├── README.md                     # Project documentation


## 🎯 Objectives

- Train a Decision Tree Classifier to predict productivity.
- Evaluate model performance using:
  - Accuracy
  - Precision
  - Recall
  - F1 Score
- Apply 10-fold Cross-Validation for robust evaluation.
- Introduce Random Forest to reduce overfitting and improve results.

## 📊 Dataset Features & Descriptions

The dataset captures daily operational data from garment manufacturing teams. Each row represents a team's performance on a given day. Below are the features included:

| Feature Name             | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| `date`                   | The calendar date of the observation (e.g., `1/1/2015`)                     |
| `quarter`                | Fiscal quarter in which the date falls (e.g., `Quarter1`)                   |
| `department`             | Department name (`sweing`, `finishing`, etc.)                              |
| `day`                    | Day of the week (e.g., `Thursday`)                                          |
| `team`                   | Team number assigned to the production unit                                 |
| `targeted_productivity`  | Target productivity assigned to the team (float between 0 and 1)            |
| `smv`                    | Standard Minute Value – time required to complete a task                    |
| `wip`                    | Work In Progress – unfinished items at the start of the day                 |
| `over_time`              | Total overtime minutes worked by the team                                   |
| `incentive`              | Monetary incentive given to the team (in local currency units)              |
| `idle_time`              | Total minutes of idle time during the day                                   |
| `idle_men`               | Number of workers idle during the day                                       |
| `no_of_style_change`     | Number of style changes (product variations) during the day                 |
| `no_of_workers`          | Total number of workers in the team                                         |
| `actual_productivity`    | Actual productivity achieved by the team (target variable, float 0–1)       |

> 🔍 Note: Some values like `wip` may contain missing data (`NaN`) and require preprocessing before modeling.

## 🧠 Technologies Used

- **Google Colab** (Python 3)
- `pandas`, `numpy` for data manipulation
- `scikit-learn` for modeling and evaluation
- `matplotlib`` for visualization


## 📈 Sample Evaluation Output
from sklearn.model_selection import cross_validate

multiple_cross_scores = cross_validate(
    tree,
    X, y,
    cv=10, 
    scoring=["accuracy", "precision", "recall", "f1"])
print("Cross Validation Accuracy Scores:", multiple_cross_scores["test_accuracy"].round(2))
print("Mean Cross Validation Precision:", round(multiple_cross_scores["test_precision"].mean(),2))
print("Mean Cross Validation Recall:", round(multiple_cross_scores["test_recall"].mean(),2))
print("Mean Cross Validation F1 Score:", round(multiple_cross_scores["test_f1"].mean(),2))

## Output 
Cross Validation Accuracy Scores: [0.85 0.88 0.81 0.87 0.87 0.82 0.72 0.76 0.84 0.79]
Mean Cross Validation Precision: 0.85
Mean Cross Validation Recall: 0.92
Mean Cross Validation F1 Score: 0.88

##🌲 Why Random Forest?
Random Forest was chosen to:
- Handle non-linear relationships
- Reduce variance compared to a single decision tree
- Provide feature importance insights

##▶️ How to Run
- Open the notebook in Google Colab
- Upload the dataset or mount your Google Drive
- Run cells sequentially to:
- Preprocess data
- Train models
- Evaluate performance
- Visualize results

## 📬 Contributions
Feel free to fork, share, or suggest improvements. Collaboration is welcome!

## 📜 License
This project is licensed under the MIT License.

---






# ⛰ Everest Ascents Analysis & Machine Learning

## 📌 Description
This project analyzes a dataset of ascents to Mount Everest, aiming to explore patterns in the data and build a Machine Learning model to predict whether a climber survives or dies in their attempt.

## Table of Contents
1. [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
2. [Data Preprocessing](#data-preprocessing)
3. [Machine Learning Modeling](#machine-learning-modeling)
4. [Results](#results)
5. [Possible Improvements](#possible-improvements)
6. [Repository Structure](#repository-structure)
7. [How to Run](#how-to-run)
8. [Conclusion](#conclusion)

## Exploratory Data Analysis (EDA)
The exploratory analysis included:
- Data cleaning, transformation and breaking down Features.
- Removal of irrelevant columns (`Name`, `Citizenship`, `Season`, `Month`).
- Conversion of categorical variables (`Sex`, `Oxy`, `Dth`, `Host`) into numerical format.
- Graphical analysis of relationships between key variables:
  - Deaths vs. Oxygen usage.
  - Deaths vs. Gender.
  - Deaths vs. Age.
  - Deaths vs. Ascent route (`Host`).

## Data Preprocessing
The following transformations were applied:
- Removal of age outliers (only climbers between 18 and 75 years old).
- Filtering to include only ascents in **May**, due to the low amount of data in other months.
- Application of One-Hot Encoding for `Host`.

## Machine Learning Modeling
To predict the `Dth` variable (death or survival), a classification model was tested:

### Model: Random Forest Classifier
- Trained with an **75%-25% split** of the data.
- Evaluated using metrics such as `accuracy`, `precision`, `recall`, and `f1-score`.
- Identification of the importance of variables in prediction.

## Results
- **Accuracy:** 99.1%
- **Identified Issue:** The model struggles to correctly identify the `Dth = 1` class due to **class imbalance** (many more survivors than fatalities).

## Possible Improvements
To improve death classification in future developments:
- **SMOTE** (Synthetic Minority Over-sampling Technique) to balance the classes.
- **XGBoost** with adjusted `scale_pos_weight` for imbalance handling.
- **Hyperparameter optimization** to enhance accuracy in predicting fatalities.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/everest-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run:
   ```bash
   python EverestAscent.py
   ```

## Conclusion
This project provides a detailed analysis of Everest ascents and an initial classification model to predict fatalities. Future improvements will include techniques to balance the data and test more advanced models.


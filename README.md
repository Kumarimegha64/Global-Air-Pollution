# 🌍 Global Air Pollution Analysis & AQI Prediction

## 📌 Project Overview

This project analyzes global air pollution data to understand air quality patterns across different countries and cities and develops a machine learning model to predict **Air Quality Index (AQI) categories**.

The project combines:

* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature engineering
* Machine learning classification
* Model evaluation
* Model interpretation
* AQI category prediction
* Power BI dashboard development

The main objective is to transform raw air pollution data into meaningful insights and build a reliable machine learning system for AQI category prediction.

---

## 🎯 Business Problem

Air pollution is a major environmental and public health concern. Different pollutants such as **PM2.5, ozone, carbon monoxide (CO), and nitrogen dioxide (NO₂)** contribute to overall air quality.

Organizations and decision-makers need to understand:

* Which pollutants have the greatest influence on air quality?
* How does air quality vary across countries and cities?
* Which AQI categories occur most frequently?
* Can machine learning accurately classify AQI categories?
* Which features are most important for predicting air quality?

This project addresses these questions through data analysis, visualization, machine learning, and dashboard development.

---

## 📊 Dataset

The project uses the **Global Air Pollution Dataset** available on Kaggle.

**Dataset source:** Kaggle – Global Air Pollution Dataset

The dataset contains information about air quality measurements from cities around the world.

### Dataset Size

* **Rows:** 23,463
* **Columns:** 12

### Features

| Feature            | Description                       |
| ------------------ | --------------------------------- |
| Country            | Country where the city is located |
| City               | City name                         |
| AQI Value          | Overall Air Quality Index value   |
| AQI Category       | Overall AQI classification        |
| CO AQI Value       | Carbon Monoxide AQI value         |
| CO AQI Category    | CO pollution category             |
| Ozone AQI Value    | Ozone AQI value                   |
| Ozone AQI Category | Ozone pollution category          |
| NO2 AQI Value      | Nitrogen Dioxide AQI value        |
| NO2 AQI Category   | NO₂ pollution category            |
| PM2.5 AQI Value    | PM2.5 AQI value                   |
| PM2.5 AQI Category | PM2.5 pollution category          |

---

# 🧹 Data Cleaning

The raw dataset was inspected and cleaned before analysis and modeling.

### Initial Data Quality

The dataset initially contained:

* **427 missing values** in the Country column
* **1 missing value** in the City column
* No missing values in the numerical AQI and pollutant columns
* **0 duplicate rows**

The missing and incomplete records were handled during the data-cleaning stage.

The cleaned dataset was then saved for use in subsequent analysis and machine learning notebooks.

---

# 📈 Exploratory Data Analysis

Exploratory Data Analysis was performed to understand the structure and distribution of the data.

The analysis included:

* Numerical feature distributions
* Histograms
* Box plots
* AQI category distribution
* Pollutant analysis
* Correlation analysis
* AQI and pollutant relationships
* Country-level observations

### Key Pollutants Analyzed

The main pollutants considered in the analysis were:

* PM2.5
* Ozone
* Carbon Monoxide (CO)
* Nitrogen Dioxide (NO₂)

The analysis showed that pollutant levels are strongly related to overall air quality, with PM2.5 being particularly important.

---

# ⚙️ Feature Engineering

Feature engineering was performed to prepare the dataset for machine learning.

The process included:

* Selecting relevant numerical features
* Encoding categorical variables
* Preparing the target variable
* Preparing the dataset for model training
* Avoiding unnecessary or redundant variables

Special attention was given to preventing **data leakage**, where information directly related to the target could artificially increase model performance.

---

# 🤖 Machine Learning

This project treats AQI category prediction as a **multi-class classification problem**.

The target variable is:

**AQI Category**

The following models were evaluated:

1. Logistic Regression
2. Random Forest
3. Balanced Random Forest

---

## 📊 Model Performance

### Logistic Regression

**Accuracy: 90.54%**

Logistic Regression provided a strong baseline model but performed worse than the tree-based models.

---

### Random Forest

**Accuracy: 98.55%**

**Macro F1 Score: 89.94%**

Random Forest achieved very high overall accuracy and performed particularly well on the more common AQI categories.

However, its performance on some minority classes, especially **Hazardous** and **Very Unhealthy**, was weaker.

---

### Balanced Random Forest

**Accuracy: 98.32%**

**Macro F1 Score: 92.34%**

The Balanced Random Forest achieved slightly lower overall accuracy than the standard Random Forest but provided better performance across imbalanced classes.

This improvement is especially important for minority AQI categories.

---

## 🏆 Final Model

The **Balanced Random Forest** was selected as the preferred model because it provided a better balance between overall accuracy and performance across different AQI categories.

| Model                  | Accuracy |   Macro F1 |
| ---------------------- | -------: | ---------: |
| Logistic Regression    |   90.54% |          — |
| Random Forest          |   98.55% |     89.94% |
| Balanced Random Forest |   98.32% | **92.34%** |

Although Random Forest achieved the highest accuracy, Balanced Random Forest achieved a higher Macro F1 score.

Therefore, the Balanced Random Forest was considered more suitable when performance across all AQI categories is important.

---

# 🔍 Model Interpretation

Feature importance analysis was performed to understand which variables contributed most to the model's predictions.

### Top Important Features

| Feature         | Importance |
| --------------- | ---------: |
| PM2.5 AQI Value |     0.3073 |
| Ozone AQI Value |     0.0793 |
| CO AQI Value    |     0.0591 |
| Country – India |     0.0391 |
| NO₂ AQI Value   |     0.0380 |

### Main Finding

**PM2.5 AQI Value was the most important feature in the model**, with an importance score of approximately **0.307**.

This indicates that PM2.5 plays a particularly important role in distinguishing between AQI categories within this dataset.

Ozone, CO, and NO₂ also contributed to the model's predictions, while country-level features provided additional information.

---

# 🔮 Prediction System

A prediction system was developed using the trained machine learning model.

The system takes relevant pollution and location features as input and predicts the corresponding AQI category.

Possible AQI categories include:

* Good
* Moderate
* Unhealthy for Sensitive Groups
* Unhealthy
* Very Unhealthy
* Hazardous

The prediction system also allows prediction probabilities to be examined, providing more information than simply returning the predicted category.

---

# 📊 Power BI Dashboard

A Power BI dashboard was created to provide an interactive visual analysis of the global air pollution dataset.

The dashboard helps users explore:

* Overall AQI patterns
* AQI categories
* Pollutant levels
* Country-level air quality
* City-level air quality
* Relationships between pollutants and AQI

The dashboard complements the Python analysis by providing an interactive business intelligence layer.

---

# 📓 Project Notebooks

The project is organized into eight Jupyter notebooks.

| Notebook                        | Description                                                             |
| ------------------------------- | ----------------------------------------------------------------------- |
| `01_data_understanding.ipynb`   | Dataset loading, structure, columns, data types, and initial inspection |
| `02_data_cleaning.ipynb`        | Missing-value handling, cleaning, and preparation                       |
| `03_eda.ipynb`                  | Exploratory data analysis and visualization                             |
| `04_feature_engineering.ipynb`  | Feature preparation and transformation                                  |
| `05_ml_model.ipynb`             | Machine learning model development                                      |
| `06_model_evaluation.ipynb`     | Model performance evaluation                                            |
| `07_model_interpretation.ipynb` | Feature importance and model interpretation                             |
| `08_prediction_system.ipynb`    | AQI category prediction system                                          |

---

# 🗂️ Project Structure

```text
Global Air Pollution Dataset/
│
├── data/
│   ├── raw/
│   │   └── global air pollution dataset.csv
│   │
│   └── processed data/
│       └── clean_air_pollution.csv
│
├── models/
│   └── aqi_category_model.pkl
│
├── Notebook/
│   ├── 01_data_understanding.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_eda.ipynb
│   ├── 04_feature_engineering.ipynb
│   ├── 05_ml_model.ipynb
│   ├── 06_model_evaluation.ipynb
│   ├── 07_model_interpretation.ipynb
│   └── 08_prediction_system.ipynb
│
├── PowerBI/
│   └── Global_Air_Pollution_Dashboard.pbix
│
├── images/
│   └── dashboard.png
│
├── README.md
└── requirements.txt
```

---

# 🛠️ Technologies Used

### Programming & Analysis

* Python
* Pandas
* NumPy

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn
* Random Forest
* Balanced Random Forest
* Logistic Regression

### Model Persistence

* Joblib

### Business Intelligence

* Microsoft Power BI

### Development Environment

* Jupyter Notebook

---

# 🚀 How to Run the Project

## 1. Clone the Repository

Clone this project repository to your local computer.

## 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate the environment.

### Windows

```bash
.venv\Scripts\activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

## 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Navigate to the `Notebook` folder and run the notebooks in numerical order.

Recommended order:

```text
01 → 02 → 03 → 04 → 05 → 06 → 07 → 08
```

---

# 💡 Key Insights

The analysis produced several important findings:

1. **PM2.5 is the most influential feature** in the machine learning model.

2. **Pollutant AQI values are strongly associated with overall AQI categories.**

3. **Random Forest achieved very high classification accuracy**, reaching approximately 98.55%.

4. **Balanced Random Forest improved Macro F1 performance**, making it more effective for handling less frequent AQI categories.

5. **AQI categories are imbalanced**, meaning some categories contain substantially more observations than others.

6. Evaluating only accuracy can hide poor performance on minority classes, so **Macro F1 was also considered when selecting the final model**.

7. Combining **Python analysis, machine learning, and Power BI** provides both predictive and business-oriented perspectives on air quality.

---

# 🎯 Conclusion

This project demonstrates an end-to-end data analytics and machine learning workflow using global air pollution data.

The project begins with raw data understanding and cleaning, followed by exploratory analysis, feature engineering, machine learning, model evaluation, model interpretation, and prediction.

Among the tested models, the Balanced Random Forest provided the best balance between overall performance and minority-class classification, achieving approximately **98.32% accuracy and 92.34% Macro F1**.

The feature importance analysis identified **PM2.5 AQI Value as the strongest predictor** of AQI category in the model.

The Power BI dashboard further transforms the analysis into an interactive format that can help users explore air quality patterns across countries and cities.

Overall, this project demonstrates practical skills in:

**Data Cleaning → EDA → Feature Engineering → Machine Learning → Model Evaluation → Model Interpretation → Prediction → Power BI**

---

# 👩‍💻 Project Author

**Megha**

Data Analyst / Machine Learning Portfolio Project

---

## 📚 Dataset Source

Global Air Pollution Dataset — Kaggle


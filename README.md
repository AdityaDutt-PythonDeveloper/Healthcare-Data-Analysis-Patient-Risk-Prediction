# 🏥 Healthcare Data Analysis & Patient Risk Prediction

An end-to-end Healthcare Data Analytics project that explores patient information, diagnoses, laboratory results, treatment costs and clinical outcomes using Python, SQL, Power BI and Machine Learning.

The project combines data analysis and visualization with an experimental patient outcome prediction application built using Streamlit.

---

## 📌 Project Overview

Healthcare organizations generate large amounts of patient data. Analyzing this information can help identify patterns in patient outcomes, treatment costs, hospital stays and laboratory results.

The objective of this project is to analyze healthcare datasets, extract meaningful insights and experiment with a Machine Learning model to classify patient outcomes.

The project covers data processing, exploratory analysis, feature engineering, dashboard development and application deployment.

## 🎯 Project Objectives

- Analyze patient demographics and healthcare information.
- Explore relationships between diagnoses, treatment costs and patient outcomes.
- Calculate the length of hospital stay for each patient.
- Identify abnormal laboratory results using predefined project thresholds.
- Analyze patient outcomes and high-risk patient segments.
- Build an interactive Power BI dashboard.
- Develop an experimental Logistic Regression classification model.
- Deploy an interactive prediction application using Streamlit.

## 🛠️ Technologies & Tools Used

| Technology | Purpose |
|---|---|
| Python | Data analysis and preprocessing |
| Pandas | Data manipulation and cleaning |
| NumPy | Numerical operations and feature engineering |
| Matplotlib | Data visualization |
| SQL | Database management and analytical queries |
| Power BI | Interactive dashboards and reporting |
| Scikit-learn | Machine Learning |
| Logistic Regression | Patient outcome classification |
| Streamlit | Interactive web application |
| Joblib | Model serialization and loading |
| Google Colab | Python development environment |

## 📊 Dataset Description

The project uses four CSV datasets.

| Dataset | Description |
|---|---|
| patients.csv | Patient information, admission and discharge dates, diagnosis IDs, outcome IDs and treatment costs |
| diagnoses.csv | Diagnosis information and diagnosis categories |
| outcomes.csv | Patient outcome categories |
| labs.csv | Patient laboratory test records and results |

### Dataset Summary

| Dataset | Records |
|---|---:|
| Patients | 200 |
| Diagnoses | 10 |
| Outcomes | 3 |
| Laboratory Records | 200 |

The datasets are combined using common identifiers such as `PatientID`, `DiagnosisID` and `OutcomeID`.

## 🐍 Python Data Analysis

Python is used to process and analyze the healthcare datasets.

### 1. Data Loading and Integration

The four CSV datasets are imported using Pandas.

Patient information is combined with diagnosis and outcome information using merge operations.

### 2. Data Preprocessing

- Converted admission and discharge dates into datetime format.
- Calculated the number of days spent in the hospital.
- Combined outcome categories into a binary classification target for the experimental model.
- Created additional analytical features.

### 3. Feature Engineering

The following features are created:

| Feature | Description |
|---|---|
| LengthOfStay | Number of days between admission and discharge |
| OutcomeEncoded | Binary representation of patient outcomes |
| HighRisk | Rule-based patient indicator |
| AbnormalCount | Number of abnormal laboratory results based on selected thresholds |

### 4. Exploratory Data Analysis

The analysis focuses on understanding:

- Patient outcome distribution.
- Diagnosis-wise patient distribution.
- Treatment cost patterns.
- Hospital stay duration.
- Laboratory abnormalities.
- High-risk patient distribution.

## 🗄️ SQL Analysis

SQL is included as part of the healthcare analytics workflow.

The intended analytical areas include:

- Retrieving patient details along with diagnoses and outcomes.
- Aggregating patient counts by diagnosis.
- Identifying patient segments using age and outcome conditions.
- Retrieving patient laboratory history.

SQL query scripts can be found in the `sql/` directory.

## 📈 Power BI Dashboard

An interactive Power BI dashboard was developed to present healthcare insights in a visual format.

### Key Performance Indicators

- Total Patients
- Average Treatment Cost
- Average Hospital Stay

### Dashboard Visualizations

- Patient outcome distribution.
- Monthly patient trends.
- Treatment cost by diagnosis.
- Relationship between treatment cost and hospital stay.

The dashboard helps explore healthcare data and understand patterns across different patient groups.

### Dashboard Preview

Add your dashboard screenshot here:

![Healthcare Power BI Dashboard](screenshots/powerbi_dashboard.png)

## 🤖 Machine Learning – Patient Outcome Prediction

An experimental Logistic Regression model was developed using Scikit-learn.

### Prediction Objective

The model attempts to classify patient outcomes into two categories:

| Class | Outcome |
|---|---|
| 0 | Recovered |
| 1 | Complicated / Deceased |

### Features Used

The current model uses four input features:

1. Age
2. Length of Stay
3. Abnormal Lab Count
4. Treatment Cost

### Model Development Workflow

1. Prepared the feature and target variables.
2. Split the dataset into training and testing sets.
3. Trained a Logistic Regression model.
4. Generated predictions.
5. Evaluated model performance using a classification report.
6. Examined the ROC curve.
7. Saved the trained model using Joblib.

### Model Evaluation

The initial notebook reported approximately 70% accuracy.

However, this result should be interpreted cautiously because the original outcome encoding contains a spelling mismatch for the `Deceased` category, which affects target-label preparation.

The model requires corrected labels, proper missing-target handling and further evaluation before its performance can be considered reliable.

The dataset also contains only 200 patient records, limiting the strength and generalizability of predictive conclusions.

## 🌐 Streamlit Application

The trained Logistic Regression model was integrated into an interactive Streamlit application.

### Application Features

- Patient age input.
- Hospital stay duration input.
- Abnormal laboratory count input.
- Treatment cost input.
- Patient outcome prediction.
- Prediction probability visualization.

### Application Preview

Add your application screenshots here:

![Streamlit Application](screenshots/streamlit_home.png)

![Streamlit Prediction](screenshots/streamlit_prediction.png)

### How the Application Works

1. The user enters patient information.
2. The application prepares the input features.
3. The saved Machine Learning model generates a prediction.
4. The application displays the predicted outcome category.
5. Prediction probabilities are visualized using a bar chart.

## 🚀 Installation and Execution

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/Healthcare-Data-Analysis-and-Risk-Prediction.git
```

### 2. Navigate to the Project Directory

```bash
cd Healthcare-Data-Analysis-and-Risk-Prediction
```

### 3. Install Dependencies

```bash
pip install pandas numpy matplotlib scikit-learn streamlit joblib
```

### 4. Run the Streamlit Application

```bash
cd streamlit_app
streamlit run app.py
```

The application will open in your browser.

**Note:** The trained model file must be available at the path expected by `app.py`. The application and model should be kept compatible with the preprocessing and feature definitions used during training.

## ⚠️ Limitations and Future Improvements

This project is an educational analytics project and has several limitations.

### Current Limitations

- The dataset contains only 200 patient records.
- The initial Machine Learning model requires corrected target-label preparation.
- Some laboratory tests are not included in the current abnormal-count calculation.
- Laboratory reference thresholds require further validation.
- Predictive performance requires more rigorous evaluation.

### Future Improvements

- Expand the dataset with more representative records.
- Improve data validation and preprocessing.
- Compare Logistic Regression with Decision Tree and Random Forest.
- Apply cross-validation.
- Evaluate precision, recall, F1-score, ROC-AUC and PR-AUC.
- Improve Power BI dashboard interactivity.
- Add more laboratory parameters.
- Improve model explainability.
- Enhance Streamlit application functionality.

## ⚠️ Disclaimer

This project is developed for educational and analytical purposes only.

The Machine Learning model is experimental and has not been clinically validated. Its predictions must not be used for medical diagnosis, patient treatment or real-world clinical decision-making.

## 👨‍💻 Author

**Aditya Dutt**

B.Tech – Computer Science & Engineering (Artificial Intelligence & Machine Learning)

Interested in Data Analytics, Business Intelligence, Machine Learning and Business Analysis.

---

⭐ If you find this project interesting, feel free to explore the repository!

# 🏥 Healthcare Appointment No-Show Prediction & Analysis

## 🔍 Overview

This project focuses on analyzing and predicting **no-shows in healthcare appointments**—a widespread problem in public health systems that causes inefficient use of medical resources and delays for other patients. To address this, we’ve developed a complete data science pipeline involving:

- 📊 **Exploratory Data Analysis (EDA)** to discover trends and patterns in patient behavior.
- 🤖 **Machine Learning (ML) models** to predict the likelihood of no-show events.
- 📈 **Power BI Dashboard** to provide an interactive and visual summary of patient behavior trends and key risk factors for no-shows.

### 🎯 Objectives

The primary goals of this project are:

- To understand **demographic**, **behavioral**, and **medical** factors that contribute to patients missing scheduled medical appointments.
- To explore the **effectiveness of SMS reminders** and other hospital interventions.
- To build accurate **classification models** that can predict whether a patient will attend their appointment.
- To develop a **dashboard** that enables healthcare administrators to make **data-driven decisions** to reduce no-shows and improve service delivery.

### 📦 Dataset Description

The dataset used is the **“Medical Appointment No Shows” dataset** from Kaggle, containing **110,527 appointment records** collected from a public hospital system in **Brazil**. Each row represents a patient appointment and includes the following key attributes:

| Feature               | Description                                                                 |
|-----------------------|-----------------------------------------------------------------------------|
| `PatientId`           | Unique identifier for the patient                                           |
| `AppointmentID`       | Unique identifier for the appointment                                       |
| `Gender`              | Patient gender (`M` or `F`)                                                 |
| `ScheduledDay`        | Timestamp when the appointment was scheduled                                |
| `AppointmentDay`      | Date of the actual appointment                                               |
| `Age`                 | Patient’s age                                                               |
| `Neighbourhood`       | Location of the hospital                                                    |
| `Scholarship`         | Indicates if the patient is enrolled in a social welfare program (1 = Yes)  |
| `Hipertension`        | Whether the patient has hypertension (1 = Yes)                              |
| `Diabetes`            | Whether the patient has diabetes (1 = Yes)                                  |
| `Alcoholism`          | Whether the patient has alcoholism (1 = Yes)                                |
| `Handcap`            | Whether the patient has any disability (0–4 scale)                          |
| `SMS_received`        | Whether the patient received a reminder SMS (1 = Yes)                       |
| `No-show`             | Target variable — indicates if the patient missed the appointment (Yes/No)  |

From this dataset, additional features such as **waiting time** (difference between scheduled and appointment date) and **day of the week** were engineered to uncover deeper insights.

This dataset provides a comprehensive foundation for analyzing patient behavior and improving appointment management systems using data science.

---

## 📁 Repository Contents

| File Name                                                | Description                                                                 |
| -------------------------------------------------------- | --------------------------------------------------------------------------- |
| `Healthcare_Appointment_No_Show_Prediction_EDA.ipynb`    | Jupyter notebook containing detailed exploratory data analysis and visuals |
| `Healthcare_Appointment_No_Show_Prediction_ML.ipynb`     | Notebook with ML models and performance evaluation (cleaned data used)     |
| `KaggleV2-May-2016.csv`                                  | Original dataset obtained from Kaggle                                       |
| `Healthcare_Dashboard.pbix`                              | Power BI dashboard file with filters, KPIs, and interactive visuals         |
| `README.md`                                              | Documentation file for this project workflow                                |

---

## 🛠️ Tools Used

* **Python (Pandas, Seaborn, Matplotlib, Scikit-learn)**
* **Jupyter Notebooks (Google Colab or Local Jupyter)**
* **Power BI Desktop**

---

## ✅ Step-by-Step Procedure

### 🔹 Step 1: Exploratory Data Analysis (EDA)

📄 File: `Healthcare_Appointment_No_Show_Prediction_EDA.ipynb`

* Imported and cleaned the dataset.
* Created new features like `WaitingTimeDays` (AppointmentDate - ScheduledDate).
* Visualizations performed:
  - **AgeGroup vs No-show count**
  - **Gender vs No-show count**
  - **DayOfWeek vs No-show rate**
  - **SMS_received vs No-show**
  - **WaitingTimeDays vs No-show rate**
  - **Neighbourhood vs No-show count**
* Key findings:
  - Patients with **longer waiting times** tend to miss more.
  - **SMS reminders** significantly reduce no-shows.
  - No-show rates vary slightly by **weekdays**.
  - Younger age groups (<19) tend to miss more appointments.

---

### 🔹 Step 2: Machine Learning Modeling

📄 File: `Healthcare_Appointment_No_Show_Prediction_ML.ipynb`

* Data preprocessing:
  - One-hot encoding of categorical features.
  - Standardization of numerical features.
* ML Models trained:
  - **Logistic Regression**
  - **Random Forest**
  - **XGBoost**
* Evaluation Metrics:
  - Accuracy, Precision, Recall, F1-score
  - Confusion Matrix
  - ROC Curve
* Best performing model:
  - Random Forest achieved the highest F1-score and recall.
* Feature importance was visualized to highlight top predictors:
  - `WaitingTimeDays`, `Age`, `SMS_received`, and `Scholarship` had significant influence.

---

### 🔹 Step 3: Power BI Dashboard Creation

📦 File: `Healthcare_Dashboard.pbix`

* Imported raw CSV file into Power BI.
* Created interactive visuals:
  - **KPI Cards**: Total Appointments, No-show Rate, Average Waiting Time
  - **Bar Charts**: AgeGroup vs No-show, Gender vs No-show
  - **Pie Chart**: SMS_received vs No-show
  - **Heatmap**: DayOfWeek vs No-show rate
  - **Line Plot**: WaitingTimeDays vs No-show rate
  - **Filters**: Gender, AgeGroup, SMS, ChronicCondition, AppointmentDay
* Dashboard provides instant filtering and insights to hospital administrators.

---

## 📌 Key Insights

* 🚫 **20.19%** of patients did not show up for appointments.
* 📲 Receiving an **SMS reminder** improved show-up rates.
* 🕒 Patients with **long waiting times** are less likely to attend.
* 👶 Younger patients (<19) and certain neighborhoods are more likely to no-show.
* 💡 Predictive modeling can proactively **identify at-risk patients**.

---

## 📈 ML Model Performance Snapshot

| Model               | Accuracy | Precision | Recall | F1-Score |
|--------------------|----------|-----------|--------|----------|
| Logistic Regression| 0.79     | 0.43      | 0.0311 | 0.0581   |
| Random Forest      | 0.80     | 0.53      | 0.11   | 0.19     |
| XGBoost            | 0.80     | 0.62      | 0.073  | 0.13     |




---

## 🖥️ How to Reproduce the Project

Follow these steps to run this project locally:

### 🔹 Step 1: Clone the Repository

```bash
git clone https://github.com/Harshita-bioinfo/Healthcare-NoShow-Prediction.git
cd Healthcare-NoShow-Prediction
```

### 🔹 Step 2: Launch Notebooks

```bash
jupyter notebook Healthcare_Appointment_No_Show_Prediction_EDA.ipynb
jupyter notebook Healthcare_Appointment_No_Show_Prediction_ML.ipynb
```

### 🔹 Step 3: Explore Power BI Dashboard

Open `Healthcare_Dashboard.pbix` in **Power BI Desktop** to interact with the dashboard.

---



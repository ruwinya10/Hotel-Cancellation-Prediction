
# 🏨 Hotel Booking Cancellation Prediction System

### Predicting Hotel Booking Cancellations Using Machine Learning

**IT3051 – Fundamentals of Data Mining | Mini Project 2026**

**Team:** Data Frontier  
**Institution:** Sri Lanka Institute of Information Technology (SLIIT)  
**Specialization:** BSc (Hons) in Information Technology – Data Science

---

## 📌 Project Overview

Hotel booking cancellations create significant challenges for the hospitality industry, including revenue loss, unoccupied rooms, and inefficient resource allocation.

The **Hotel Booking Cancellation Prediction System** is a machine learning-based application designed to predict whether a hotel reservation is likely to be cancelled based on booking information and historical customer behavior.

The system uses data mining techniques to identify cancellation patterns and provides predictions through an interactive web application.

By identifying potentially risky reservations in advance, the system helps hotel management make informed decisions regarding room allocation, reservation planning, and customer management.

---

## 🎯 Project Objectives

- Analyze historical hotel booking data to identify cancellation patterns.
- Perform exploratory data analysis (EDA) to discover important relationships.
- Clean and preprocess data to improve model performance.
- Develop and compare multiple machine learning classification algorithms.
- Optimize models through hyperparameter tuning.
- Select the best-performing model for cancellation prediction.
- Develop a web application for real-time predictions.
- Support data-driven decision-making in hotel operations.

---

## 📊 Dataset Information

**Dataset:** Hotel Booking Demand Dataset

**Source:** Kaggle

🔗 [Hotel Booking Demand Dataset](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand)

| Attribute | Description |
|-----------|-------------|
| Total Records | 119,390 |
| Total Variables | 32 |
| Hotel Types | City Hotel, Resort Hotel |
| Time Period | July 2015 – August 2017 |
| Target Variable | `is_canceled` |
| Problem Type | Binary Classification |

### Target Variable

- `0` – Booking Not Cancelled
- `1` – Booking Cancelled

### Important Features

- Hotel Type
- Lead Time
- Arrival Date
- Length of Stay
- Number of Guests
- Meal Type
- Market Segment
- Distribution Channel
- Deposit Type
- Previous Cancellations
- Booking Changes
- Customer Type
- Average Daily Rate (ADR)
- Special Requests

---

## 🔍 Data Mining Workflow

The project follows a complete machine learning workflow:

1. **Data Collection** – Obtain the Hotel Booking Demand dataset.
2. **Data Understanding** – Explore dataset characteristics and relationships.
3. **Exploratory Data Analysis** – Analyze distributions, missing values, outliers, and cancellation patterns.
4. **Data Preprocessing** – Handle missing values, duplicates, invalid records, and categorical variables.
5. **Feature Engineering** – Prepare relevant features for model training.
6. **Model Development** – Train four classification algorithms.
7. **Model Evaluation** – Compare models using multiple performance metrics.
8. **Model Optimization** – Perform hyperparameter tuning.
9. **Final Model Selection** – Select the best-performing model.
10. **System Development** – Integrate the model with a web application.

---

## 🧹 Data Preprocessing

Several preprocessing techniques were investigated to improve data quality and model reliability.

### Missing Value Handling

The original dataset contains missing values in:

- `company`
- `agent`
- `country`
- `children`

### Duplicate Records

The dataset contains approximately 31,994 exact duplicate records, requiring consideration during data preparation.

### Outlier Detection

Unusual values were identified in numerical features such as Average Daily Rate (`adr`).

### Categorical Encoding

Categorical features were transformed into machine-readable representations.

### Data Leakage Prevention

Features that directly reveal the final booking outcome, such as `reservation_status` and `reservation_status_date`, were excluded from predictive modeling.

### Feature Preparation

Relevant numerical and categorical booking characteristics were prepared for machine learning algorithms.

---

## 🤖 Machine Learning Models

Four supervised machine learning algorithms were implemented and compared.

### 1. Logistic Regression

A statistical classification algorithm used as a baseline for predicting booking cancellations.

### 2. Decision Tree

A tree-based classification algorithm that learns decision rules from booking characteristics.

### 3. Random Forest

An ensemble learning algorithm that combines multiple decision trees to improve prediction reliability.

### 4. XGBoost (Extreme Gradient Boosting)

An advanced gradient boosting algorithm that combines sequential decision trees to produce accurate predictions.

---

## 📈 Model Performance Comparison

### Baseline Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 73.53% | 51.00% | 78.13% | 61.71% | 82.82% |
| Decision Tree | 78.77% | 61.19% | 60.86% | 61.02% | 73.22% |
| Random Forest | 84.03% | 76.06% | 60.61% | 67.46% | 89.67% |
| XGBoost | 81.19% | 61.32% | 84.29% | 70.99% | 90.70% |

### Optimized Model Performance

| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
|-------|----------|-----------|--------|----------|---------|
| Logistic Regression | 73.53% | 51.00% | 78.13% | 61.71% | 83.16% |
| Decision Tree | 76.68% | 54.94% | 81.18% | 65.53% | 86.50% |
| Random Forest | 83.25% | 67.27% | 75.28% | 71.05% | 90.01% |
| XGBoost | 82.62% | 64.21% | 82.13% | 72.07% | 90.95% |

### 🏆 Final Selected Model – XGBoost

XGBoost was selected as the final prediction model because it demonstrated the strongest overall balance between cancellation detection and classification performance.

**Final XGBoost Performance:**

- **Accuracy:** 82.62%
- **Precision:** 64.21%
- **Recall:** 82.13%
- **F1-Score:** 72.07%
- **ROC-AUC:** 90.95%

The model achieved strong recall and ROC-AUC performance, making it suitable for identifying potentially risky hotel reservations.

---

## 💻 System Architecture

The application follows a frontend-backend machine learning architecture.

**Frontend (React.js)**  
↓  
**REST API (FastAPI)**  
↓  
**Data Validation and Preprocessing**  
↓  
**Trained XGBoost Model**  
↓  
**Cancellation Prediction**  
↓  
**Prediction Result Display**

### Frontend

The frontend provides a user-friendly interface where users can enter hotel reservation details and receive cancellation predictions.

### Backend

The backend is developed using FastAPI and is responsible for:

- Receiving booking information.
- Validating user inputs.
- Applying required preprocessing.
- Loading the trained machine learning model.
- Generating cancellation predictions.
- Returning prediction results to the frontend.

---

## ✨ System Features

### Interactive Booking Input

The system provides a seven-step booking information form:

1. **Hotel & Dates** – Hotel type and arrival information.
2. **Stay Details** – Weekend nights, weekday nights, and lead time.
3. **Guests** – Number of adults, children, and babies.
4. **Room & Meal** – Reserved room type and meal plan.
5. **Booking Information** – Market segment, distribution channel, deposit type, and customer type.
6. **Guest History** – Previous cancellations, previous bookings, and booking changes.
7. **Pricing & Extras** – Daily rate, waiting list, parking requirements, and special requests.

### Cancellation Prediction

After entering the required information, users can generate a prediction indicating whether the reservation is likely to be cancelled.

### Decision Support

The prediction results can assist hotel management in:

- Identifying high-risk reservations.
- Improving occupancy planning.
- Prioritizing customer follow-ups.
- Managing booking uncertainty.
- Supporting revenue management decisions.

---

## 🛠️ Technologies Used

### Programming & Machine Learning
- Python
- Pandas
- NumPy
- Scikit-learn
- XGBoost
- Jupyter Notebook

### Backend
- FastAPI
- Python
- REST API

### Frontend
- React.js
- JavaScript
- HTML
- CSS

### Development Tools
- Visual Studio Code
- Jupyter Notebook
- Git
- GitHub

---

## 📁 Project Structure

The data mining component includes the following files and directories:

```text
FDM Project/
│
├── Models/
│   ├── Decision_Tree.ipynb
│   ├── Logistic_Regression.ipynb
│   ├── Random_Forest.ipynb
│   └── XG_Boost.ipynb
│
├── outputs/
│   ├── hotel_bookings_cleaned.csv
│   ├── X_train.csv
│   ├── X_test.csv
│   ├── y_train.csv
│   └── y_test.csv
│
├── sourse dataset/
│   └── hotel_bookings.csv
│
├── Stage3_Data_Understanding_and_EDA.ipynb
│
└── Stage4_Data_Preprocessing_and_Feature_Engineering.ipynb
```

The complete prediction application additionally includes React frontend and FastAPI backend components.

---

## 🚀 How the System Works

1. The user opens the hotel booking prediction application.
2. The user enters the required reservation details.
3. The frontend sends booking information to the FastAPI backend.
4. The backend validates and preprocesses the input.
5. The trained XGBoost model analyzes the booking information.
6. The system generates a cancellation prediction.
7. The prediction result is displayed through the frontend.

---

## 📌 Key Findings

The analysis identified several booking characteristics associated with cancellation behavior:

- Booking lead time
- Hotel type
- Previous cancellation history
- Deposit type
- Customer and booking characteristics
- Special requests
- Length and type of stay
- Booking modifications

The results indicate that cancellation behavior depends on multiple booking-related factors rather than a single characteristic.

---

## 📉 Business Impact

The system aims to support hotel operations through:

- **Improved Occupancy Planning:** Identify reservations with higher cancellation risk.
- **Revenue Protection:** Support strategies to reduce potential revenue losses.
- **Proactive Customer Management:** Prioritize appropriate follow-ups.
- **Operational Efficiency:** Improve room and resource allocation.
- **Data-Driven Decisions:** Use historical booking patterns to support management decisions.

---

## 📚 References

Antonio, N., de Almeida, A., & Nunes, L. (2019). *Hotel booking demand datasets*. Data in Brief, 22, 41–49.

https://doi.org/10.1016/j.dib.2018.11.126

Dataset available at:

https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand

---

## 📄 License

This project was developed for academic and educational purposes as part of the IT3051 – Fundamentals of Data Mining module at SLIIT.

The original dataset is distributed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.

---

⭐ **Developed by Team Data Frontier | SLIIT | 2026**

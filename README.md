# Optimizing Hotel Revenue Through Booking Cancellation Prediction

## Project Overview

This project analyzes a hotel booking dataset to identify key factors predicting cancellations and builds a **machine learning model** (Random Forest Classifier) to forecast potential revenue loss. The goal is to provide hotels with a data-driven tool to proactively manage cancellations and optimize revenue streams.

---

## Objectives

The main objectives of this project were to:

* Clean and preprocess the hotel booking dataset for analysis.
* Perform Exploratory Data Analysis (EDA) to identify features strongly correlated with cancellations.
* Build and train a machine learning model to predict the likelihood of a booking cancellation.
* Evaluate the model's performance using metrics like accuracy, precision, and recall.
* Provide actionable recommendations for hotels to reduce cancellations.

---

## Problem Statement

Hotel booking cancellations significantly impact revenue and operational efficiency. Last-minute cancellations often result in unsold rooms and lost income. This project addresses the challenge by identifying high-risk bookings, enabling hotels to implement targeted strategies like optimized overbooking, incentive offers, and proactive customer engagement to mitigate revenue loss.

---

## Dataset Information

The analysis used a dataset containing **119,390 booking records** for a city hotel and a resort hotel, encompassing **32 features**.

| Feature Category    | Key Fields Used                                                                      |
| :------------------ | :----------------------------------------------------------------------------------- |
| Booking Details     | `hotel` (type), `lead_time`, `arrival_date` details, `stays_in_nights`, `adr`        |
| Guest Information   | `adults`, `children`, `babies`, `country`, `is_repeated_guest`                         |
| Transaction Details | `meal`, `market_segment`, `distribution_channel`, `deposit_type`, `previous_cancellations` |
| Target Variable     | `is_canceled` (1 if canceled, 0 if not)                                              |

**Data Cleaning:** Preprocessing involved handling missing values (imputing `company`, `agent`, `country`, `children`), converting data types, removing invalid bookings (zero guests), feature engineering (`total_stay`, `total_people`), and removing outliers in `adr` (> 5000).

---

## Technology Stack

| Component                  | Tool / Language               |
| :------------------------- | :---------------------------- |
| Data Cleaning & Processing | Python (Pandas, NumPy)        |
| Data Analysis & EDA        | Python (Matplotlib, Seaborn)  |
| Machine Learning           | Python (Scikit-learn)         |
| Environment                | Jupyter Notebook              |
| Documentation              | Markdown (README), Word       |

---

## Exploratory Data Analysis (EDA) - Key Insights

* **Hotel Type Impact:** **City hotels** experience significantly higher cancellation rates (**41.7%**) compared to **resort hotels** (**27.8%**).
* **Lead Time:** Longer lead times strongly correlate with increased cancellation likelihood.
* **Price Sensitivity (ADR):** Higher Average Daily Rates (ADR) are associated with more cancellations, particularly in resort hotels.
* **Previous Cancellations:** Guests with a history of cancellations are far more likely to cancel again.
* **Deposit Type:** Surprisingly, **"Non-Refundable"** deposits have the highest cancellation rates, potentially due to inflexibility. "No Deposit" bookings also show significant cancellations.
* **Guest Loyalty:** **Repeated guests** have a drastically lower cancellation rate.

---

## Model Building & Evaluation

* **Model Chosen:** **Random Forest Classifier** (selected for robustness and performance).
* **Preprocessing:** Categorical features were one-hot encoded. Data was split into 80% training and 20% testing sets.
* **Performance Metrics:**
    * **Accuracy:** **87.2%** (Correctly predicted cancellation status in over 87% of test cases).
    * **Precision:** High precision indicated a low rate of false positives.
    * **Recall:** Strong recall demonstrated the model's ability to identify a high percentage of actual cancellations.

---

## Recommendations

Based on the analysis and model findings:

1.  **Dynamic Deposits:** Implement small, non-refundable deposits for bookings with long lead times to reduce speculative reservations.
2.  **Reward Loyalty:** Offer flexible cancellation policies or discounts to repeat guests to further secure their bookings.
3.  **Target City Hotel Bookings:** Use proactive communication (reminders, upgrade offers) for city hotel bookings due to their higher cancellation risk.
4.  **Review Non-Refundable Policy:** Consider offering future stay credits instead of complete forfeiture for non-refundable cancellations to potentially improve customer sentiment.
5.  **Leverage Predictive Model:** Integrate the model to flag high-risk bookings, enabling targeted interventions like strategic overbooking or confirmation calls.

---

## Conclusion

This project successfully identified key drivers of hotel booking cancellations and developed a high-accuracy (87%) predictive model using a Random Forest Classifier. The findings and the model provide hotels with valuable tools to anticipate cancellations, manage revenue risk effectively, and implement data-driven retention strategies.

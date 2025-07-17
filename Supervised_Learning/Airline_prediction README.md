# ✈️ Airline Passenger Satisfaction Prediction – Summary & Analytical Insights

---

## 📌 Project Objective

To develop a robust data-driven predictive model that accurately classifies airline passengers as **“Satisfied”** or **“Neutral/Dissatisfied”**, 
based on their demographic, travel, and in-flight experience data.  
The solution is intended to help airlines make data-informed decisions—leveraging insights to improve customer satisfaction, reduce churn, and optimize service delivery.

---

## 📊 Dataset Overview

- **Total Records**: 129,880
- **Features**: 24 columns, including:
  - **Demographics**: Age, Gender, Customer Type  
  - **Flight Details**: Type of Travel, Class, Flight Distance  
  - **Service Ratings** (scale 0–5): Inflight Wifi, Food, Cleanliness, Leg Room, etc.  
  - **Operational Metrics**: Arrival/Departure Delays  
- **Target Variable**: `Satisfaction` (binary:  
  - 1 = Satisfied  
  - 0 = Neutral or Dissatisfied)

---

## 🧪 Methodology & Analytical Approach

### 1. Data Preprocessing
- Merged train and test sets to streamline cleaning  
- Dropped irrelevant columns (`Unnamed: 0`)  
- Imputed 393 missing values in `Arrival Delay in Minutes` using mean strategy  
- Encoded categorical variables using one-hot encoding  
- Transformed `Satisfaction` variable to binary (0 = Neutral/Dissatisfied, 1 = Satisfied)

### 2. Exploratory Data Analysis (EDA)
- **Satisfaction Distribution**:
  - ✅ 43.45% Satisfied  
  - ❌ 56.55% Neutral/Dissatisfied  

- **Top Correlated Features**:
  - Online Boarding (r ≈ 0.44)  
  - Inflight Entertainment (r ≈ 0.43)  
  - Seat Comfort (r ≈ 0.42)  
  - Wifi Service, Leg Room, Cleanliness, Check-in Service

### 3. Model Training & Evaluation

| Model               | Accuracy | Precision (D/S) | Recall (D/S) | F1-Score      |
|---------------------|----------|------------------|--------------|---------------|
| Logistic Regression | 81.26%   | 0.86 / 0.66       | 0.56 / 0.91  | 0.68 / 0.76   |
| Decision Tree       | 95.02%   | 0.95 / 0.96       | 0.97 / 0.93  | 0.96 / 0.94   |
| **Random Forest**   | **96.23%** | **0.96 / 0.97** | **0.98 / 0.94** | **0.97 / 0.95** |

🏆 **Best Model**: Random Forest Classifier  
- Delivered the most balanced performance across all metrics  
- Achieved exceptionally low error rates, indicating strong generalization on unseen data

---

## 🔍 Confusion Matrix (Random Forest Classifier)

| Actual \ Predicted | Dissatisfied | Satisfied |
|--------------------|--------------|-----------|
| Dissatisfied        | 14,490       | 325       |
| Satisfied           | 655          | 10,506    |

- ✔️ Low false positives/negatives  
- ✔️ High sensitivity and specificity  

---

## 💡 Key Business Insights

1. **Service Quality is the Main Driver of Satisfaction**  
   - Top features:  
     - Inflight Wifi, Entertainment, Seat Comfort  
     - Online Boarding, Legroom, Cleanliness  

2. **Operational Efficiency Matters**  
   - Long flight distances and delays correlate negatively with satisfaction

3. **Dissatisfaction is Widespread**  
   - Over 56% of passengers were not satisfied, signaling a need for urgent improvements

---

## 🚀 Strategic Recommendations

| Area                   | Action                                                                 |
|------------------------|------------------------------------------------------------------------|
| ✈️ Inflight Experience | Invest in wifi infrastructure; upgrade entertainment and comfort       |
| 📲 Boarding & Check-in | Digitize and streamline boarding to reduce stress and delays           |
| 🧼 Cleanliness         | Enhance cabin and restroom hygiene protocols                           |
| 🧠 Data Utilization    | Use model outputs to proactively identify and retain at-risk customers |

---

## 🛠️ Future Work & Deployment Path

- To deploy the Random Forest model in a real-time feedback system (e.g., web dashboard)
- To monitor live satisfaction trends across routes, classes, or customer types
- To integrate NLP to analyze open-ended passenger feedback and extract sentiment patterns

---

## 📈 Conclusion

This project demonstrates the power and value of machine learning in transforming the airline customer experience. 
By identifying the most influential predictors of satisfaction, airline operators can:
- Optimize service delivery
- Personalize experiences
- Boost customer loyalty

The Random Forest model, with 96% accuracy, offers a scalable and interpretable solution for real-world deployment, enabling **data-informed strategic decision-making**.

---

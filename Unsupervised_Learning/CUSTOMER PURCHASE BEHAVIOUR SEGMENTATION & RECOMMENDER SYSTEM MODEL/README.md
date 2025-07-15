# 🛒 Customer Purchase Behavior Segmentation & Recommender System  
## 🧠 Unsupervised Machine Learning with Clustering

This project applies unsupervised learning techniques to segment customers based on their purchasing behavior and builds a basic recommender logic around those segments. 
It aims to help businesses personalize marketing strategies, optimize offers, and enhance customer experience.

---

## 📌 Project Objectives

- Segment customers into distinct groups based on purchasing patterns.
- Derive actionable insights from customer clusters.
- Create a basic recommender logic that aligns with cluster characteristics.
- Apply and evaluate unsupervised machine learning using KMeans clustering.

---

## 📊 Dataset Overview

The dataset includes key features such as:
- `CustomerID`
- `Gender`
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`

These are used to understand customer profiles and uncover patterns in purchasing behavior, and also applying feature engineering techniques.

---

## 🧪 Methodology & Approach

### 1. **Problem Understanding**
   - Identify business goals: Understand different types of customers and tailor offerings accordingly.

### 2. **Data Preparation**
   - Load the dataset, check for missing values, and clean where necessary.
   - Encode categorical features if applicable (e.g., Gender).

### 3. **Exploratory Data Analysis (EDA)**
   - Visualize feature distributions to understand patterns in income, age, and spending.
   - Plot pairwise relationships between features to detect clustering tendencies.

### 4. **Feature Engineering**
   - Construct new features if needed (e.g., Age groups).
   - Normalize features to prepare for clustering (using MinMaxScaler).

### 5. **Clustering with KMeans**
   - Use the **Elbow Method** to identify the optimal number of clusters.
   - Apply `KMeans` clustering to segment customers.
   - Assign cluster labels back to the original dataset.

### 6. **Cluster Analysis & Interpretation**
   - Visualize clusters using scatter plots and 3D plots (Plotly).
   - Analyze each cluster's characteristics — spending level, income bracket, etc.

### 7. **Recommendation Logic**
   - Based on segment behavior, recommend potential marketing or product strategies.
   - Highlight which clusters represent high-value customers or upselling opportunities.

---

## 🧰 Tools & Technologies

- **Python** (Jupyter Notebook)
- **Pandas, NumPy** – Data preprocessing & analysis
- **Matplotlib, Seaborn** – Data visualization & EDA
- **Scikit-learn** – Clustering (KMeans), preprocessing
- **Plotly** – Interactive visualizations

---

## 🔍 Workflow Summary

1. **Data Cleaning:** Checked for missing values and ensured feature consistency.
2. **EDA:** Explored income, age, and spending distributions to uncover trends.
3. **Feature Scaling:** Applied `MinMaxScaler` for effective clustering.
4. **Modeling:** Used the Elbow Method and `KMeans` to cluster the data.
5. **Visualization:** Plotted 2D/3D cluster maps to show customer groupings.
6. **Recommendation Strategy:** Suggested actions for each segment based on behavior.

---

## 📈 Key Results

- Discovered **3 to 5 distinct customer clusters** with clear spending and income behavior differences.
- Built intuitive visualizations to aid business stakeholders in decision-making.
- Demonstrated how simple clustering can provide strong foundations for targeted campaigns.

---

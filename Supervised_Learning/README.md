# 📝 Customer Sentiment Analysis & Prediction  
### 🔍 Using Supervised Machine Learning and Natural Language Processing (NLP)

This repository contains a sentiment analysis model built with supervised machine learning techniques and NLP. 
It classifies customer reviews as **positive** or **negative**, using vectorized text data and multiple classification models.

---

## 📑 Table of Contents

- [📌 Introduction](#-introduction)  
- [🧠 Methodology and Approach](#-methodology-and-approach)  
- [📁 Data Source](#-data-source)  
- [🔍 Data Exploration](#-data-loading-and-initial-exploration)  
- [🧹 Data Cleaning and Preprocessing](#-data-cleaning-and-preprocessing)  
- [📊 Feature Engineering (TF-IDF)](#-feature-engineering-tf-idf)  
- [⚙️ Model Training](#-model-training)  
- [📈 Model Evaluation](#-model-evaluation)  
- [💻 Installation](#-installation)  
- [🚀 Usage](#-usage)  
- [📊 Results](#-results)  
- [🤝 Contributing](#-contributing)  
- [🛡️ License](#-license)  

---

## 📌 Introduction

Sentiment analysis is essential for businesses to interpret customer feedback and improve products and services. 
This project builds a robust classifier that predicts the **sentiment polarity** of movie reviews using machine learning and NLP techniques.

---

## 🧠 Methodology and Approach

The workflow includes:
1. Loading and inspecting data  
2. Cleaning and preprocessing text  
3. Converting text to numerical vectors using TF-IDF  
4. Training multiple classifiers  
5. Evaluating models using precision, recall, accuracy, and F1-score

---

## 📁 Data Source

- **Dataset**: [`IMDB Dataset.csv`](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)  
- **Contents**: 50,000 movie reviews labeled as either **positive** or **negative**

---

## 🔍 Data Loading and Initial Exploration

- Loaded dataset into a Pandas DataFrame  
- Checked for missing values: none found  
- Removed 418 duplicate rows  
- Verified balanced class distribution (~50% positive, 50% negative)

---

## 🧹 Data Cleaning and Preprocessing

- **Word Counts**: Added original and cleaned word counts  
- **Label Encoding**: Converted `positive` → 0 and `negative` → 1  
- **Contraction Expansion**: Converted words like “don’t” → “do not”  
- **Text Cleaning Pipeline**:
  - Removed HTML tags  
  - Lowercased text  
  - Tokenized sentences  
  - Removed stopwords  
  - Applied stemming using NLTK

---

## 📊 Feature Engineering (TF-IDF)

TF-IDF (Term Frequency–Inverse Document Frequency) was used to convert text into weighted numerical features that capture term importance.

### 💡 Why TF-IDF?

- Reduces noise from common words  
- Emphasizes distinctive terms  
- Improves model performance for classification tasks

---

## ⚙️ Model Training

Data was split using `train_test_split` (70/30 split). Four models were trained:

1. **Multinomial Naive Bayes + TF-IDF**  
2. **Multinomial Naive Bayes + CountVectorizer**  
3. **Random Forest + TF-IDF**  
4. **Random Forest + CountVectorizer**

Each used a `Pipeline` for consistency and cleaner code.

---

## 📈 Model Evaluation

Used a custom evaluation function to compute:

- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-Score**

All models were evaluated on the same test set.

---
## 📊 Results
The sentiment analysis models were evaluated on accuracy, precision, recall, F1-score, and training time. Below is a comparison of the models:

| Model                           | Accuracy   | Precision | Recall | F1-Score | Training Time      |
| ------------------------------- | ---------- | --------- | ------ | -------- | ------------------ |
| **MultinomialNB + TF-IDF**      | **86.03%** | 86.03%    | 86.03% | 86.03%   | \~8 seconds        |
| MultinomialNB + CountVectorizer | 85.25%     | 85.29%    | 85.25% | 85.25%   | \~8 seconds        |
| Random Forest + TF-IDF          | 84.76%     | 84.81%    | 84.76% | 84.75%   | \~5 minutes 23 sec |
| Random Forest + CountVectorizer | 84.83%     | 84.89%    | 84.83% | 84.83%   | \~6 minutes 5 sec  |


## ✅ Best Performance: Multinomial Naive Bayes with TF-IDF
⚖️ Trade-off: Random Forests had longer training time with similar accuracy.

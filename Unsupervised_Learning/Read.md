# SmartPhones Price Analysis & Recommendation System

## Project Overview
This project builds a **data-driven phone price analysis and recommendation system** using Jumia’s smartphone listings.  
It solves two main problems:
1. **Understanding the smartphone market** through price, specification, and customer review analysis.
2. **Helping customers find similar phones** using a content-based recommendation model.

The project integrates **data preprocessing**, **feature engineering**, **customer segmentation (KMeans clustering)**,
and a **cosine similarity-based recommendation engine**.

---

## Methodology & Approach

### Data Preprocessing & Cleaning
- **Data Source**: Jumia smartphone listings (`Jumia_Phones.csv`).
- **Tasks performed**:
  - Removed HTML tags from product names, reviews, and prices using `BeautifulSoup`.
  - Extracted structured attributes:  
    - **Brand**, **Model**, **Screen Size**, **RAM**, **ROM**, **Battery**, **Android Version**, **Color**, **Price** and **Reviews**.
  - Applied regex patterns to standardize and clean model names.
  - Corrected anomalies in RAM/ROM values (e.g., removing unrealistic values like `128GB` in RAM).
  - Converted prices to numeric (NGN) and review ratings to floats.
  - Handled missing values:
    - **ML-based imputation** using `RandomForestRegressor`/`RandomForestClassifier`.
    - Dropped columns with excessive missing data (`Battery` > 50% missing).

---

### Customer Segmentation (KMeans Clustering)
- **Goal**: Group phones into **price-performance segments** for market insights.
- **Features used**:
  - `Price`, `RAM`, `ROM`, `Review`
- **Process**:
  - Normalized features with `StandardScaler`.
  - Used **Elbow Method** and **Silhouette Score** to determine optimal clusters.
  - Final clustering: `k=3` (Silhouette Score ≈ 0.4958).
- **Cluster Labels**:
  1. **Premium-Product** – Affordable but high-value phones.
  2. **Top-Tier (High Premium - Spec)** – High RAM/ROM, large screens, higher price.
  3. **Mid-Tier (Low Budget)** – Lower price, basic specifications.
  
---

### Price Segmentation
- Price bins:  
  - Low (< ₦70k)  
  - Lower-Mid (₦70k – ₦150k)  
  - Upper-Mid (₦150k – ₦300k)  
  - High (> ₦300k)
- Helps target different market categories and price-conscious users.

---

### Recommendation System (Content-Based Filtering)
- **Goal**: Suggest similar phones based on **specs, price, and reviews**.
- **Process**:
  1. Created a **model-cluster matrix** showing how each model appears in the clusters.
  2. Calculated **cosine similarity** between all models.
  3. Defined a function `phone_recommendation(model_name, top_n)`:
     - Finds top-N similar phones excluding the queried model.
     - Returns phone details for quick decision-making.
- **Use Case**:
  ```python
  phone_recommendation("S25 ULTRA", top_n=5)

  
## Key Insights & Inferences
- Market is heavily mid-range: Most phones priced between ₦70k – ₦150k.

- Premium segment has fewer models but higher specs and brand variety.

- Customer reviews tend to favor mid-to-premium devices, possibly due to perceived value.

- Cosine similarity allows finding alternatives with almost identical specs, improving user choice flexibility.

## Problems Solved
- Data Transparency – Converts messy e-commerce data into structured, analyzable form.

- Customer Segmentation – Helps sellers target marketing campaigns to different buyer personas.

- Smart Recommendations – Provides customers with relevant alternatives when their chosen model is unavailable or too costly.

- Market Analysis – Identifies high-demand specs and pricing trends for sellers and manufacturers.

## Challenges & Solutions
**Challenge	Solution**
- HTML-embedded product details	Used BeautifulSoup to parse and clean text
- Inconsistent model naming	Applied regex pattern mapping for standardization
- Missing values in critical features	ML-based imputation using RandomForest models
- Price variation & anomalies	Converted all prices to numeric NGN values and standardized format
- Choosing optimal clusters	Used Elbow Method + Silhouette Score for validation
- Similarity computation bias	Normalized features before cosine similarity

##  How to Use
- Data Cleaning – Run preprocessing scripts to load and clean new datasets.

- Clustering – Re-run KMeans to segment updated phone data.

- Recommendation – Use phone_recommendation(model_name, top_n) to get similar phones.




# Technologies/Tool Used
- Python: pandas, numpy, scikit-learn, seaborn, matplotlib, plotly, etc

- Web Scraping: BeautifulSoup

- ML Models: RandomForest (imputation), KMeans (clustering)

- Recommendation: Cosine Similarity (content-based)

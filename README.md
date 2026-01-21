# E-commerce Customer Insights and RFM Segmentation

![RFM](images/RFM.png)
> The image was taken from this [Linkedin post](https://www.linkedin.com/pulse/how-conduct-rfm-analysis-improve-your-business-strategy-sifat/)

An end-to-end Data Analytics project utilizing Python and SQL principles to transform raw transactional data into actionable business intelligence. By implementing a [Recency, Frequency, and Monetary (RFM) model](https://en.wikipedia.org/wiki/RFM_(market_research)), this project segments over 4,300 unique customers to identify high-value "Champions" and at-risk users.

## Business Impact
* Data Integrity: Cleaned and validated a raw dataset of 541k+ records, ensuring 100% referential integrity for analytical reporting.
* Behavioral Insights: Quantified customer value into distinct segments (Champions, Loyal, At-Risk, Regulars), providing a framework for targeted marketing and retention strategies.
* Automated Pipeline: Developed a Python-based processing engine that automates data cleaning and feature engineering, reducing the time from raw data to insight discovery.

## Tech Stack
* Language: Python (Pandas, NumPy, datetime, sklearn)
* Visualization: Plotly (Interactive Dashboards), Matplotlib, Seaborn
* Concepts: RFM Modeling, Exploratory Data Analysis (EDA), Statistical Distribution, Data Cleaning.
* Datasets: [ucimlrepo](https://archive.ics.uci.edu/dataset/352/online+retail) `(id=352)`

## Methodology and Key Findings

### 1. Data Engineering and Cleaning
Leveraging a background in software reliability, I processed the UCI Online Retail Dataset by:
* Removing null CustomerID values to ensure segment accuracy.
* Filtering out transaction cancellations and non-positive quantities.
* Engineering a TotalSales feature to track gross revenue per transaction.

### 2. RFM Calculation

I calculated three core metrics for each of the 4,338 unique customers:
* Recency: Days since the last purchase/snapshot **(identifying engagement)**.
* Frequency: Total number of unique invoices **(identifying loyalty)**.
* Monetary: Total spending **(identifying revenue contribution)**.

### 3. Interactive Visualization
The project features a dynamic dashboard (built with Plotly) that allows stakeholders to:
* Identify the correlation between purchase frequency and total spend.
* Visualize the distribution of customer segments through interactive 3D Clusters and histograms.
* Drill down into specific customer cohorts to optimize acquisition costs.

#### 3.1. Below are the screenshots of the generated plots
![recency](images/recency.png)
<p align="center">Histogram Distribution for Recency</p>

![frequency](images/frequency.png)
<p align="center">Histogram Distribution for Frequency</p>

![monetary](images/monetary.png)
<p align="center">Histogram Distribution for Monetary</p>

![frequency_vs_monetary](images/frequency_vs_monetary.png)
<p align="center">Scatter plot for Frequency vs Monetary</p>

![elbow](images/Elbow.png)
<p align="center">Elbow Method for Optimal K Clustering</p>

![3D_RFM_Clusters](images/3D_RFM_Clusters.png)
<p align="center">3D RFM Customer Clusters</p>

> NOTE: every plot shown here are interactive except `elbow method graph`

## How to Run

<details>
<summary>🔨 Manual Build</summary>

1. Clone this repository.
2. Open [RFM.ipynb](RFM.ipynb) in Google Colab or Jupyter Notebook.
3. Install dependencies:
  
```python
pip install pandas matplotlib seaborn plotly ucimlrepo
```
> NOTE: Google Collab already preinstalled everything except `ucimlrepo`

4. Run all cells to generate the interactive dashboard.
</details>

<details>
<summary>🔗 Google Collab Link</summary>

1. Click this Google Collab [link](https://colab.research.google.com/drive/1laIJbLEEMY-9b0zpW-Fy0z5NiS99p4XU?usp=sharing)
2. Run All

</details>


## Summary from the Project

Four distinct customer segments were identified based on their average Recency, Frequency, and Monetary values.

<details>
  <summary>📊 Clusters</summary>
  

### Cluster 0

| Avg. Recency | Avg. Frequency | Avg. Monetary |
|---|---|---|
| 43.7 | 3.68 | 1359.05 |

**Description**: These customers have a moderate recency, frequency, and monetary value. They are fairly active but not among the top spenders or most frequent buyers. They could be "Regular Customers" or "Potential Loyalists".

**Marketing Strategy**: Encourage increased frequency and monetary value. Offer loyalty programs, personalized recommendations based on past purchases, and exclusive discounts to motivate them to move into higher-value segments.


### Cluster 1

| Avg. Recency | Avg. Frequency | Avg. Monetary |
|---|---|---|
| 248.08 | 1.55 | 480.62 |

**Description**: These customers have high recency (meaning they haven't purchased recently), low frequency, and low monetary value. They are likely "At-Risk Customers" or "Lost Customers".

**Marketing Strategy**: Implement win-back campaigns with aggressive discounts, re-engagement emails, or special offers on products they previously showed interest in. Try to understand reasons for churn if possible through surveys.

### Cluster 2

| Avg. Recency | Avg. Frequency | Avg. Monetary |
|---|---|---|
| 7.38 | 82.54 | 127338.31 |

**Description**: This cluster represents customers with very low recency (purchased very recently), extremely high frequency, and exceptionally high monetary value. These are clearly the "Champions" or "Best Customers".

**Marketing Strategy**: Reward them with VIP treatment, exclusive access to new products, early sales previews, and personalized communication. Focus on retention and encouraging word-of-mouth referrals. Solicit feedback to ensure continued satisfaction.

### Cluster 3

| Avg. Recency | Avg. Frequency | Avg. Monetary |
|---|---|---|
| 15.5 | 22.33 | 12709.09 |

**Description**: These customers have low recency, high frequency, and high monetary value, though not as extreme as Cluster 2. They are likely "Loyal Customers" or "High-Value Engaged".

**Marketing Strategy**: Maintain engagement through personalized communication, exclusive content, and loyalty programs. Cross-sell and up-sell relevant products. Encourage them to become advocates for the brand.
  
</details>

<details>
  <summary>🪜 Insights or Next Steps</summary>


* Leverage the interactive 3D Plotly visualization in an e-commerce dashboard to allow stakeholders to intuitively explore customer segments and their behavioral patterns, facilitating quicker decision-making for targeted campaigns.
* Continuously monitor the RFM profiles of these clusters over time to detect shifts in customer behavior, validate the effectiveness of marketing strategies, and adjust segment definitions or strategies as needed.
  
</details>




---

<p align="center">😁 Thank you for visiting</p>

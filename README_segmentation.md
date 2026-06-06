# 🛍️ Customer Segmentation Analysis — Pakistan E-Commerce Market
**Tool:** Python (pandas, scikit-learn, matplotlib, seaborn) | **Domain:** Marketing Analytics | **Dataset:** Pakistan's Largest E-Commerce Dataset (Kaggle)

---

## 📁 Project Structure

```
python-customer-segmentation/
│
├── README.md                        ← You are here (findings & recommendations)
├── data/
│   └── pakistan_ecommerce.csv       ← Raw dataset
├── notebooks/
│   └── customer_segmentation.ipynb  ← Full analysis notebook
└── visuals/
    ├── elbow_curve.png
    ├── elbow_curve_clean.png
    ├── segment_count.png
    ├── segment_monetary.png
    └── rfm_scatter.png
```

---

## 🎯 Project Objective

This project segments customers of a Pakistani e-commerce platform using the RFM (Recency, Frequency, Monetary) model and K-Means clustering. The goal is to identify distinct customer groups and provide targeted marketing strategies for each segment — applicable to South Asian e-commerce platforms such as Daraz, Chaldal, and Shajgoj.

---

## 📦 Dataset Overview

| Attribute | Detail |
|---|---|
| Source | [Kaggle — Pakistan's Largest E-Commerce Dataset](https://www.kaggle.com/datasets/zusmani/pakistans-largest-ecommerce-dataset) |
| Raw Rows | 1,048,575 |
| Clean Rows (completed orders) | 233,685 |
| Date Range | July 2016 — August 2018 |
| Unique Customers | 67,094 |

---

## 🔧 Methodology

### Step 1 — Data Cleaning
- Removed 5 fully empty columns
- Dropped rows with missing Customer ID or grand_total
- Filtered to completed orders only (removed canceled and refunded)
- Final clean dataset: **233,685 rows**

### Step 2 — RFM Feature Engineering

| Feature | Definition |
|---|---|
| **Recency** | Days since customer's last purchase (reference: 2018-08-13) |
| **Frequency** | Number of unique orders placed |
| **Monetary** | Total amount spent (₨) |

### Step 3 — Outlier Removal
- Capped Frequency and Monetary at 99th percentile
- Removed extreme outliers (e.g. single customer with ₨35.7M spend, 1,579 orders)
- Final clustering dataset: **66,014 customers**

### Step 4 — K-Means Clustering
- Used Elbow Method to determine optimal K
- Selected **K = 4** clusters
- Applied StandardScaler before clustering to normalize RFM values

---

## 📊 Segment Results

| Segment | Customers | Avg Recency | Avg Frequency | Avg Monetary |
|---|---|---|---|---|
| ⭐ Champions | 2,017 | 245 days | 5.77 orders | ₨124,024 |
| 🟢 Loyal Customers | 4,745 | 312 days | 6.64 orders | ₨32,400 |
| 🟡 At Risk | 29,861 | 249 days | 1.41 orders | ₨7,625 |
| 🔴 Dormant | 29,391 | 583 days | 1.34 orders | ₨4,999 |

---

## 📈 Visualizations

### Customer Count by Segment
![Customer Count](visuals/segment_count.png)

Over 88% of customers fall into the At Risk or Dormant categories — representing a massive re-engagement opportunity.

---

### Average Spending by Segment
![Average Spending](visuals/segment_monetary.png)

Champions spend 16x more than Dormant customers on average (₨124,024 vs ₨4,999). Loyal Customers spend 4x more than At Risk customers.

---

### Recency vs Monetary Value by Segment
![RFM Scatter](visuals/rfm_scatter.png)

Champions cluster at high monetary values across varying recency levels — indicating they purchase frequently regardless of how long ago they last bought. Dormant customers cluster at low monetary values and high recency (600–800 days).

---

## 💡 Business Recommendations

### ⭐ Champions (2,017 customers — 3% of base)
- Launch a **VIP loyalty program** with early access to new products and exclusive discounts
- Use as **brand ambassadors** — referral programs work best with this segment
- Upsell premium product categories (electronics, high-end fashion)
- **Priority:** Retain at all costs — they drive disproportionate revenue

### 🟢 Loyal Customers (4,745 customers — 7% of base)
- Offer **tiered rewards** to push them toward Champion status
- Send **personalized product recommendations** based on category purchase history
- Target with bundle deals and loyalty points
- **Priority:** Nurture toward Champions — highest conversion potential

### 🟡 At Risk (29,861 customers — 45% of base)
- Send **win-back campaigns** with time-limited discount offers
- Identify which category they last purchased in and target accordingly
- A/B test email subject lines — urgency vs value messaging
- **Priority:** Highest volume opportunity — even 10% conversion = 3,000 recovered customers

### 🔴 Dormant (29,391 customers — 44% of base)
- Last resort: send a **"We miss you"** campaign with a steep one-time discount
- If no response after 2 attempts, pause marketing spend on this segment
- Analyze why they churned — price sensitivity, poor experience, or competition
- **Priority:** Low ROI — focus budget on At Risk segment first

---

## 🛠️ Tools & Libraries

| Tool | Purpose |
|---|---|
| pandas | Data loading, cleaning, RFM calculation |
| numpy | Numerical operations |
| scikit-learn | StandardScaler, KMeans clustering |
| matplotlib | Bar charts, scatter plot, elbow curve |
| seaborn | Plot styling |

---

## 🌏 Local Relevance

This analysis uses data from Pakistan's e-commerce market — a South Asian context directly comparable to Bangladesh. The segmentation framework and recommendations are applicable to platforms like **Daraz BD**, **Chaldal**, **Shajgoj**, and **Bikroy** operating in the Bangladeshi market.

---

## 👤 Author

**Swagata Barman**
BBA in Business Analytics & Marketing — United International University, Dhaka
📧 barmanswagata1@gmail.com
🌐 [swa34.wordpress.com](https://swa34.wordpress.com)


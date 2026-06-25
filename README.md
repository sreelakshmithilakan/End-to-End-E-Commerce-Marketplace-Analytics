# End-to-End E-Commerce Marketplace Analytics
![Language](https://img.shields.io/badge/Language-Python-3776AB?style=flat-square) ![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Pandas%20%7C%20NumPy-150458?style=flat-square) ![Visualization](https://img.shields.io/badge/Visualization-Plotly%20%7C%20Matplotlib-2b5b84?style=flat-square) ![Dev Environment](https://img.shields.io/badge/Environment-Jupyter-F37626?style=flat-square) ![Version Control](https://img.shields.io/badge/Version%20Control-Git%20%2F%20GitHub-F05032?style=flat-square)

## Overview

This project presents an end-to-end analytical assessment of a multi-vendor e-commerce marketplace using transactional, customer, product, seller, payment, and logistics data.

The objective was to evaluate marketplace performance through five strategic perspectives:

* Customer Analytics
* Product Analytics
* Seller Analytics
* Delivery & Customer Experience Analytics
* Revenue & Marketplace Analytics

The analysis combines customer segmentation, product portfolio evaluation, seller ecosystem assessment, logistics performance measurement, and revenue concentration analysis to uncover the key drivers of marketplace growth, operational efficiency, and customer satisfaction.

---

## Business Objectives

### Customer Analytics

* Identify high-value customer segments
* Evaluate customer retention behavior
* Understand revenue contribution by customer groups

### Product Analytics

* Identify revenue-driving categories
* Evaluate product portfolio performance
* Assess logistics efficiency across categories
* Discover cross-category purchasing patterns

### Seller Analytics

* Analyze seller performance distribution
* Measure marketplace dependency on top sellers
* Identify category-level seller dominance

### Delivery & Customer Experience Analytics

* Measure fulfillment efficiency
* Evaluate delivery reliability
* Assess the impact of delivery performance on customer satisfaction

### Revenue & Marketplace Analytics

* Analyze revenue growth trends
* Evaluate marketplace revenue concentration
* Understand customer payment preferences

---

## Dataset

The analysis was conducted using the Olist Brazilian E-Commerce Dataset.

### Core Tables

| Dataset                      | Description                            |
| ---------------------------- | -------------------------------------- |
| Customers                    | Customer information                   |
| Orders                       | Order lifecycle and delivery data      |
| Order Items                  | Product-level transaction records      |
| Products                     | Product information                    |
| Product Category Translation | Category mapping                       |
| Sellers                      | Seller information                     |
| Payments                     | Payment methods and transaction values |
| Reviews                      | Customer review scores                 |

---

## Tools & Technologies

### Programming & Analysis

* Python
* Pandas
* NumPy

### Data Visualization

* Plotly Express
* Matplotlib

### Development Environment

* Jupyter Notebook / Google Colab

### Version Control

* Git
* GitHub

---

# Analysis Framework

## 1. Customer Analytics

### RFM Segmentation

Customers were initially evaluated using the Recency, Frequency, and Monetary (RFM) framework to understand purchasing behavior and customer value.

#### Key Findings
* Approximately 97% of customers made only a single purchase.
* Frequency showed extremely limited variation across the customer base, reducing its effectiveness as a differentiating metric.
* As a result, customer segmentation was driven primarily by Recency and Monetary dimensions.
* Repeat purchase behavior remained relatively low across the marketplace.
* Customer retention emerged as one of the largest opportunities for long-term growth.


**Analytical Note**

Due to the highly skewed purchase frequency distribution, Frequency provided limited segmentation value in this dataset. Consequently, customer analysis focused primarily on Recency and Monetary behavior, while Frequency was examined separately through retention and repeat-purchase analysis.

---
### Recency vs Monetary Customer Distribution

<img width="1340" height="448" alt="newplot (22)" src="https://github.com/user-attachments/assets/46dbd6e1-faa9-4fe0-a05b-4f5c0adf8e00" />

#### Methodology

- Customers were scored using a simplified RFM framework.
- Due to extremely low repeat purchase behavior (approximately 97% of customers placed only one order), Frequency was excluded from this visualization.
- Recency scores were assigned using quintiles (1–5) based on days since the most recent purchase.
- Monetary scores were assigned using quintiles (1–5) based on total customer spending.
- The heatmap displays the number of customers within each Recency–Monetary score combination.


**Insight**

The customer base is heavily concentrated in **medium-to-high Recency and Monetary score** combinations, indicating that a large proportion of customers have purchased relatively recently and generated meaningful revenue. However, a noticeable group of low-recency customers remains, suggesting that customer churn and inactivity continue to impact the marketplace.

Recommended Action:
Prioritize retention and re-engagement strategies for customers with declining recency scores while nurturing recently active, high-spending customers through personalized offers, loyalty programs, and targeted marketing campaigns. Improving repeat purchase behavior among these segments can significantly increase customer lifetime value.

### Customer Value Segmentation

<img width="1340" height="525" alt="newplot (21)" src="https://github.com/user-attachments/assets/54792b95-eab3-459e-b8a5-befca46581d3" />


#### Methodology

Customers were segmented using Recency and Monetary scores.

| Segment | Definition |
|----------|------------|
| Champion | High spending, highly recent customers |
| Potential Loyalist | Recent customers with moderate-to-high spending |
| Regular Customer | Average recency and spending behavior |
| At Risk | Previously valuable customers showing declining activity |
| Lost Customer | Customers with low recent engagement |

*Frequency was not a significant segmentation driver due to the marketplace's very low repeat purchase rate.*


#### Insight

Regular Customers represent the largest customer segment, followed by Potential Loyalists, indicating that the marketplace has successfully built a broad customer base. However, the sizeable **At Risk and Lost Customer segments** suggest that a significant portion of customers may not be progressing toward long-term loyalty. While Champion customers form a meaningful high-value segment, there remains substantial opportunity to increase customer lifetime value through improved retention and engagement strategies.

Recommended Action:
Focus on converting **Regular Customers and Potential Loyalists** into repeat purchasers through personalized promotions, loyalty programs, and targeted post-purchase engagement. Simultaneously, implement reactivation campaigns for At Risk and Lost Customers to reduce churn and strengthen long-term customer retention.

---

### Customer Value Segment vs Retention Segment

<img width="1340" height="525" alt="newplot (25)" src="https://github.com/user-attachments/assets/565e89e7-ca23-4a1e-b3b8-1389d70a14c0" />

#### Methodology

Customers were classified according to actual purchase frequency.

| Retention Segment | Criteria |
|------------------|----------|
| One-Time Buyer | 1 Purchase |
| Returning Customer | 2–4 Purchases |
| Loyal Customer | 5+ Purchases |

The heatmap compares customer value segments against actual purchasing frequency behavior.

#### Insight

Despite the presence of high-value customer segments such as Champions and Potential Loyalists, the marketplace is overwhelmingly dominated by one-time buyers across all customer groups. Repeat purchasing behavior remains limited, indicating that customer acquisition is significantly outperforming customer retention.

Recommended Action:
Implement retention-focused initiatives such as personalized remarketing campaigns, loyalty programs, post-purchase engagement journeys, and targeted offers for high-value customers. Increasing repeat purchase rates among existing customers is likely to deliver greater long-term revenue growth than customer acquisition alone.

---

## 2. Product Analytics

### Pareto Analysis

<img width="1340" height="525" alt="newplot (26)" src="https://github.com/user-attachments/assets/c7a94bea-3743-4910-b58a-38665e81dd07" />


#### Methodology

- Product categories were ranked by total revenue generated.
- Revenue contribution percentages were calculated for each category.
- A cumulative revenue curve was created to determine how many categories generate 80% of marketplace revenue.


#### Insight
Revenue follows a classic Pareto distribution, with only 16 of 71 product categories generating approximately 80% of total marketplace revenue. These categories serve as the marketplace's primary revenue drivers and have a disproportionate impact on overall business performance.

Recommended Action: Focus promotional campaigns, inventory planning, and category growth initiatives on these high-performing categories while identifying secondary categories with growth potential to diversify revenue sources.

---

### Product Portfolio Matrix

<img width="1340" height="525" alt="newplot (27)" src="https://github.com/user-attachments/assets/edd17a5c-9820-46e3-8e1e-e65fdef576a1" />


#### Methodology

Product categories were classified using:

- Average Product Price
- Total Units Sold

Categories were segmented using median-based thresholds.

| Segment | Characteristics |
|----------|---------------|
| Portfolio Star | High price, high volume |
| Traffic Driver | Low price, high volume |
| Premium Niche | High price, low volume |
| Low Impact | Low price, low volume |

Bubble size represents category revenue contribution.

#### Insight

The marketplace product portfolio is highly diverse, with categories distributed across all four strategic quadrants. While a small group of Portfolio Stars drives both sales volume and revenue, several categories function primarily as Traffic Drivers, generating customer demand despite lower average prices. The presence of Premium Niches suggests opportunities for higher-margin growth, while Low Impact Categories contribute relatively little to marketplace performance and may dilute operational focus.

Recommended Action:
Prioritize inventory planning, promotional investment, and supplier partnerships for **Portfolio Stars** to sustain revenue growth. Use **Traffic Drivers** to attract and retain customers through competitive pricing and cross-selling opportunities. Expand high-potential **Premium Niches** through targeted marketing and product assortment strategies, while reviewing **Low Impact Categories** for optimization, repositioning, or potential rationalization.

---

### Freight Efficiency Analysis

<img width="1340" height="525" alt="newplot (28)" src="https://github.com/user-attachments/assets/6306dee4-b350-48d1-8e50-70dc9deee6b9" />


#### Methodology

Freight efficiency was calculated using:

Freight-to-Price Ratio (%) = (Total Freight Cost ÷ Total Product Revenue) × 100

Categories with higher ratios indicate a greater logistics burden relative to product value.

#### Insight
Freight costs consume a disproportionately large share of product value in several categories, with some categories allocating more than 25-35% of product price toward shipping expenses. This indicates that logistics costs can significantly erode profitability, particularly for bulky, low-priced, or difficult-to-ship products. Categories such as furniture, food, and electronics appear especially exposed to transportation cost pressures.

Recommended Action:
Review shipping strategies for high freight-ratio categories by optimizing packaging, consolidating shipments, negotiating carrier rates, or adjusting pricing structures to better absorb logistics costs. Prioritize operational improvements in categories with the highest freight burden to protect margins and improve overall marketplace profitability.


---

## 3. Seller Analytics

### Geographic Seller Performance

<img width="1340" height="525" alt="newplot (29)" src="https://github.com/user-attachments/assets/2e8d1b9b-a8a2-4986-8b47-591922f89b01" />

#### Methodology

Seller revenue was aggregated by state and analyzed using:

- Total Revenue Contribution
- Average Revenue per Seller

This analysis evaluates both seller concentration and regional productivity.

#### Insight
Marketplace revenue is highly concentrated within a small number of states. São Paulo (SP) contributes approximately 64% of total marketplace revenue, significantly outperforming all other regions. The remaining states contribute comparatively smaller shares, highlighting a strong geographic concentration within the seller ecosystem.

Recommended Action

Reduce geographic concentration risk by encouraging **seller acquisition and marketplace expansion** in underrepresented states. Diversifying the seller base can improve marketplace resilience, increase regional product availability, and reduce dependency on a single geographic market.

---

### Marketplace Dependency Risk

<img width="1340" height="525" alt="newplot (31)" src="https://github.com/user-attachments/assets/28f869dd-d871-4c66-96c2-baddf7aba291" />

#### Methodology

- Sellers were ranked by revenue contribution.
- A cumulative revenue distribution curve was created.
- The percentage of sellers required to generate 80% of total revenue was calculated.


#### Insight

Marketplace revenue is moderately concentrated among a relatively small group of sellers. Approximately 543 sellers (17.5% of all sellers) generate 80% of marketplace revenue, creating operational dependence on key vendors while maintaining broader seller participation.

---

### Seller Category Specialization

<img width="1340" height="525" alt="newplot (32)" src="https://github.com/user-attachments/assets/c39f82aa-cd63-464e-8f9b-888fed7788ee" />

#### Methodology

For each product category:

- Revenue generated by the top-performing seller was identified.
- The top seller's share of category revenue was calculated.
- Categories were ranked according to seller dominance levels.


#### Insight

Competitive intensity varies considerably across product categories. While some categories distribute revenue among many sellers, others are dominated by a small number of vendors, increasing category-level concentration risk.

---

## 4. Delivery & Customer Experience Analytics

### Fulfillment Velocity Analysis

<img width="1340" height="525" alt="newplot (33)" src="https://github.com/user-attachments/assets/d1dc3c99-d95f-4f57-b1b8-4cff8e789dd0" />


#### Key Metrics

| Metric           | Average Days |
| ---------------- | -----------: |
| Approval Time    |         0.43 |
| Dispatch Time    |         2.80 |
| Delivery Time    |         9.33 |
| Total Cycle Time |        12.56 |

#### Insight

The average order lifecycle is approximately 12.6 days. Delivery transit alone accounts for nearly 74% of total fulfillment time, making transportation and last-mile logistics the primary operational bottleneck.

---

### Delivery Reliability Analysis

<img width="1340" height="525" alt="newplot (34)" src="https://github.com/user-attachments/assets/bee2d0c0-f1f2-4d90-9d12-0137f34a64e4" />


#### Key Metrics

* 91.9% of orders delivered on time or early
* 8.1% of orders delivered late
* Average delay among late orders: 9.5 days

#### Insight

Delivery performance remains strong across the marketplace, with the vast majority of orders arriving on or before the promised delivery date. However, delayed orders experience substantial overruns that can negatively impact customer experience.

---

### Delivery Performance vs Customer Reviews

<img width="1340" height="525" alt="newplot (35)" src="https://github.com/user-attachments/assets/cfffefba-ffed-49af-84ca-fb0739988d24" />


#### Key Metrics

| Delivery Status | Average Review Score |
| --------------- | -------------------: |
| On Time / Early |                 4.29 |
| Late            |                 2.57 |

#### Insight

Customer satisfaction is strongly linked to delivery performance. Orders delivered on time receive significantly higher review scores, while customer ratings decline sharply when delivery delays occur.

---

## 5. Revenue & Marketplace Analytics

### Revenue Trend Analysis

<img width="1340" height="525" alt="newplot (36)" src="https://github.com/user-attachments/assets/c356de80-69b2-48d3-b685-c64cbb12552f" />

#### Insight

Marketplace revenue expanded rapidly throughout 2017, increasing nearly sixfold before reaching a peak of approximately 1.15 million during late 2017. Revenue subsequently stabilized above one million per month, indicating a transition toward marketplace maturity.

---

### Revenue Concentration Analysis

<img width="1340" height="525" alt="newplot (37)" src="https://github.com/user-attachments/assets/849c22b6-6b61-4acf-8baa-21032bce12b9" />

#### Results

| Entity     | % Required to Generate 80% Revenue |
| ---------- | ---------------------------------: |
| Sellers    |                              17.5% |
| Categories |                              22.5% |
| Customers  |                              49.2% |

#### Insight

Revenue concentration varies significantly across marketplace entities. Sellers and categories exhibit relatively high concentration levels, while customer spending remains broadly distributed. Nearly half of all customers are required to generate 80% of marketplace revenue, reducing customer concentration risk.

---

### Payment Behavior Analysis

<img width="1340" height="525" alt="newplot (38)" src="https://github.com/user-attachments/assets/538e9b70-eb71-452d-86f0-906514850bb0" />


#### Revenue Share by Payment Method

| Payment Method | Revenue Share |
| -------------- | ------------: |
| Credit Card    |         78.3% |
| Boleto         |         17.9% |
| Voucher        |          2.4% |
| Debit Card     |          1.4% |

#### Insight

Customer payment behavior is heavily dominated by credit card transactions, which account for more than three-quarters of marketplace revenue. Alternative payment methods play a significantly smaller role in overall transaction volume.

---

# Key Business Findings

### Customer Insights

* Customer retention remains one of the largest growth opportunities for the marketplace.
* Revenue is supported by a broad customer base rather than a small group of high-value customers.
* Repeat purchasing behavior remains relatively limited despite strong customer acquisition.

### Product Insights

* Revenue generation is concentrated among a limited number of product categories.
* Product categories play distinct strategic roles within the marketplace ecosystem.
* Freight costs significantly impact profitability in selected categories.
* Cross-category purchasing behavior remains relatively low.

### Seller Insights

* Marketplace performance depends heavily on a relatively small group of high-performing sellers.
* Seller revenue is geographically concentrated, with São Paulo dominating marketplace activity.
* Competitive intensity varies significantly across product categories.

### Operational Insights

* Delivery transit time is the largest fulfillment bottleneck.
* Overall delivery reliability remains strong.
* Customer satisfaction declines significantly as delivery delays increase.

### Revenue Insights

* Revenue growth accelerated rapidly during the marketplace expansion phase.
* Revenue concentration risk exists primarily among sellers and categories rather than customers.
* Credit cards dominate marketplace transactions and revenue generation.

---

## Project Structure

```text
E-Commerce-Marketplace-Analytics/
│
├── data/
├── notebooks/
│   ├── customer_analytics.ipynb
│   ├── product_analytics.ipynb
│   ├── seller_analytics.ipynb
│   ├── delivery_analytics.ipynb
│   └── revenue_analytics.ipynb
│
├── visuals/
├── README.md
└── requirements.txt
```

---

## Skills Demonstrated

* Data Cleaning & Transformation
* Exploratory Data Analysis (EDA)
* Customer Segmentation (RFM)
* Revenue & Concentration Analysis
* Marketplace Analytics
* Logistics & Operations Analytics
* Business Intelligence
* Data Visualization
* Data Storytelling
* Strategic Business Analysis

---

## Conclusion

This project demonstrates how customer behavior, product performance, seller dynamics, logistics efficiency, and revenue concentration collectively influence marketplace success. By integrating customer, commercial, operational, and financial analytics, the analysis provides a comprehensive view of marketplace performance and identifies opportunities for growth, efficiency improvements, and risk reduction.

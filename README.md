# Customer-Segmentation-and-Market-Basket-Analysis-for-Retail-Insights

Problem Statement

Retailers need to understand:

Which products are frequently bought together?

How do different customer groups behave in terms of purchasing?

The goal of this project is to combine Market Basket Analysis (FP-Growth) with Customer Segmentation (RFM + KMeans) to extract actionable insights for product bundling, promotions, and customer retention strategies.

Dataset

Source: UCI Online Retail Dataset

Transactions: ~500K records (2010–2011) from a UK-based retailer

Key Variables:

InvoiceNo – transaction ID

StockCode – product ID

Description – product name

Quantity – units purchased

InvoiceDate – date and time of purchase

UnitPrice – price per unit (GBP)

CustomerID – unique customer identifier

Country – customer location

Methodology
1. Data Cleaning & Preparation

Removed missing CustomerID values.

Excluded cancellations and negative quantities.

Standardized product descriptions.

Created basket representations for transactions and customers.

2. Market Basket Analysis (FP-Growth)

Built transaction–item matrix.

Extracted frequent itemsets and association rules.

Filtered rules using Support, confidence, and lift.

3. Customer Segmentation (RFM + KMeans)

Computed Recency, Frequency, and Monetary features.

Scaled features and applied K-Means clustering.

Validated clusters with Silhouette Score = 0.61.

4. Integration

Mapped transactions to clusters.

Ran FP-Growth within clusters to reveal segment-specific product affinities.

Results
Customer Segments

Cluster 1 – Inactive: Low-cost entry items. Strategy → win-back offers, discount bundles.

Cluster 2 – VIP: High-value complete sets (herb markers, premium bundles). Strategy → bundle promotions, loyalty programs.

Cluster 3 – Loyal: Bundles + decor (herb markers, beakers). Strategy → upsell to VIP kits, loyalty rewards.

Cluster 0 – Average: Occasion-driven purchases (Christmas decor, picnic bags). Strategy → seasonal promotions.

Market Basket Rules

VIPs: Strong bundles with confidence ~1.0 and lift > 80 (full product sets).

Inactives: Small, cheap associations (paper cups + plates).

Loyals: Consistent bundle buying, but less high-value than VIPs.

Averages: Seasonal/holiday-driven product combinations.

Visuals

Scatterplots of RFM clusters (Recency vs Frequency, Frequency vs Monetary).

<img width="695" height="547" alt="image" src="https://github.com/user-attachments/assets/fa7f199e-ade3-43f5-a787-3f537b920d16" />
<img width="694" height="547" alt="image" src="https://github.com/user-attachments/assets/b3aaf7e7-25f7-4ece-b45f-04daaea10b81" />

Network graphs of association rules per cluster.

<img width="794" height="658" alt="image" src="https://github.com/user-attachments/assets/21d46fed-1084-4cd6-8b4d-ca3442acd96c" />

<img width="794" height="658" alt="image" src="https://github.com/user-attachments/assets/08b411c0-5a35-4095-a4b7-5ca961233138" />

<img width="794" height="658" alt="image" src="https://github.com/user-attachments/assets/51c4e3e1-ed1a-4766-a5cb-55c61be08797" />

<img width="794" height="658" alt="image" src="https://github.com/user-attachments/assets/4d2f60fd-d946-4271-8992-7ab487354000" />


Business-facing summary

Cluster 0 – Average

Behavior: Occasion-driven (tea plates, Christmas decor, picnic bags)

Strategy: Seasonal promotions, holiday discounts, themed offers

Cluster 1 – Inactive

Behavior: Low-cost, entry items (tea plates, paper cups, small decor)

Strategy: Win-back offers, discount bundles, starter packs

Cluster 2 – VIP

Behavior: High-value complete sets (herb markers, premium bundles)

Strategy: Bundle promotions, premium loyalty programs, stock management

Cluster 3 – Loyal

Behavior: Bundles + decor (herb markers, beakers, themed products)

Strategy: Upsell to VIP bundles, loyalty rewards, cross-selling kits


Key Insights

Different customer clusters have distinct buying behaviors.

VIPs buy full sets, requiring careful stock management and premium offers.

Inactives engage only with low-value items, needing re-engagement campaigns.

Average and Loyal customers respond well to seasonal and upsell strategies.

Tech Stack

Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn)

MLxtend (FP-Growth, Association Rules)

NetworkX (rule network graphs)

Next Steps

Extend to revenue-weighted rules (not just frequency).

Analyze seasonality by InvoiceDate.

Deploy interactive dashboard with Streamlit.


Author
Project by Karthik Velavarthypathi

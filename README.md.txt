🛍️ Customer Segmentation Analysis using K-Means Clustering

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)
![Status](https://img.shields.io/badge/Status-Complete-success.svg)

A comprehensive customer segmentation project using Machine Learning to identify distinct customer groups and provide actionable marketing insights based on RFM (Recency, Frequency, Monetary) analysis.

Internship Project | Arch Technologies



 📋 Table of Contents
- [Project Overview](-project-overview)
- [Dataset](-dataset)
- [Installation](-installation)
- [Methodology](-methodology)
- [Key Results](-key-results)
- [Customer Segments](-customer-segments)
- [Visualizations](-visualizations)
- [Business Recommendations](-business-recommendations)
- [Technologies Used](-technologies-used)
- [Project Structure](-project-structure)
- [How to Run](-how-to-run)
- [Author](-author)
- [Acknowledgments](-acknowledgments)



 🎯 Project Overview

This project demonstrates the application of unsupervised machine learning (K-Means clustering) to segment customers based on their purchasing behavior. By analyzing transaction data, we identified 4 distinct customer segments that enable targeted marketing strategies and optimized resource allocation.

# Business Objectives:
- Identify distinct customer segments based on purchasing behavior
- Understand customer value and engagement patterns
- Provide actionable marketing recommendations for each segment
- Optimize marketing budget allocation based on customer profitability



 📊 Dataset

Source:[UCI Machine Learning Repository - Online Retail Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail)

Description:** Transactional data from a UK-based online retail company (December 2010 - December 2011)

Key Features:**
- InvoiceNo:** Unique transaction identifier
- StockCode:** Product code
- Description:** Product description
- Quantity:** Number of items purchased
- InvoiceDate:** Transaction date and time
- UnitPrice:** Price per unit
- CustomerID:** Unique customer identifier
- Country:** Customer's country

Dataset Statistics:
- Total Customers Analyzed: 4,057
- Date Range: 2010-12-01 to 2011-12-09
- Total Revenue: $4,100,992.81
- Average Customer Value: $1,010.84



💻 Installation

Prerequisites
```bash
Python 3.8+
pip
```

Required Libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```

 Clone Repository
```bash
git clone https://github.com/yourusername/customer-segmentation-analysis.git
cd customer-segmentation-analysis
```

---

🔬 Methodology

 1. Data Preprocessing
- Removed missing values and cancelled orders
- Filtered out invalid transactions (negative quantities/prices)
- Created `TotalPrice` feature
- Final dataset: 4,057 customers after cleaning

 2. Feature Engineering - RFM Analysis
RFM Metrics:
- Recency (R): Days since last purchase
- Frequency (F): Total number of purchases
- Monetary (M): Total amount spent

3. Data Scaling
- Applied StandardScaler to normalize features
- Ensured equal weight for all RFM dimensions

4. Determining Optimal Clusters
Methods Used:
- Elbow Method: Analyzed WCSS for K=2 to K=10
- Silhouette Score: Validated optimal number of clusters
- Result: K = 4 clusters selected

5. K-Means Clustering
- Algorithm: K-Means
- Number of Clusters: 4
- Random State: 42 (for reproducibility)
- Max Iterations: 300

6. Model Evaluation
- Silhouette Score: 0.4455 (moderate to good cluster separation)
- Davies-Bouldin Index: 0.8602 (lower is better)
- Inertia (WCSS): 2870.14

---

📈 Key Results

Clustering Performance Metrics

| Metric | Value | Interpretation |
|--------|-------|----------------|
| Silhouette Score | 0.4455 | Well-defined clusters |
| Davies-Bouldin Index | 0.8602 | Good cluster separation |
| Total WCSS| 2870.14 | Optimal variance minimization |

 Overall Statistics

| Metric | Value |
|--------|-------|
| Total Customers | 4,057 |
| Total Revenue | $4,100,992.81 |
| Average Customer Value | $1,010.84 |
| Most Valuable Segment | Cluster 3 (VIP Champions) |
| Most Active Segment | Cluster 3 |
| Most Recent Segment | Cluster 3 |



 🎯 Customer Segments

💎 Cluster 3: VIP/Champions (8.60% of customers)
Profile:
- Size: 349 customers
- Average Recency: 25.6 days
- Average Frequency: 9.6 purchases
- Average Monetary: $3,390.77
- Revenue Contribution: $1,183,379.71 (28.86%)

Characteristics: 
- Most valuable and engaged customers
- Recent, frequent, and high-value purchasers
- Strong brand loyalty

Strategy:
- 🌟 VIP treatment with exclusive perks
- 💎 Premium loyalty rewards
- 📢 Referral programs and brand ambassadorship
- 🎁 Early access to new products



⭐ Cluster 1: Loyal Customers (20.63% of customers)
Profile:
- Size: 837 customers
- Average Recency: 40.2 days
- Average Frequency: 5.0 purchases
- Average Monetary: $1,821.96
- Revenue Contribution: $1,524,976.72 (37.19%)

Characteristics:
- Consistent purchasers with good spending
- Regular engagement
- Strong revenue contributors

Strategy:
- 🤝 Relationship building programs
- 📈 Upselling and cross-selling opportunities
- 🎁 Points-based loyalty programs
- 💬 Testimonials and reviews



🌱 Cluster 2: Potential Customers (46.71% of customers)
Profile:
- Size: 1,895 customers
- Average Recency: 54.5 days
- Average Frequency: 1.9 purchases
- Average Monetary: $532.75
- Revenue Contribution: $1,009,566.19 (24.62%)

Characteristics:
- Largest segment with growth potential
- Recent but infrequent buyers
- Lower average spending

Strategy:
- 🌱 Nurture campaigns with educational content
- 🎯 Targeted promotions and discounts
- 📧 Email marketing automation
- 🔄 Subscription and replenishment programs



⚠️ Cluster 0: At-Risk/Lost Customers (24.06% of customers)
Profile:
- Size: 976 customers
- Average Recency: 255.7 days
- Average Frequency: 1.4 purchases
- Average Monetary: $392.49
- Revenue Contribution: $383,070.19 (9.34%)

Characteristics:
- Haven't purchased in 8+ months
- Low engagement and spending
- Risk of churn

Strategy:
- 🚨 Win-back campaigns with aggressive discounts
- 🔄 Re-engagement emails ("We miss you")
- 📞 Direct outreach and surveys
- 💡 Analyze churn reasons

---

 📊 Visualizations

The project includes comprehensive visualizations:

1. Elbow Method Plot - Optimal K selection
2. Silhouette Score Analysis - Cluster validation
3. 2D Scatter Plots** - RFM feature relationships
4. 3D Cluster Visualization - All dimensions with centroids
5. Box Plots - Distribution comparison across clusters
6. Heatmap - Normalized cluster characteristics
7. Radar Charts - Individual cluster profiles
8. Distribution Histograms - Feature distributions by segment
(Visualizations are generated in the Jupyter notebook)

---

 💼 Business Recommendations

 1. Prioritize High-Value Segments
- Allocate 29% of marketing budget to Cluster 3 (VIP Champions)
- Allocate 37% to Cluster 1 (Loyal Customers)
- These two segments drive 66% of total revenue

 2. Segment-Specific Campaigns
- VIP Champions: Exclusive experiences and premium services
- Loyal Customers: Loyalty rewards and personalized offers
- Potential Customers: Frequency-building promotions
- At-Risk Customers: Aggressive win-back campaigns

 3. Resource Optimization
- Focus retention efforts on Clusters 1 and 3
- Growth initiatives for Cluster 2 (largest segment)
- Evaluate cost-effectiveness of re-activating Cluster 0

 4. Personalization Strategy
- Tailor messaging based on segment characteristics
- Implement dynamic pricing strategies
- Create segment-specific product recommendations

 5. **Performance Monitoring
- Track segment movement over time
- Monitor customer lifecycle transitions
- A/B test strategies within segments

---

 🛠️ Technologies Used

| Category | Technologies |
|----------|-------------|
| Language | Python 3.8+ |
| Data Manipulation | Pandas, NumPy |
| Machine Learning | Scikit-learn (K-Means, StandardScaler) |
| Visualization | Matplotlib, Seaborn |
| Development Environment** | Jupyter Notebook / Google Colab |
| Version Control | Git, GitHub |

---

📁 Project Structure

```
Arch_Technologies_Task/
│
├── data/
│   └── online_retail.xlsx          # Raw dataset
│
├── notebooks/
│   └── customer_segmentation.ipynb # Main analysis notebook
│
├── results/
│   ├── customer_segmentation_results.csv  # Segmented customer data
│   └── visualizations/             # Generated plots and charts
│
├── requirements.txt                # Python dependencies
├── README.md                       # Project documentation
└── LICENSE                         # MIT License
```

---

 🚀 How to Run

 Option 1: Local Environment

1. Clone the repository
```bash
git clone https://github.com/yourusername/customer-segmentation-analysis.git
cd customer-segmentation-analysis
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Download the dataset
- Download from [UCI Repository](https://archive.ics.uci.edu/static/public/352/online+retail.zip)
- Extract to `data/` folder

4. Run the notebook
```bash
jupyter notebook notebooks/customer_segmentation.ipynb
```

 Option 2: Google Colab

1. Open the notebook in Google Colab
2. Upload the dataset when prompted
3. Run all cells sequentially

---

 📝 Key Learnings

 Technical Skills Developed:
✅ Unsupervised machine learning (K-Means clustering)  
✅ RFM analysis for customer segmentation  
✅ Feature engineering and data preprocessing  
✅ Model evaluation metrics (Silhouette Score, Davies-Bouldin Index)  
✅ Advanced data visualization techniques  
✅ Business intelligence and actionable insights generation  

 Business Skills Developed:
✅ Customer lifetime value estimation  
✅ Marketing strategy development  
✅ Budget allocation optimization  
✅ Stakeholder communication  

---

 👤 Author

Mohammed Abdulrafiu Omotosho
- LinkedIn: [Your LinkedIn Profile]
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: abdulrafiumohammed2019@gmail.com

Internship Program: Arch Technologies  
Project Duration: [01/10/2025] - [30/11/2025]

---

 🙏 Acknowledgments

- Arch Technologies for providing this learning opportunity
- UCI Machine Learning Repository for the dataset
- Scikit-learn community for excellent documentation
- Special thanks to my mentors and colleagues at Arch Technologies

---

📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.



 📞 Contact & Feedback

Have questions or suggestions? Feel free to:
- Open an issue on GitHub
- Connect with me on LinkedIn
- Send me an email

⭐ If you found this project helpful, please consider giving it a star!

---

🔮 Future Enhancements

- [ ] Implement hierarchical clustering for comparison
- [ ] Add time-series analysis for customer behavior trends
- [ ] Develop predictive models for customer churn
- [ ] Create an interactive dashboard using Streamlit/Plotly
- [ ] Incorporate additional features (product categories, geography)
- [ ] Automate segment monitoring and alerting system

---

Last Updated: November 2024

---



Made with ❤️ during my internship at Arch Technologies

[![GitHub followers](https://img.shields.io/github/followers/Omotosho-2579?style=social)](https://github.com/Omotosho-2579)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/abdulrafiu-mohammed-aislt-9ab4051ba/)


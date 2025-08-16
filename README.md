# Customer-Segmentation-for-UrbanCart-Retail-Unsupervised-Learning-K-Means-Clustering-PCA-Approach
This project presents a comprehensive customer segmentation analysis for **UrbanCart Retail Chain**.  By applying **unsupervised machine learning (K-Means Clustering)** and enhancing the model with **Principal Component Analysis (PCA)**, this study transforms raw transactional and demographic data into actionable business intelligence.

The primary goal is to group customers into distinct segments, enabling UrbanCart to move from a one-size-fits-all strategy to one that is data-driven, personalized, and efficient.

- **Business Focus**: Retail Analytics & Marketing Strategy
- **Data Science Focus**: Unsupervised Learning, Clustering, Dimensionality Reduction

---

##  Business Problem & Objectives

UrbanCart operates across 50 locations but struggles to understand the diverse preferences and behaviours of its customers. Despite collecting rich data, they lack a systematic way to leverage it for strategic advantage.

The key objectives were to:
1.  **Segment Customers**: Group customers into meaningful clusters based on their purchasing habits and demographics.
2.  **Profile Segments**: Understand and interpret the unique characteristics of each customer group.
3.  **Drive Strategy**: Provide actionable recommendations to personalize marketing campaigns, optimize product inventory, and enhance customer loyalty programs.

---

## Dataset Summary

The analysis was performed on a dataset containing the following customer attributes:

| Feature | Description | Data Type |
| --- | --- | --- |
| `Age` | Customer's age in years. | Numerical |
| `AnnualIncome` | Customer's annual income in USD. | Numerical |
| `SpendingScore` | A score (1-100) assigned based on spending behaviour. | Numerical |
| `PurchaseFrequency` | The average number of purchases made per month. | Numerical |
| `AverageBasketSize` | The average amount spent per transaction in USD. | Numerical |
| `PreferredCategory` | The customer's most frequently purchased product category. | Categorical |
| `Gender` | Customer's gender (Male/Female). | Categorical |
| `LoyaltyPoints` | Points accumulated through loyalty programs. | Numerical |

---

## Methodology & Workflow

The project followed a structured data science workflow, from data preparation to model deployment and interpretation.

#### 1. Data Preparation & Cleaning
- The dataset was loaded and inspected for missing values; none were found.
- Irrelevant identifiers (`CustomerID`) and features with potential data leakage or high correlation with other metrics (`LoyaltyPoints`) were dropped.
- **Categorical Encoding**: `Gender` and `PreferredCategory` were converted to numerical format using `sklearn.preprocessing.LabelEncoder`.
- **Feature Scaling**: All numerical features were standardized using `sklearn.preprocessing.StandardScaler` to ensure that distance-based algorithms like K-Means perform accurately.

#### 2. K-Means Clustering Analysis
- **Finding Optimal Clusters**: The **Elbow Method** and **Silhouette Score** were used to determine the optimal number of clusters. Both methods indicated that **k=4** was the ideal number, providing the best balance between inertia and cluster separation.

  
- **Initial Model**: A K-Means model with 4 clusters was trained on the preprocessed dataset.

#### 3. Performance Enhancement with PCA
To improve model performance and reduce dimensionality, **Principal Component Analysis (PCA)** was applied.
- **Dimensionality Reduction**: The analysis of the cumulative explained variance showed that **3 principal components** retained over **90%** of the original information, reducing the feature space from 7 to 3.

  
- **Improved Cluster Separation**: The Silhouette Score significantly improved after applying PCA, increasing from **0.67** to **0.75**, which indicates better-defined and more distinct clusters.
- **Visualization**: Reducing the data to two principal components allowed for a clear 2D visualization of the customer segments, confirming their separation.

  
---

## Cluster Profiles & Business Insights

The analysis revealed four distinct customer personas, each with unique behaviours and needs:

| Cluster | Persona | Key Characteristics |
| :--- | :--- | :--- |
| **Cluster 0** | **High-Value Spenders** | Characterized by high annual income, high spending scores, and high purchase frequency. These are UrbanCart's most valuable and loyal customers. |
| **Cluster 1** | **Budget-Conscious Regulars** | Low-income and low-spending individuals who are price-sensitive but shop with moderate frequency. They primarily purchase groceries and essentials. |
| **Cluster 2** | **Young & Occasional Buyers** | Younger customers with moderate income and high spending scores but low purchase frequency. They are likely trend-conscious and make occasional high-value purchases in luxury or electronics. |
| **Cluster 3** | **Mid-Tier Shoppers** | This group has moderate annual income, spending scores, and purchase frequency, representing the average UrbanCart customer. |

---

## Strategic Recommendations

Based on the cluster profiles, the following data-driven strategies are recommended:

1.  **For High-Value Spenders (Cluster 0)**:
    * **Marketing**: Implement a VIP loyalty program with exclusive perks, early access to new products, and personalized high-end offers.
    * **Inventory**: Ensure premium and high-margin products are well-stocked.

2.  **For Budget-Conscious Regulars (Cluster 1)**:
    * **Marketing**: Target with value-based promotions, discounts on bulk purchases, and cashback offers on essential items.
    * **Loyalty**: Design a points system that rewards frequency over basket size.

3.  **For Young & Occasional Buyers (Cluster 2)**:
    * **Marketing**: Re-engage this segment with trendy, limited-time offers and marketing campaigns focused on luxury and electronics.
    * **Inventory**: Stock the latest gadgets and luxury items to attract their high-spending potential.

4.  **For Mid-Tier Shoppers (Cluster 3)**:
    * **Marketing**: Use this segment for A/B testing new promotions and upselling campaigns to encourage higher spending and increase visit frequency.

---

## Real-Time Application

To demonstrate practical application, the trained **K-Means model**, **StandardScaler**, and **LabelEncoders** were saved using `pickle`. This allows for a real-time system where a new customer's data can be fed into the pipeline to instantly assign them to a predefined segment, enabling immediate marketing personalization.

**Example Prediction**:
A new customer with the profile: `{'Age': 30, 'AnnualIncome': 60000, 'SpendingScore': 75, 'PurchaseFrequency': 4, 'AverageBasketSize': 120, 'PreferredCategory': 'Luxury', 'Gender': 'Male'}` was correctly assigned to **Cluster 2 (Young & Occasional Buyers)**.

---

## Tools & Technologies

-   **Python 3.11**
-   **Pandas**: For data manipulation and analysis.
-   **Scikit-learn**: For K-Means Clustering, PCA, feature scaling, and model evaluation.
-   **Matplotlib & Seaborn**: For data visualization and creating insightful plots.
-   **Jupyter Notebook**: For interactive development and analysis.


## Repository Structure

```
 customer-segmentation-urbancart
├── customer_segmentation_dataset.csv
├── Case study - Unsupervised Learning (Clustering).ipynb
├── README.md
├── Customer Segmentation For Urban Cart Retail Chain - Clustering.pptx.pdf


## Personal Reflection

This project deepened my expertise in **unsupervised learning** and customer-centric analytics. As a Yoruba-born data scientist navigating the UK job market, I designed this case to mirror real business use-cases in retail. The ability to derive clusters that speak to behavioural economics and consumer psychology is something I find deeply fulfilling.

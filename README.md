# Amazon_E-Commence_Sales
this is my 2nd project with Quantum Analytics

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Recommendations](#recommendations)

### Project Overview
---

**Project Overview: Amazon Product Ratings and Reviews Analysis**  

This project leverages a dataset containing detailed information on over 1,000 Amazon products, focusing on their **ratings and customer reviews**. Amazon, a leading American multinational technology company, has revolutionized e-commerce by managing inventory, shipping, pricing, customer service, and returns, making it a trusted platform for global consumers.  

### Objectives:  
- **Customer Sentiment Analysis**: Analyze customer reviews to uncover sentiments, recurring themes, and factors influencing satisfaction or dissatisfaction.  
- **Ratings Insights**: Examine product ratings to identify patterns and correlations with product categories, pricing, and customer reviews.  
- **Product Performance Evaluation**: Identify top-performing products and those requiring improvement based on user feedback.  
- **Consumer Behavior Trends**: Explore how customers interact with product reviews and ratings, providing insights into purchasing decisions.  

### Value of the Dataset:  
This dataset is a treasure trove for:  
- **E-commerce Analysts**: Understanding customer preferences and pain points to enhance the shopping experience.  
- **Marketers and Sellers**: Gaining insights into product performance to refine strategies for product placement, pricing, and advertising.  
- **Data Enthusiasts**: Offering opportunities to create engaging visualizations and actionable insights from real-world data.  

### Potential Use Cases:  
1. **Sentiment Visualization**: Develop word clouds or sentiment charts to highlight common themes in customer reviews.  
2. **Rating Distribution Analysis**: Visualize and analyze the distribution of ratings across various product categories.  
3. **Review Length and Sentiment Correlation**: Explore how the length of a review relates to its sentiment or rating.  
4. **Product Category Insights**: Identify categories with the highest and lowest average ratings to pinpoint consumer preferences.  
5. **Predictive Analysis**: Use machine learning to predict future ratings or review sentiment based on historical data.  

This project will provide valuable insights into consumer behavior and product performance on Amazon, empowering stakeholders to make data-driven decisions that enhance customer satisfaction and improve overall business strategies.

![Dashboard]![2 Amazon E-Commence Sales](https://github.com/user-attachments/assets/328f0d8c-5374-4c9a-8388-1967d94ba378)



### Data Sources

Amazon-Sales dataset: The primary dataset used for this analysis is the "Amazon-Sales-csv.csv" file, containing detailed information about AAmazon-Sales.

### Tools

- Excel - Data Cleaning
  - [Download here](https://microsoft.com)
- SQL Server - Data Analysis
- PowerBI - Creating reports


### Data Cleaning/Preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis

EDA involved exploring the sales data to answer key questions, such as:

- What is the overall sales trend?
- Which products are top sellers?
- What are the peak sales periods?

### Data Analysis

Include some interesting code/features worked with

**Top Performing Products by Rating**
```sql
SELECT product_id, product_name, category, AVG(rating) AS avg_rating
FROM products
WHERE rating IS NOT NULL
GROUP BY product_id, product_name, category
ORDER BY avg_rating DESC
LIMIT 10;
```

**Price vs. Rating Analysis**
```sql
SELECT product_id, product_name, actual_price, discounted_price, rating
FROM products
WHERE rating IS NOT NULL AND actual_price IS NOT NULL
ORDER BY actual_price DESC;
```

**Category Performance**
```sql
SELECT category, AVG(rating) AS avg_rating, COUNT(product_id) AS product_count
FROM products
WHERE rating IS NOT NULL
GROUP BY category
ORDER BY avg_rating DESC;
```

**Discount Impact on Rating**
```sql
SELECT discount_percentage, AVG(rating) AS avg_rating
FROM products
WHERE discount_percentage IS NOT NULL AND rating IS NOT NULL
GROUP BY discount_percentage
ORDER BY discount_percentage DESC;
```

**Relationship Between Actual Price and Rating**
```sql
SELECT actual_price, AVG(rating) AS avg_rating
FROM products
WHERE actual_price IS NOT NULL AND rating IS NOT NULL
GROUP BY actual_price
ORDER BY actual_price DESC;
```

**Total Number of Reviews**

```sql
SELECT COUNT(DISTINCT review_id) AS total_reviews
FROM products;
```

**Rating Count**
```sql
SELECT SUM(rating_count) AS total_rating_count
FROM products
WHERE rating_count IS NOT NULL;
```

**Average Product Rating**
```sql
SELECT AVG(rating) AS avg_product_rating
FROM products
WHERE rating IS NOT NULL;
```

**Average Discount Percentage**
```sql
SELECT AVG(discount_percentage) AS avg_discount_percentage
FROM products
WHERE discount_percentage IS NOT NULL;
```


### Results/Findings

The analysis results are summarized as follows:

**Top Performing Products by Rating:**

The highest-rated products generally fall within the Electronics and Computer Accessories categories.
Top-rated products often have a moderate price range rather than extremely high or low prices.

**Price vs. Rating Analysis:**

No strong correlation was observed between product price and rating.
Some lower-priced products have received high ratings, suggesting value-for-money influences customer satisfaction.

**Category Performance:**

Electronics and Computer Accessories lead in average product ratings and customer engagement.
Some categories with high product counts have inconsistent ratings, indicating variable product quality.

**Discount Impact on Rating:**

Higher discount percentages often correlate with slightly higher ratings, suggesting customers appreciate deals.
However, the correlation isn't very strong, indicating other factors (e.g., product quality, brand reputation) play a role.

**Relationship Between Actual Price and Rating:**

Premium-priced products generally maintain higher average ratings.
Budget-friendly products still manage to secure high ratings in certain categories.

**Total Number of Reviews:**

The dataset contains a significant number of reviews, indicating active customer engagement.

**Rating Count:**

Products with higher rating counts often belong to popular categories like Electronics and Networking Devices.

**Average Product Rating:**

The overall average product rating indicates general customer satisfaction.

**Average Discount Percentage:**

On average, products offer a reasonable discount, with some categories being more discount-heavy.


### Recommendations

Based on the analysis, we recommend the following actions:

**Focus on Top Performing Categories:**

Invest more in promoting Electronics and Computer Accessories, as they consistently perform well.

**Optimize Pricing Strategies:**

Analyze price points of highly-rated products and adjust pricing strategies to match customer preferences.

**Discount Campaigns:**

Use targeted discount campaigns for moderately priced products to improve sales and customer satisfaction.

**Enhance Product Quality Across Categories:**

Focus on improving quality consistency in categories with mixed ratings.

**Encourage Customer Reviews:**

Products with more reviews tend to have better visibility and credibility. Encourage reviews through post-purchase engagement emails or loyalty programs.
### Limitations

**Data Completeness:**

Some missing values (e.g., ratings, prices) were imputed, which might affect precision.

**Time Frame:**

The dataset doesn’t include timestamps, limiting the ability to analyze trends over time.

**Limited Product-Specific Insights:**

While trends across categories are clear, individual product performance may require deeper analysis.

**Discount-Only Focus:**

The analysis assumes discounts and price heavily influence ratings, while other factors (e.g., product quality, delivery time) are not covered.

### References

`column_1`

**bold**

*italic*

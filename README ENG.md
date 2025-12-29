# User Retention Analysis – Online Retail Data  

## 1. Overview  
The goal of this project is to analyze user retention in online retail transaction data. After data cleaning, there are **352,079 transaction records** in the dataset. A cohort analysis is built to understand customer retention trends over time.  

## 2. Objective & Research Questions  
**Objective:**  
- Measure monthly customer retention rates.  
- Identify cohorts with the best and worst retention.  

**Research Questions:**  
- What are the retention patterns from the first month up to the 12th month?  
- Which cohorts demonstrate the highest retention rates?  
- What factors contribute to declining retention?  

## 3. Data Description  
- **Records:** 352,079 transactions after cleaning.  
- **Key Features:** order_id, product_code, product_name, quantity, order_date, price, customer_id, year_month, order_status, amount.  
- **Time Period:** Multi-year transaction data (example cohorts January–December 2010).  
- **Data Quality:**  
  - Missing values removed (customer_id & product_name).  
  - Outliers in quantity & amount filtered using z-score.  
  - Duplicates removed (6,411 rows).  

## 4. Key Steps  
- **Data Cleaning:** Remove missing values, duplicates, and outliers.  
- **Feature Engineering:** Create year_month, order_status, and amount columns.  
- **Standardization:** Ensure product_name consistency based on product_code.  
- **Cohort Analysis:** Build cohorts based on first transaction month, calculate retention rate per month.  

## 5. Methodology & Algorithms  
**Cohort Analysis Process:**  
- Aggregate transactions per customer per month.  
- Define cohort (first transaction month).  
- Calculate period_num (month distance from cohort).  
- Pivot table → unique customers per cohort & month.  
- **Retention rate = active customers / cohort size.**  
- Visualization: Retention rate heatmap per cohort.  

## 6. Evaluation Metrics  
- **Retention Rate:** Percentage of customers remaining active in month n after cohort start.  
- **Cohort Size:** Number of new customers in the first month.  

**Insights:**  
- Month 1 retention = 100% (baseline).  
- Sharp decline after month 2.  
- January 2010 cohort → 47% retention at month 12.  
- February 2010 cohort → only 22% retention at month 12.  
- June 2010 cohort → slight improvement at month 6 (32%).  

## 7. Visualization & Dashboard  
- **Retention Heatmap:** Shows declining retention trends across cohorts.  
- **Cohort Size Table:** Displays number of new customers per month.  

**Visual Insights:**  
- Early cohorts (Jan–Jun 2010) show stronger retention.  
- Later cohorts (Jul–Dec 2010) generally weaker retention.  

## 8. Limitations & Challenges  
- **Data Outliers:** Negative quantities (cancelled orders) → required transformation.  
- **Cohort Coverage:** Analysis limited to 2010.  
- **Missing Customer IDs:** 100,920 rows removed → potential loss of information.  

## 9. Future Work / Recommendations  
- Extend cohort analysis to later years.  
- Add segmentation by product categories.  
- Integrate clustering to profile customers within cohorts.  
- Build supervised churn prediction models.  

## 10. Business Impact  
- High-retention cohorts: Candidates for loyalty programs.  
- Low-retention cohorts: Primary targets for re-engagement campaigns.  
- **Key Insight:** Retention drops sharply after month 2 → need onboarding & early engagement strategies.  

## 11. Strategic Insights  
- **Retention Strategy:** Focus on cohorts with sharp retention decline (e.g., February 2010).  
- **Loyalty Programs:** Strengthen cohorts with stable retention (e.g., January 2010).  
- **Upselling & Bundling:** Encourage small-order cohorts to increase engagement.  
- **Conversion Optimization:** Reduce cart abandonment and optimize checkout to improve retention.  

## 12. Tools & Environment  
- **Python Libraries:** pandas, numpy, matplotlib, seaborn, scipy.  
- **Environment:** Google Colab for interactive analysis.  
- **Visualization:** Cohort retention heatmap using seaborn.  

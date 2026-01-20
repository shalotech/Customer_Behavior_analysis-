# Customer Shopping Behavior Analysis Project

This project analyzes consumer shopping patterns for a retail company to identify trends and optimize marketing strategies.

## Business Objective

The company wants to understand customer shopping behavior to improve sales, satisfaction, and loyalty by examining purchasing patterns across demographics, product categories, and sales channels.

## Dataset Overview

**3,900 customer transactions** with attributes including:
- Customer demographics (age, gender, location)
- Purchase details (item, category, amount)
- Behavior indicators (reviews, subscriptions, previous purchases)
- Transaction specifics (season, shipping, discounts, payment method)

## Data Preparation

### Cleaning Steps
1. **Column standardization**: Converted to snake_case naming
2. **Duplicate removal**: Dropped redundant `promo_code_used` column (identical to `discount_applied`)
3. **Missing values**: Filled 37 missing review ratings using category-based median imputation
4. **Feature engineering**:
   - Created `age_group` segments (Young Adult, Adult, Middle-aged, Senior)
   - Converted `frequency_of_purchases` to numeric `purchases_frequency_days`
   - Standardized "Every 3 Months" to "Quarterly"

## Key Analyses Performed

### 1. **Revenue Analysis**
- Male customers generated $157,890 (68% of revenue)
- Female customers contributed $75,191 (32% of revenue)

### 2. **Discount Effectiveness**
- 839 customers used discounts but still spent above average
- Hat (50%), Sneakers (49.66%), and Coat (49.07%) had highest discount usage rates

### 3. **Product Performance**
- Top-rated items: Gloves (3.86), Sandals (3.84), Boots (3.82)
- Most popular by category: Jewelry (Accessories), Blouse/Pants (Clothing), Sandals (Footwear), Jacket (Outerwear)

### 4. **Subscription Impact**
- Subscribers: 1,053 customers, $59.49 avg spend, $62,645 total revenue
- Non-subscribers: 2,847 customers, $59.87 avg spend, $170,436 total revenue
- **Finding**: Subscription status doesn't significantly impact spending

### 5. **Customer Segmentation**
- **Loyal** (>10 purchases): 3,116 customers (80%)
- **Returning** (2-10 purchases): 701 customers (18%)
- **New** (1 purchase): 83 customers (2%)

### 6. **Loyalty Patterns**
- Among repeat buyers (>5 purchases): 2,518 non-subscribers vs 958 subscribers
- **Insight**: High purchase frequency doesn't correlate strongly with subscription adoption

### 7. **Demographic Insights**
- Young Adults lead revenue: $62,143
- Middle-aged: $59,197
- Adults: $55,978
- Seniors: $55,763

### 8. **Shipping Preferences**
- Express shipping correlates with slightly higher spending ($60.48 avg)
- Standard shipping: $58.46 average

## Technical Stack

- **Python**: pandas for data manipulation
- **SQL**: MySQL for analytical queries via SQLAlchemy
- **Analysis Tools**: Aggregations, window functions, CTEs, case statements

## Strategic Recommendations

Based on the analysis, the company should:
1. Target young adults with tailored marketing campaigns
2. Investigate why subscription programs aren't attracting loyal customers
3. Optimize discount strategies for high-margin products
4. Leverage the large loyal customer base for retention programs
5. Focus on products with high ratings for promotional activities

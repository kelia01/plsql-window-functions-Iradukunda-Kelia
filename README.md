# Electronic_retail

## Step 1: Problem definition:
### Business Context:
- Company type: An e-commerce marketplace for electronic device parts (batteries, chargers, ...).
- Data challenge: Sales and Customer Experience.
- Industry: Electronics retail.
### Data Challenge:
Customers struggle to identify trustworthy sellers because many vendors sell similar products with different levels of reliability.
The company needs to analyze customer reviews, ratings, and sales data to rank sellers and products by trust level.
### Expected Outcome:
Use PL/SQL window functions to:
Rank sellers based on average ratings within each product category.
Identify top-rated products per region.
Show trends in review frequency over time.

The result will be a report that helps customers choose reliable sellers and motivates other vendors to improve quality.

## Step 2: Success criteria

### Top 5 most trusted sellers per product category/region → RANK()
Rank sellers based on average customer ratings or trust score within each category or region

### Running total of sales or reviews per seller per month → SUM() OVER()
Calculate cumulative sales or number of positive reviews for each seller to track reliability growth over time.

### Month-over-month change in seller ratings or sales → LAG()/LEAD()
Compare the current month’s average rating or sales to the previous month to identify improving or declining sellers.

### Customer engagement quartiles → NTILE(4)
Divide customers into 4 groups based on number of purchases or review frequency, to identify top buyers or highly active reviewers.

### 3-month moving average of seller ratings or sales → AVG() OVER()
Smooth out monthly fluctuations to track overall seller performance trends.

## Step 3: Database schema

| Table         | Purpose          | Key Columns                                                                | Example Row                           |
| ------------- | ---------------- | -------------------------------------------------------------------------- | ------------------------------------- |
| **customers** | Customer info    | `customer_id (PK)`, name, region                                           | 1001, Jose Mutoni, Kigali                |
| **sellers**   | Seller info      | `seller_id (PK)`, name, trust\_score, region                               | 2001, TechParts Ltd, 4.6, Kigali      |
| **products**  | Product catalog  | `product_id (PK)`, seller\_id (FK), name, category                         | 3001, 2001, Battery Pack, Electronics |
| **reviews**   | Customer reviews | `review_id (PK)`, customer\_id (FK), seller\_id (FK), rating, review\_date | 4001, 1001, 2001, 5, 2025-01-15       |







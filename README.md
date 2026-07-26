# Customer Shopping Behavior Analysis

End-to-end analysis of retail customer shopping behavior — data cleaning in Python, business analysis in SQL, and an interactive dashboard in Power BI.

**Workflow:** CSV → Python (cleaning) → PostgreSQL (SQL analysis) → Power BI (dashboard)

## Files

| File | Description |
|---|---|
| `customer_service.ipynb` | Cleans data, handles nulls, creates `age_groups` & `purchases_frequency`, loads data into PostgreSQL |
| `customer_behavior_analysis.sql` | SQL queries answering key business questions (revenue, discounts, products, shipping, subscriptions, segmentation) |
| `dashboard_customer_behavior.pbix` | Power BI dashboard visualizing all insights |

## Data Cleaning Highlights

- Filled missing `review_rating` with category-wise median
- Standardized column names to lowercase snake_case
- Dropped redundant `promo_code_used` column
- Binned `age` into `age_groups`: young_adult, adult, middle_aged, senior
- Mapped `frequency_of_purchases` to numeric `purchases_frequency` (days)
- Loaded cleaned data into PostgreSQL via SQLAlchemy

## Key Business Questions (SQL)

1. Revenue by gender
2. Revenue by age group
3. Customers who used a discount but spent above average
4. Top 5 products by discount rate
5. Top 5 products by average review rating
6. Top 3 best-selling items per category
7. Avg purchase amount: Standard vs Express shipping
8. Avg spend & revenue: subscribers vs non-subscribers
9. Repeat buyers (5+ purchases) by subscription status
10. Customer segmentation: New / Returning / Loyal

## Power BI Dashboard

`dashboard_customer_behavior.pbix` turns the SQL findings into an interactive report, including:

- **Revenue overview** — total revenue by gender, age group, and category
- **Product insights** — top-selling items, average ratings, discount rates
- **Shipping & subscription comparison** — spend patterns across shipping types and subscription status
- **Customer segments** — breakdown of New, Returning, and Loyal customers
- **Slicers/filters** — for gender, category, shipping type, and subscription status to explore the data interactively
- <img width="665" height="376" alt="Screenshot 2026-07-27 031211" src="https://github.com/user-attachments/assets/08713daa-e727-4e2a-a30a-87cff5e160fa" />
  DASHBOARD


Connects directly to the PostgreSQL `customer` table for live/refreshable data.

## Tools

Python (pandas, SQLAlchemy) · PostgreSQL · Power BI

## Note

Notebook creates the age-bucket column as `age_groups`; SQL script references `age_group` — align column names before running.

## Author

Ayush

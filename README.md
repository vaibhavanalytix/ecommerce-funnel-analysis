# E-Commerce Purchase Funnel Analysis

## Problem Statement

E-commerce platforms typically assume a linear purchase funnel 
(view -> cart -> purchase) and design abandonment-recovery strategies 
around it. This analysis examines whether that assumption holds for 
this dataset, and segments user behavior across the funnel stages to 
identify the actual purchase paths users take - with the goal of 
informing where funnel optimization efforts (cart experience vs. 
direct-buy flow) would have the most impact.

## Dataset

- Source: [Kaggle - E-commerce Behavior Data](https://www.kaggle.com/) 
  (REES46 dataset by Wafaa EL Husseini)
- Scope: October 2019, ~1.05 million clickstream events (view/cart/purchase)
- Fields: event_time, event_type, product_id, category_id, category_code, 
  brand, price, user_id, user_session

## Key Findings

1. **The funnel is not sequential.** Purchases do not reliably follow 
   the cart step - a large share of buyers convert without ever adding 
   an item to cart.

2. **Direct purchases dominate.** Among 12,774 unique purchasers, 62.54% 
   bought without ever adding an item to cart (Direct Buy: 7,963 users) - 
   nearly double the users who completed the full view -> cart -> purchase 
   path (4,782 users).

3. **"Add to cart" is a weak signal in this dataset.** Traditional cart 
   abandonment strategies would misrepresent actual buyer behavior here, 
   since most conversions bypass the cart entirely - likely through 
   direct/"buy now" purchase flows.

4. **Total revenue generated in the month:** $5,566,814 (from 12,774 
   purchase transactions), with electronics - smartphones as the leading 
   category by purchase volume.

5. **Data quality:** category_code was missing in 31.9% of all events. 
   Even among completed purchases, 3,692 transactions had no category 
   recorded — retained as "unknown" rather than dropped, to preserve 
   valid transaction records.

## Business Implication

Since most buyers convert without using the cart, investment in "cart 
recovery" campaigns (e.g., abandoned cart emails) may yield limited 
return. Effort may be better directed toward optimizing the 
direct-purchase flow and understanding what drives users to skip the 
cart entirely.

## Tools Used

- **Python** (pandas, numpy) - data cleaning and exploratory analysis
- **Jupyter Notebook** - exploration and documentation
- **Power BI** - interactive dashboard with DAX measures

## Project Structure
ecommerce-funnel-analysis/


├── data/              # raw dataset (not pushed - see .gitignore)

├── notebooks/         # exploration notebook (01_exploration.ipynb)

├── outputs/           # cleaned dataset export

├── dashboards/        # Power BI dashboard (.pbix)

└── README.md


## Dashboard

*Interactive dashboard with KPIs, funnel segmentation, category/brand 
breakdowns, and a Summary/Dashboard toggle view.*

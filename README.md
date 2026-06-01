# Task-2-Waliyullahi-Akorede-Husain
Repository for Task 2

# Decodelabs Internship Diary: Project 2 – Exploratory Data Analysis (EDA)

Data is rarely what it seems at first glance. Following the data cleaning phase, I advanced to **Exploratory Data Analysis (EDA)** on the Decodelabs sales dataset (1,200 orders across 1,189 unique customers). 

While surface-level metrics initially hinted at a business in a downward manner, building out targeted **Excel Pivot Tables** and deep-diving into the distributions revealed a completely different story. 

---

## Tech Stack & Methodology
* **Excel Pivot Tables & Pivot Charts** (Granular aggregation and trend analysis)
* **Feature Engineering** (Custom categorical binning for behavioral mapping)
* **Descriptive Statistics** 

---

## Key Business Insights 

### 1. Gross Revenue & Net Revenue

* High-level summary cards showed an impressive **Gross Revenue of $1.3M**.
* Breaking down metrics by `OrderStatus` revealed that actual cash in the bank (Net Revenue from *Delivered* & *Shipped* orders) was only **$489K**. 
* A staggering **$520K** was classified as *Non-Realized Revenue* due to cancellations ($276K) and returns ($243K). This points to an immediate operational or supply-chain crisis rather than a marketing problem.

### 2. High-Value Carts vs. Low Customer Retention
* The dataset boasts a massive **Average Order Value (AOV) of $1,000**, proving customers are highly committed to premium, big-ticket carts. 
* With 1,189 unique customers generating 1,200 orders, the customer purchase frequency sits at a near-flat **1.009**. Customers are buying high-value items once and never returning.

### 3. False Revenue Collapse in the Third Year 
* A yearly trend analysis showed total gross revenue dropping from **$553K in 2023** to **$232K in 2025**—a surface-level crash of over 50%.
* By drilling down into quarters and months, I discovered that the 2025 data abruptly stops in June (Q2). The business wasn't collapsing, the data collection for the year was simply cut off midway through.

---

## Feature Engineering 

To understand purchasing behavior deeply, I engineered a new feature by grouping `ItemsinCart` into distinct **Cart Sizes**:
* **Small:** 1–3 items
* **Medium:** 4–6 items
* **Large:** 7+ items

While **Large carts** drove the highest gross revenue, they also contributed heavily to cancellations. 

#### The Uniform Distribution Phenomenon
During cross-tabulation, the pivot tables revealed a highly uniform, near-perfect split across multiple variables—a critical pattern noted for downstream modeling:
* Revenue lost to cancellations was identical between Large and Medium carts ($121.6K each).
* Coupon codes split almost perfectly into ~25% buckets across the board (`FREESHIP`: 313, `NO COUPON`: 309).
* Sales revenue across seven entirely different product categories was virtually identical, with a mere $8 difference between Chairs ($195.6K) and Printers ($195.6K).
* Net revenue split evenly into ~20% buckets for each payment method.

---

EDA isn't just about charting data; it's about interrogation. 

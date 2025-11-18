# Data-Analyst-Task4
Task 4 – DASHBOARD CREATION 
# Myntra E-Commerce Product Analysis Dashboard

## Project Overview

This project focuses on developing an interactive Power BI dashboard using web-scraped e-commerce product data from Myntra. The core objective is to transform raw product data into actionable business intelligence, providing management with clear insights into brand performance, pricing strategies, and customer engagement within the **Jeans/Pants** product category.

---

## 1. Project Details

| Key Metric | Value |
| :--- | :--- |
| **Data Source** | `myntra_dataset_ByScraping.csv` (Web Scraped) |
| **Analysis Tool** | Microsoft Power BI Desktop |
| **Project Owner** | NARKHEDE OM RAHUL |
| **Role** | Data Analyst Intern |
| **Company** | Elevate Labs |

---

## 2. Dashboard Structure and Insights

The dashboard is structured to facilitate data-driven decision-making, offering filtering capabilities by Brand and Price Range.

### Key Performance Indicators (KPIs)
The top section of the dashboard features three key performance indicators:
* **Avg Rating:** Measures overall product quality perceived by customers.
* **Total Ratings:** Sum of all customer feedback, indicating market penetration and popularity.
* **Avg Discount:** The typical discount percentage offered across the inventory.

### Core Visualizations
| Visual Name | Purpose | Data Fields Used |
| :--- | :--- | :--- |
| **Top Brands by Total Ratings** | Identifies the brands with the highest customer engagement and popularity. | `brand_name` vs. **`Total Ratings`** (DAX Measure) |
| **Avg Price vs. Brand** | Compares the average selling price across different brands. | `brand_name` vs. **Average of `price`** |
| **Pricing vs. Quality Scatter Plot** | Examines the correlation between a product's average price and its average customer rating. | Average of `price` vs. Average of `ratings` |
| **Discount Distribution** | Visualizes the proportion of inventory falling into different discount buckets. | **Count of Products** vs. Discount Buckets |

---

## 3. Data Preparation Steps (Power Query - Phase 1)

The following transformations were executed in the Power Query Editor to clean and shape the data:

1.  **Data Type Conversion:** Ensured all numerical columns (`price`, `MRP`, `ratings`, etc.) were set to appropriate numerical types for calculation.
2.  **Missing Value Handling:** Rows with null or zero values for `ratings` or `number_of_ratings` were filtered out to prevent skewing of average calculations.
3.  **Custom Column Creation:** A new feature, **`discount_amount`**, was created to show the absolute monetary discount (`[MRP] - [price]`).

---

## 4. DAX Measures (Phase 2)

The following Data Analysis Expressions (DAX) were defined to enable dynamic and aggregated analysis within the model:

| Measure Name | DAX Formula | Description |
| :--- | :--- | :--- |
| `Avg Rating` | `AVERAGE('myntra_dataset'[ratings])` | Calculates the arithmetic mean of product ratings. |
| `Total Ratings` | `SUM('myntra_dataset'[number_of_ratings])` | Calculates the aggregate volume of customer feedback. |
| `Avg Discount` | `AVERAGE('myntra_dataset'[discount_percent])` | Calculates the mean discount percentage. |

---

## 5. Setup and Usage Instructions

### Prerequisites
* Microsoft Power BI Desktop (Latest Version Recommended)

### Steps to View the Dashboard
1.  Download the Power BI file (`[Project_Name].pbix` file).
2.  Open the file using **Power BI Desktop**.
3.  The data will automatically load from the embedded `myntra_dataset_ByScraping.csv` file.
4.  Navigate to the main **Report View** tab. Use the **Slicers** on the dashboard to filter by `Brand` or `Price Range` and observe the real-time interaction of the visualizations.

---

**© 2024 Elevate Labs | NARKHEDE OM RAHUL**

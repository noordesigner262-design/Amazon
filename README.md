# Amazon Sales Analysis Dashboard

## 📌 Overview
An interactive Power BI dashboard built on 128,976 Amazon sales orders (Kaggle dataset, 31 Mar 2022 to 29 Jun 2022). It lets users explore total sales, sales by city and state, daily sales trends and individual product performance in one place.

**Business question:** Where do sales come from, when do they peak, and which products and categories drive them?

<img width="557" height="311" alt="overview" src="https://github.com/user-attachments/assets/6a1f34ac-22ca-434e-b585-6a7a6494b6a0" />

<img width="519" height="292" alt="product_view" src="https://github.com/user-attachments/assets/180d3f8b-89e0-402a-a39d-25897126a05e" />

<img width="521" height="289" alt="Product_page" src="https://github.com/user-attachments/assets/94c9124f-23ea-497f-98ce-58d836c91764" />



## 📂 Project Structure
```
├── [dataset_name].csv          # Raw Kaggle dataset
├── [queries].sql               # SQL queries used for [what you used SQL for]
├── Amazon_Dashboard.pbix       # Power BI dashboard
├── overview.png                # Overview page screenshot
├── product_page.png            # Product gallery screenshot
├── product_view.png            # Product detail screenshot
├── README.md                   # Project documentation
```

## 📊 Dataset
- **Source:** Kaggle
- **Size:** 128,976 orders
- **Period:** 31 Mar 2022 to 29 Jun 2022
- **Key fields:** Order ID	Date	Status	Fulfilment	Sales Channel 	ship-service-level	Style	SKU	Category	Size	ASIN	Courier Status	Qty	currency	ship-city	ship-state	ship-postal-code	ship-country	fulfilled-by	

## 🔍 Methodology

### 1. Data Cleaning and Transformation (Power Query)
1.	Fixed the mismatch between the Feedback and Label columns (Corrected_Label) - Converted columns to correct data types (numeric vs text) - Checked for missing values (none found) and impossible values (none found in  Order ID	Date	Status	Fulfilment	Sales Channel 	ship-service-level	Style	SKU	Category	Size	ASIN	Courier Status	Qty	currency	ship-city	ship-state	ship-postal-code	ship-country	fulfilled-by)
2.	Standardized Amazon Prime y on n (brand	colour	delivery_type	discount_percentage	large	left_in_stock	no_of_reviews)



### 2. SQL
Data Extraction AND joining column for analysis

### 3. Data Modelling and DAX
- Created measures for total sales, units sold and seller count.
- Built a **dynamic Sales/Units toggle** using a disconnected table (`sales_option`) and `SELECTEDVALUE`, so users can switch every KPI between revenue and quantity with one click.

### 4. Dashboard Design
| Page | What it shows |
|---|---|
| **Overview** | KPI cards (total sales, filtered sales, seller count), order-status filter, sales by city, sales by state, daily sales trend |
| **Product** | Product gallery with category search |
| **Product View** | Drill-through for one product: total amount, units, remaining units, reviews, monthly sales trend, date range slicer |
| **Product Tooltip** | Hover tooltip with quick product details |

**Interactive features:** category search box, order-status filter, date slicer, Sales/Units toggle, product drill-through.

## 📈 Key Insights
- **Total sales:** 102.24M across 128,976 orders and 188 sellers. 
- **Regional concentration (clothing view):** Maharashtra (0.16M), Karnataka (0.13M) and Telangana (0.10M) are the top states, and Bengaluru (87K), Hyderabad (83K) and Mumbai (59K) are the top cities. The top 3 states account for roughly 44% of clothing sales.
- 
- **Sales trend:** Daily sale Trend: 27 April: 23,389 sales
- **Order status:** Cancelled:	5845, 
Pending: 678, 
Pending - Waiting for Pick Up:	291, 
Shipped:	80590

- **Top categories:** Women Kurta = 15,459 sales

## 💡 Business Recommendations
- Plan inventory and promotions region-wise, focusing on the top states and cities.
- Prepare stock ahead of the peak sales dates seen in the trend chart.
- Investigate cancelled and returned orders to reduce lost revenue.

## 🛠️ Technologies Used
- Power BI Desktop (DAX, Power Query)
- SQL
- Microsoft Excel

## ⚠️ Limitations
- The data covers only about 3 months, so seasonal patterns cannot be judged.


## 📌 Future Improvements
- Add profit and margin analysis if cost data is available
- Add customer and return-rate analysis
- Publish the dashboard to Power BI Service with a public link

# Super Store Sales Analysis-Dashboard


## 📊 Project Overview

The **Super Store Analysis** dashboard visualizes critical data to help stakeholders make informed decisions. Key metrics include:

- **Sales Performance**: Analysis of revenue trends across regions, product categories, and time.
- **Profit Analysis**: Identification of high- and low-profit areas to optimize business strategies.
- **Customer Insights**: Evaluation of customer behavior and segmentation to enhance targeting.

![Screenshot 2024-12-19 171218](https://github.com/user-attachments/assets/eca68722-5efa-486e-91f0-322e31981cc7)
![Screenshot 2024-12-19 171233](https://github.com/user-attachments/assets/d76acd87-2ae2-4b67-bf94-09e1481b6006)

---

## 🚀 Project Objectives

1. **Visualize sales trends**: Understand patterns over time and across locations.
2. **Identify profit margins**: Highlight products or regions with the highest and lowest profitability.
3. **Customer analysis**: Segment customers based on buying behavior for better engagement strategies.

---

## 📂 Data Sources

The dashboard was created using the following dataset(s):
### Dataset Link : https://www.kaggle.com/datasets/bitricks/superstore-dataset


## 🛠️ Steps Followed

### 1. **Data Collection and Preparation**
   - Imported raw data into Power BI.
   - Performed data cleaning using Power Query to handle missing or     inconsistent values.
   - Normalized data for better analysis and visualization.

### 2. **Data Modeling**

 - Snap of Model View
 ![Screenshot 2024-12-19 190315](https://github.com/user-attachments/assets/72590c17-14ae-4710-89ee-d67dc112b3b4)

   - Established relationships between tables.
   - Created a dedicated Date table using DAX (Data Analysis Expressions) in order to  ensure more accurate, efficient, reusability aross reports,and insightful time-based analysis in the Power BI report.

   for creating new Date Table following DAX expression was written
   
   - Dates Table = ADDCOLUMNS(CALENDAR(MIN(Orders[Order Date]),MAX(Orders[Order Date])),"Start of Month",EOMONTH( [Date],-1)+1)
   - Month = FORMAT('Dates Table'[Date], "MMMM")
   - Year = YEAR('Dates Table'[Date])

   Snap of new Dates Table ,

![Screenshot 2024-12-19 174720](https://github.com/user-attachments/assets/f4bdf724-1d8e-4ace-9b09-0a69b25b94eb)

   - Created calculated measures using DAX (Data Analysis Expressions) for metrics like:
     - Orders Count
     - Total Sales
     - Profit Margins
     - Average Order Value per Customer 
     - Returned Orders %
     - Products 
     - Total Customers

     - Key Metrics PY (Per year)
     
     - % Returned Orders PY :
        % returned orders PY = CALCULATE([Returned Orders %],SAMEPERIODLASTYEAR('Dates Table'[Date]))

     -  Profit PY :
        Profit PY = CALCULATE([Profit],SAMEPERIODLASTYEAR('Dates Table'[Date]))

     -  Sales PY :
          Sales PY = CALCULATE([Sales],SAMEPERIODLASTYEAR('Dates Table'[Date]))


     - Created calculated measures in order to get trend for yearto year (vs PY)
     - vs PY - % Returned Orders  :
     vs PY - %returned orders = [Returned Orders %] - [% returned orders PY]
  
     - vs PY - Profit  :
     vs PY - profit = DIVIDE([Profit] - [Profit PY],[Profit PY])
  
     - vs PY - Sales :
     vs PY - sales = DIVIDE([Sales] - [Sales PY],[Sales PY])



### 3. **Dashboard Creation**

**-Page 1**
   - Designed visualizations to highlight insights:

    - Card Visuals: Display key metrics such as customers, products, orders, revenue, profit, and average sales.
   - Filled Map Chart: Highlights sales distribution across regions.
   - Treemap: Visualizes the top customers based on sales contribution.
 - Clustered Bar Chart: Displays the top-performing products, lowest-selling products.
- Donut Chart: Shows the percentage distribution of orders by shipping methods.

**-Page2**
  - Designed visualizations to highlight insights:
  **Overall Performance**:
- KPI Visuals: Display metrics such as total sales ($2.3M), profit ($292.3K), and returned orders percentage (5.79%).

![kpis](https://github.com/user-attachments/assets/5facb0da-4aae-4a00-824d-943b896c1ebe)

**Sales by Segment**:
- Donut Chart: Visualizes the distribution of sales among different customer segments:
 - Consumer: 50.32%
 - Corporate: 30.77%
 - Home Office: 18.92%

**Profit by Product**:
- Clustered Bar Chart: Shows the profit or loss for individual product categories, such as tables with negative profit and copies generating $56.09K in profit.

**Sales vs. Previous Year Over Time**:
- Line Chart: Compares sales trends over time with the corresponding data from the previous year.


**Slicer Feature in the Dashboard**
- A slicer has been integrated into the Power BI dashboard to enhance interactivity and flexibility. This feature allows users to filter and analyze data dynamically based on specific criteria, such as:

- Year
- Date ranges
- Customer Name
- Product Segment
- Country
- Region

The slicer empowers users to customize their view and focus on specific data subsets, making the dashboard more user-friendly and adaptable to various analytical needs.

 Snap of Slicer Pane,
![Screenshot 2024-12-19 193701](https://github.com/user-attachments/assets/ea1b61be-a524-4ae4-9006-54cde8bd6511)


---
 ### 4. **Insights and Storytelling**
- Analyzed data to identify key patterns and trends:
**Seasonal Spikes**:
- Observed a consistent rise in sales during specific months, as depicted in the "Sales vs Previous Year Over Time" line chart.
**Low-Profit Products**:
- Highlighted underperforming product categories like "Tables" (negative profits), signaling a need for pricing or inventory adjustments.
**Integrated KPI indicators**:
- Sales Growth: Showcased as $2.3M, with a 47.16% improvement compared to the previous year.
- Profit Increase: Achieved $292.30K, a significant 48.85% rise year-over-year.
- Returned Orders: Monitored at 5.79%, with a slight decrease of 2.95% compared to the prior period.
- Visualized Segment Analysis through a donut chart, emphasizing Consumer (50.32%) as the highest contributor.

- Ensured insights were actionable and connected to potential strategies:
- Boosting high-performing segments like Technology.
- Addressing underperforming segments and products in Furniture.

### 5. **Publishing**
   - The report was then published to Power BI Service.
 ![Screenshot 2024-12-19 204710](https://github.com/user-attachments/assets/3d1ab545-02ea-41a8-b75b-09c62614a265)


---

## 📈 Key Features

- **Interactive Filters**: Dynamic filtering by region, category, and time period.
- **Trend Analysis**: Visual representation of key metrics over time.
- **Profitability Insights**: Highlighting areas of improvement.

---

## 🛠️ Tools and Technologies

- **Power BI Desktop**: For data modeling, transformation, and visualization.
- **Power Query**: For data cleaning and preparation.
- **DAX (Data Analysis Expressions)**: For creating measures and calculated columns.

---

## 🧩 Future Enhancements

- **Advanced Analytics**: Integration of machine learning models to predict future sales trends.
- **Real-Time Updates**: Linking with live data sources for real-time dashboards.
- **Expanded Metrics**: Adding customer satisfaction and retention analysis.

---

## 📜 How to Use

1. Clone this repository:
   ```bash
   git clone https://github.com/Raghava-Rohan/Sales-Analysis-PowerBI.git

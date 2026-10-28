# Business-Intelligence-Sales-profit-Analysis-Report
# Superstore Sales and Profit Performance Dashboard

## Project overview
This project uses **Microsoft Power BI** to explore historical Superstore sales and profitability from **2014–2017**. The dashboard is designed to help management compare performance across regions, customer segments, product categories and products, and identify opportunities to improve profit margins.


## Tools and files
- **Power BI Desktop:** Power Query for preparation, DAX for measures, and interactive visuals.

## Data cleaning and preparation

1. **Import:** Home → Get Data → Text/CSV → select the source file → Transform Data. Check the delimiter and character encoding.
2. **Inspect:** In Power Query, I enable **Column quality**, **Column distribution**, and **Column profile** under View. Check column names, row counts, nulls, errors and distinct values.
3. **Missing values:** Review key fields (`Order ID`, `Order Date`, `Sales`, `Profit`, `State`, `Category`). found **no missing values**.
4. **Duplicates:** I Checked identical rows and `Row ID` uniqueness. And found **zero  duplicated rows**.
5. **Data types:** Converted `Order Date` and `Ship Date` to Date (used an appropriate **MM/DD/YYYY locale**); `Sales`, `Profit`, and `Discount` to Decimal Number; `Quantity` and `Row ID` to Whole Number; identifiers, `Postal Code`, and categorical fields to Text.
6. **Text consistency:** Inspect fields such as `Region`, `State`, `Segment`, `Category`, and `Product Name`. 
7. **Validate:** Checked for new conversion errors, preserve the 9,994  rows, then **Close & Apply**.
8. **Date model:** Created a Date table; connect `Date[Date]` to `Superstore[Order Date]` (one-to-many). Sort `Month` by `Month Number` and `Year Month` by `Year Month Sort`.
9. **Measures:** Created the DAX measures below for the kpi

```dax
Total Sales = SUM(Superstore[Sales])
Total Profit = SUM(Superstore[Profit])
Total Orders = DISTINCTCOUNT(Superstore[Order ID])
Average Sales = DIVIDE([Total Sales], [Total Orders])
Profit Margin = DIVIDE([Total Profit], [Total Sales])
```


# Dashboard
<img width="797" height="451" alt="Super store executive summary" src="https://github.com/user-attachments/assets/1d3115d6-6894-4bcd-8ba7-6b8887deda8e" />

## Insights

### 1. What is the overall sales performance of the company?
**Answer:** Total sales were **$2,297,200.86**, total profit **$286,397.02**, across **5,009 distinct orders**. Average sales per order were **$458.61** and profit margin was **12.47%**. The business was profitable overall, but margin improvement remains important.

### 2. Which regions generate the highest sales and profit?
**Answer:** **West** leads in both sales (**$725,457.82**) and profit (**$108,418.45**), with a **14.94%** margin. **East** follows ($678,781.24 sales; $91,522.78 profit; 13.48% margin). **Central** has the weakest margin (**7.92%**) despite $501,239.89 sales; **South** has $391,721.91 sales and $46,749.43 profit. 

<img width="771" height="435" alt="Sales by Region" src="https://github.com/user-attachments/assets/6e102941-8f3a-4951-8606-388931f5dbd6" />


### 3. Which customer segments contribute the most revenue?
**Answer:** **Consumer 50.56%**, **Corporate 30.74%**, and **Home Office 18.70%** of sales. Consumer is the largest revenue segment; this chart does not establish which segment has the highest profit. 

<img width="779" height="446" alt="Sales By Customer Segment" src="https://github.com/user-attachments/assets/b33f6f40-9dd5-4f9b-8783-d3a545ffecf2" />


### 4. Which product categories perform best?
**Answer:** **Technology** leads in sales at about **$836.15K**, followed by **Furniture (~$742K)** and **Office Supplies (~$719.05K)**. These are revenue rankings; category profit and margin should be checked before concluding which is most profitable. 

<img width="772" height="440" alt="Sales By Product Category" src="https://github.com/user-attachments/assets/258aa84a-f2b7-4320-a451-1b4cc35eb2c2" />

### 5. Which products are the most profitable?
**Answer:** The leading product shown is the **Canon imageCLASS 2200 Advanced Copier (~$25.2K profit)**. It is followed by the **Fellowes PB500 Electric Punch Plastic Comb Binding Machine (~$7.75K)**, **Hewlett Packard LaserJet 3310 Copier (~$6.98K)**, **Canon PC1060 Personal Laser Copier (~$4.57K)**, and **HP Designjet T520 Inkjet Large Format Printer (~$4.09K)**. Names and values are rounded as displayed in the chart.

<img width="763" height="426" alt="Top 5 most profitable products" src="https://github.com/user-attachments/assets/3d569e34-8c35-46ca-8ac6-95d55f3053eb" />


### 6. What trends can be observed over time?
**Answer:** Monthly sales fluctuate substantially, but the broad pattern strengthens in later years, with a notable peak near the end of **2017**. The chart does not by itself prove why these fluctuations occurred.

<img width="775" height="443" alt="month and year sales trend" src="https://github.com/user-attachments/assets/1b9aab75-afb3-4a81-b0c5-5d97974f5f8d" />


### Reccommendation

1. **Investigate Central-region margins** and discounting (7.92% margin).
2. **Review loss-making states and sub-categories** through the drill-down matrix.
3. **Prioritise profitable Technology products** while tracking inventory and margins (Technology leads revenue).
4. **Improve Consumer retention** and test targeted Corporate/Home Office campaigns (Consumer is 50.56% of revenue).
5. **Conduct monthly performance reviews** using KPI cards and slicers to monitor sales, profit and margin by region and product.

## Key results
| KPI | Result |
| --- | ---: |
| Total sales | $2,297,200.86 |
| Total profit | $286,397.02 |
| Distinct orders | 5,009 |
| Average order value | $458.61 |
| Profit margin | 12.47% |

The **West** region had the highest sales and profit, while **Central** had the lowest regional margin (7.92%). **Consumer** accounted for 50.56% of revenue. **Technology** was the highest-revenue category. 



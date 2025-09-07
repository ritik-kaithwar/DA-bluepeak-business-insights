# BluePeak Enterprises — Sales & Profitability Insights  

> Comprehensive BI project combining **Power BI (DAX)** and **Python EDA** to uncover growth opportunities, manage concentration risk, and improve profitability.  

---

## Project Highlights  
- Built an **interactive BI solution in Power BI** for BluePeak Enterprises.  
- Analyzed **$1.19B revenue** across products, customers, and regions.  
- Conducted **EDA in Python** to validate drivers and trends.  
- Delivered dashboards for executives, product managers, and customer teams.  
- Generated actionable strategies to boost growth and margin efficiency.  

---

## Overview  
This project analyzes sales and profitability data for BluePeak Enterprises using **Power BI** and **Python**.  

The goals were to uncover:  
- Revenue drivers and performance gaps  
- Geographic and product concentration risks  
- Customer segment behavior  
- Actionable strategies for sustainable growth  

---

## Objectives  
- Evaluate sales performance across **regions, products, and customer segments**.  
- Build **DAX-driven KPIs** for revenue, profit, margins, and YoY trends.  
- Validate findings through **Python-based exploratory analysis**.  
- Deliver **dashboards** that support both high-level strategy and deep-dive analysis.  

---

## Data & Model  

**Tables (from metadata.xlsx)**  
- **FactSales** → Orders, revenue, profit, COGS, margins  
- **DimCustomer** → Customer details, segments  
- **DimProduct** → Product attributes  
- **DimGeography** → Region, state, county, coordinates  
- **DimDate** → Calendar table with Year, Month, Quarter  
- **OrderValueDistribution** → Helper table for order value bins  

**Relationships**  
- `FactSales[CustomerID] → DimCustomer[CustomerID]`  
- `FactSales[ProductID] → DimProduct[ProductID]`  
- `FactSales[GeoID] → DimGeography[GeoID]`  
- `FactSales[OrderDate] → DimDate[Date]`  

**Schema (Mermaid ER Diagram):**  
```mermaid
erDiagram
  DimCustomer ||--o{ FactSales : "CustomerID"
  DimProduct  ||--o{ FactSales : "ProductID"
  DimGeography||--o{ FactSales : "GeoID"
  DimDate     ||--o{ FactSales : "OrderDate"

  FactSales {
    int   OrderNumber
    date  OrderDate
    int   Quantity
    dec   UnitPrice
    dec   Revenue
    dec   TotalCost
    dec   COGS
    dec   TotalProfit
    dec   ProfitMargin
    int   CustomerID
    int   ProductID
    int   GeoID
  }

---

## Tools & Technologies  
- **Power BI** → data modeling, dashboard development  
- **DAX** → calculated KPIs, YoY growth, contribution analysis  
- **Python (Pandas, Matplotlib, Seaborn)** → exploratory analysis and validation  
- **Excel** → metadata and reconciliation  

---

## Methodology  

### Data Preparation (Python)  
- Consolidated raw dataset from **6 CSV sheets** into a single cleaned dataframe.  
- Handled missing values, standardized column names, and ensured data consistency.  
- Extracted **fact and dimension tables** (FactSales, Customers, Products, Geography, Date) from the final dataframe for modeling.  

### Data Cleaning & Validation  
- Checked consistency of revenue, orders, profit, and margins.  
- Validated calculations against raw dataset totals.  
- Ensured referential integrity across fact and dimension tables.  

### Exploratory Data Analysis (Python)  
- Analyzed monthly revenue trends and YoY comparisons.  
- Studied distributions of order values and unit prices.  
- Performed contribution analysis by product, region, and customer segments.  
- Built correlation heatmaps to uncover relationships between sales, cost, and profit drivers.  

### Data Modeling (Power BI)  
- Designed a **star schema** using extracted fact and dimension tables.  
- Built **DAX measures** for revenue, profit, profit margin, AOV, and COGS.  
- Created YoY growth and contribution % metrics for comparative analysis.  

### Dashboard Development (Power BI)  
- **Executive Overview** → high-level KPIs and overall trends.  
- **Product Performance** → top products, pricing distribution, and margin insights.  
- **Customer & Region Insights** → customer segmentation, regional contribution, and sales mix.  

### Insights & Recommendations  
- Converted findings into clear business implications and actionable strategies.  

---

## Key Insights  

### Regional Dependency  
- **Fact:** California generates **18.5% of revenue (~$220M)**.  
- **Implication:** Heavy reliance on one state → expansion in other regions needed to reduce risk.  

### Profit Margins  
- **Fact:** Margins steady at **~37% across years**.  
- **Implication:** Costs are controlled, but margin growth is capped → requires mix optimization or cost efficiency.  

### Revenue Trends  
- **Fact:** **Mar 2016** saw +8.5% YoY growth from higher orders; **Feb 2017** saw –8.2% dip from fewer orders.  
- **Implication:** Growth is volume-driven, not price-driven → demand generation is key.  

### Product Mix  
- **Fact:** Top 5 products = **36.5% of revenue (~$434M)**; **Product 25** is both high-revenue and high-margin.  
- **Implication:** Portfolio concentration risk; Product 25 is a “star” and should be leveraged further.  

### Customer Segments  
- **Fact:** “Low value” customers = **~45% of revenue**; top 5 customers <2%.  
- **Implication:** Broad low-value base is collectively important → upgrade opportunities exist; low single-customer dependency reduces risk.  

### Weekday vs Weekend  
- **Fact:** **72% of sales ($851M)** on weekdays vs **28% ($336M)** on weekends.  
- **Implication:** Untapped weekend demand → targeted offers could rebalance sales.  

---

## Recommendations  
1. **Trim COGS** → even a **1% reduction** could add ~$12M profit.  
2. **Boost weekend sales** → run targeted promotions, bundles, or campaigns.  
3. **Leverage Product 25** → promote heavily and bundle with related products.  
4. **Upgrade low-value customers** → cross-sell and upsell to shift them into higher tiers.  
5. **Diversify regions** → expand beyond California to reduce concentration risk.  

---

## Dashboard Preview  

### Executive Overview  
![Executive Overview](./images/executive-overview.jpg)  
*High-level KPIs (Revenue, Profit, Margin, Orders, AOV) with monthly YoY trends and regional breakdown for quick executive insights.*  

### Product Performance  
![Product Performance](./images/product-performance.jpg)  
*Revenue and margin contribution by top products, pricing distribution, and profitability analysis to identify high-value and high-risk SKUs.*  

### Customer & Region Insights  
![Customer & Region Insights](./images/customer-region-insights.jpg)  
*Customer segmentation (low vs high value), geographic revenue contribution, and state-level performance to uncover dependency risks and growth opportunities.*  

---

## Deliverables  
- Power BI Dashboard (`.pbix`)  
- Python EDA Notebook (`.ipynb`)  
- Metadata Schema (`metadata.xlsx`)  
- Business Report (`.pdf`)  

---

## Learnings  
- Combined **Python EDA** with **Power BI** modeling for a full analytics workflow.  
- Practiced converting data findings into **business strategy**.  
- Improved skills in **DAX measures**, **data storytelling**, and **dashboard design**.  

---

## Author  
**Ritik Kaithwar**  
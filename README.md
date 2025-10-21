# 🏠 Melbourne Housing Market Analysis (2016–2018)

## 🎯 Objective
Analyze Melbourne’s housing auction data to identify market trends, price behaviors, and top-performing suburbs.  
This project demonstrates data cleaning, transformation, and visualization using **Excel Power Query** and **dashboarding techniques**.

---

## 📂 Data Source
Original dataset: [Melbourne Housing Market Dataset – Kaggle](https://www.kaggle.com/datasets/anthonypino/melbourne-housing-market/data)
Data was imported from a CSV file and transformed using Power Query in Excel.

---

## ⚙️ Tools & Skills
- **Excel (Power Query, PivotTable, Dashboarding)**
- **Data cleaning & transformation**
- **Descriptive statistics**
- The project was inspired by [Macquarie University’s Data Visualization in Excel course on Coursera](https://www.coursera.org/learn/excel-data-visualization/home/info) and follows a similar—but not identical—dataset to apply and extend the techniques I learned there.
---

## 🧹 Data Cleaning Process

1. **Importing Data**
   - Imported CSV file into Power Query for transformation.

2. **Filtering Valid Records**
   - Kept only valid sale types:  
     - `S` (Sold)  
     - `SA` (Sold After Auction)  
     - `SP` (Sold Prior to Auction)  
   - These represent legitimate sale prices.

3. **Text Cleaning**
   - Trimmed and cleaned text fields.  
   - Removed "City Council" from the *Council Area* column for cleaner display.

4. **Date Formatting Issue**
   - Power Query couldn’t automatically detect date format (dd/mm/yyyy vs mm/dd/yyyy).  
   - Attempted multiple fixes:  
     - Adjusted Locale → UK (did not solve).  
     - Added column from examples (did not solve).  
     - Changed Windows regional setting → UK (✅ solved).  

5. **Duplicates Removal**
   - Grouped by `Address`, `Suburb`, `Date`, `Price`, and `Seller Agent` to detect duplicates.  
   - Found **7 duplicates** → removed.  
   - Row count reduced from **43,395 → 43,388** → then after null price removal → **37,464 rows**.

6. **Null Value Handling**
   - Removed rows with null prices (non-sale or incomplete data).

---

## 🔍 Data Exploration

### Extracted Columns
- **Year** and **Month** from Date for trend analysis.

### Data Gaps
- Missing data for **March 2016** and **January 2017** — verified and confirmed as absent from the source.

---

## 📊 Analysis & Key Findings

### 1. Price Trend (2016–2018)
- **Houses** remain the most expensive property type.  
- Prices peak around **March–June**, easing slightly mid-year.  
- **Townhouses** follow a similar seasonal curve.  
- **Units** are the most affordable and stable.  
- Overall trend reflects **seasonal peaks**:  
  - **Autumn (Mar–May)**  
  - **Spring (Sep–Nov)**
<img width="331" height="207" alt="image" src="https://github.com/user-attachments/assets/6a613688-8d3a-4120-bddc-912d83557bf1" />

### 2. Number of Properties Sold
- Sales volume peaks around **May** and again in **September–October**.  
- House sales dominate, with townhouses and units showing smaller but similar patterns.  
- Market activity is strongly **seasonal**, not random.
<img width="338" height="211" alt="image" src="https://github.com/user-attachments/assets/cb7bbe5d-3259-4ce9-97d6-38efb2193e85" />

### 3. Top 5 Suburbs per Council Area
- Interactive dashboard allows exploration of:
  - Most active council areas by total sales.  
  - Top-performing suburbs by **average price** and **volume**.

### 4. Average Price by Type, Suburb, and Month
- Dashboard visuals show how average prices evolve monthly across property types and locations.
- Enables year-over-year comparison to highlight growth or stability.

---

## 🖼️ Dashboard Preview
This dashboard provides an overview of Property sales in Melbourne between 2016-2018. It allows users to indentify top-performing sales at the council area and surburb levels, explore changes in price and compare averages prices across property types.
How to interact:
- Use the Year, Month, and Council Area slicers to filter the data.
- The KPI cards show the average prices and percentage change compared to the same month in the previous year.
- The bar chart highlights average suburb/council area prices of the top 8 suburb or council area.
- The line charts show monthly sales counts and average prices.
- The table lists the top 5 suburbs with the highest and lowest prices for each property type. The icons are interactive to select the property type (only works with Macro-enabled file).
<img width="1250" height="687" alt="image" src="https://github.com/user-attachments/assets/97aa30f3-923f-4af7-a2af-6dd5fb512c08" />


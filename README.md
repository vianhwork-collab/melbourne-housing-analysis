# 🏠 Melbourne Housing Market Analysis (2016–2018)

## 🎯 Objective
Analyze Melbourne’s housing auction data to identify market trends, price behaviors, and top-performing suburbs.  
This project demonstrates data cleaning, transformation, and visualization using **Excel Power Query** and **dashboarding techniques**.

---

## 📂 Data Source
Original dataset: *Melbourne Housing Dataset* (Kaggle).  
Data was imported from a CSV file and transformed using Power Query in Excel.

---

## ⚙️ Tools & Skills
- **Excel (Power Query, PivotTable, Dashboarding)**
- **Data cleaning & transformation**
- **Data analysis & storytelling**
- **Descriptive statistics**

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

### 2. Number of Properties Sold
- Sales volume peaks around **May** and again in **September–October**.  
- House sales dominate, with townhouses and units showing smaller but similar patterns.  
- Market activity is strongly **seasonal**, not random.

### 3. Top 5 Suburbs per Council Area
- Interactive dashboard allows exploration of:
  - Most active council areas by total sales.  
  - Top-performing suburbs by **average price** and **volume**.

### 4. Average Price by Type, Suburb, and Month
- Dashboard visuals show how average prices evolve monthly across property types and locations.  
- Enables year-over-year comparison to highlight growth or stability.

---

## 🖼️ Dashboard Preview
*(Add screenshots here after upload)*

Example:
```markdown
![Dashboard Overview](dashboard/screenshots/melbourne_dashboard_overview.png)
![Suburb Comparison](dashboard/screenshots/suburb_price_trend.png)

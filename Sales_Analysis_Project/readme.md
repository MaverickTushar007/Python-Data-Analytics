# 🛒 E-Commerce Sales Analysis — 12 Months of Transaction Data

This project is a complete **end-to-end analytics pipeline** built using Python.  
It analyzes **180,000+ e-commerce transactions** over a full year to uncover:

- Revenue trends  
- City-level performance  
- Consumer purchase timing  
- Product bundling patterns  
- Price–demand relationships  

The goal is to turn raw transactional data into **clear, actionable business insights** using data cleaning, feature engineering, exploratory data analysis (EDA), and visual storytelling.

---

## 🎯 Key Business Questions

1. **Which month generated the highest sales revenue?**  
2. **Which U.S. city had the strongest sales performance?**  
3. **What time of day is best for running advertisements?**  
4. **Which products are frequently bought together?**  
5. **Which products sell the most, and how does price affect demand?**

---

## 🛠 Tools & Technologies

### Python Libraries
- **Pandas** — Data cleaning, joining, and transformation  
- **Matplotlib** — Base visualizations  
- **Seaborn** — Enhanced charts and styling  
- **itertools**, **collections.Counter** — Market basket / bundling analysis  

### Environment
- **Jupyter Notebook** — Interactive analysis  
- **VS Code** — Development and organization  
- **Git & GitHub** — Version control and project tracking  

---

## 🧹 Data Preparation Workflow

To make the dataset analysis-ready, I performed the following:

### 1. Data Merging & Validation
- Combined **12 separate monthly CSV files** into a single DataFrame  
- Removed:
  - Duplicate header rows introduced during concatenation  
  - Corrupted or empty rows  

### 2. Feature Engineering
Created new columns to enable richer analysis:

- **`Month`** — extracted from `Order Date`  
- **`Hour`** — extracted from `Order Date` to study purchase time patterns  
- **`City`** — parsed from `Purchase Address` (e.g., `"San Francisco (CA)"`)  
- **`Sales`** — computed as `Quantity Ordered × Price Each`  

### 3. Data Type Fixes
- Converted `Order Date` to `datetime` format  
- Cast `Quantity Ordered` and `Price Each` to numeric types  

### 4. Bundle Analysis Setup
- Grouped rows by `Order ID`  
- Identified orders with multiple products to detect **frequently bought together** pairs

---

## 📊 Analysis & Insights

---

### 1️⃣ Best Month for Sales

**Goal:** Identify seasonal demand and revenue peaks.

I computed monthly revenue by aggregating `Sales` values per month.

#### 📈 Monthly Sales  
![Monthly Sales](Images/sales_per_month.png)

**Insight:**  
- **December** generated the highest revenue, with **> \$4.5M** in sales, driven by holiday-season demand.

---

### 2️⃣ Which City Generated the Highest Sales?

**Goal:** Understand which U.S. cities drive the most revenue.

I grouped total `Sales` by `City` and visualized the results.

#### 🏙️ Sales by City  
![Sales per City](Images/Sales_per_city.png)

**Insight:**  
- **San Francisco** led with **> \$8M** in annual revenue.  
- Large metropolitan and tech-focused cities (San Francisco, Los Angeles, New York) show significantly higher purchasing power.

---

### 3️⃣ Optimal Advertisement Timing

**Goal:** Identify the best times of day to show ads.

I used the `Hour` feature from `Order Date` to find purchase spikes.

**Peak purchase hours:**
- **11 AM**  
- **1 PM**  
- **7 PM**

**Insight:**  
- These time windows are the most effective for ad placement to maximize conversions.

---

### 4️⃣ Products Most Frequently Bought Together

**Goal:** Discover product combinations suitable for bundling and cross-selling.

Using `Order ID` to group multi-product orders and `itertools.combinations` to count product pairs:

**Common pairs include:**
- **iPhone + Lightning Charging Cable**  
- **Google Phone + USB-C Cable**  
- **MacBook Pro + USB-C Adapter**

**Insight:**  
- These pairings can be turned into product bundles or targeted cross-sell recommendations.

---

### 5️⃣ Which Products Sell the Most?

I aggregated `Quantity Ordered` per product.

#### 📦 Quantity Ordered per Product  
![Quantity Ordered](Images/Quantity.png)

**Insight:**  
- Low-cost accessories (e.g., batteries, charging cables) dominate in quantity sold.  
- Mid-range items like headphones and monitors also have strong volume.

---

### Price vs Quantity: Does Price Affect Demand?

To examine price elasticity, I overlaid price information.

#### 📈 Quantity vs Price  
![Price vs Quantity](Images/Price_vs_Quantity.png)

**Key Observations:**
- **Cheaper products → much higher sales volume.**  
- High-ticket items (e.g., MacBook Pro, ThinkPad) sell fewer units but contribute significantly to revenue.  
- Clear inverse relationship between product price and quantity sold for many SKUs.

---

## 📚 What I Learned

Through this project, I strengthened my skills in:

- Cleaning and preprocessing complex, real-world datasets  
- Engineering features from semi-structured text (addresses, date strings)  
- Performing **time-series** and **geographic** analysis  
- Using **market basket analysis** to identify bundles  
- Building dual-axis visualizations to compare price and volume  
- Presenting technical findings in a business-oriented, insight-first format  

---

## ⚠️ Challenges Faced

- Handling inconsistent and noisy rows across multiple CSV files  
- Parsing address fields reliably into city/state components  
- Ensuring consistent product naming across entries  
- Managing scale differences when overlaying quantity and price on the same chart  

These challenges led to a deeper understanding of real-world data issues and how to resolve them with Python.

---

## ✅ Conclusion

This project demonstrates how data analytics can reveal:

- **Seasonal trends** in customer purchases  
- **High-value geographic markets**  
- **Optimal advertisement timing**  
- **Product bundling opportunities**  
- **Price–demand relationships**  

It served as a full end-to-end practice in **Python-based data analytics**, from raw CSVs to business-ready insights, and is a core part of my data analytics portfolio.

---

## 📂 Project Structure

```bash
Sales_Analysis_Project/
│
├── Data/
│   ├── Sales_January_2019.csv
│   ├── Sales_February_2019.csv
│   ├── ...
│   └── Sales_December_2019.csv
│
├── Images/
│   ├── sales_per_month.png
│   ├── Sales_per_city.png
│   ├── Quantity.png
│   ├── Price_vs_Quantity.png
│   └── (other supporting charts)
│
├── Notebooks/
│   ├── 1_Merge_and_Clean_Data.ipynb
│   ├── 2_Monthly_Sales_Analysis.ipynb
│   ├── 3_City_Sales_Analysis.ipynb
│   ├── 4_Ad_Timing_Analysis.ipynb
│   ├── 5_Product_Bundling_Analysis.ipynb
│   └── 6_Product_Demand_and_Price.ipynb
│
├── requirements.txt
└── README.md

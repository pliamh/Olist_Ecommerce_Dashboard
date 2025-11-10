# Olist E-Commerce Dashboard

This project analyzes pricing, freight costs, and free-shipping behavior in the **Olist E-Commerce dataset (Brazil)**.  
Data was cleaned and processed in Python, then visualized in Tableau.

---

### 🔍 Dashboard Overview
- **Top-left:** Average Freight Cost by Product Category  
- **Top-right:** Orders per Product Category  
- **Bottom-left:** Relationship between Product Price and Freight Cost  
- **Bottom-right:** Free Shipping Orders by Product Category  

---

### 🧹 Data Preparation
The dataset was cleaned and exported from Python as:
`data_work/order_products_clean.csv`

Processing included:
- Merging orders, products, and shipping data  
- Fixing category names and filling missing values  
- Flagging free-shipping orders  
- Removing zero or invalid prices and freight values  

---

### 📊 Tools Used
- **Python:** pandas, numpy, matplotlib, scikit-learn  
- **Tableau:** dashboard design and visualization  

---

### 📁 Files
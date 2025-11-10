# Olist E-Commerce — Freight & Pricing Mini-Project

This mini-project cleans Olist order-line data (Brazil), builds a simple baseline to predict freight cost, and publishes a Tableau dashboard.

---

### 🔍 Dashboard Overview
- **Top-left:** Average Freight Cost by Product Category  
- **Top-right:** Orders per Product Category  
- **Bottom-left:** Price vs Freight by Category  
- **Bottom-right:** Free-Shipping Orders by Category  

See the image: [`reports/Olist_Ecommerce_Dashboard.png`](reports/Olist_Ecommerce_Dashboard.png)  
Open the workbook: [`reports/Olist_Ecommerce_Dashboard.twbx`](reports/Olist_Ecommerce_Dashboard.twbx)

---

### 🧹 Data Prep (Python)
Cleaned and exported in the notebook:
- [`notebooks/01_load_and_preview.ipynb`](notebooks/01_load_and_preview.ipynb)

Key steps:
- Merged orders, order_items, and products
- Translated/standardized categories
- Flagged free-shipping rows (freight_value == 0)
- Removed invalid zeros in price/freight; fixed tiny weight outliers
- Saved tidy output:
  - [`notebooks/data_processed/order_products_clean.csv`](notebooks/data_processed/order_products_clean.csv)
  - [`notebooks/data_processed/order_products_clean.parquet`](notebooks/data_processed/order_products_clean.parquet)

---

### 🧠 Baseline Model
- Features: price, category (one-hot), simple “order age” from purchase timestamp  
- Model: `LinearRegression`  
- Result: **MAE ≈ 7–8** (freight units) on hold-out split

---

### ⚙️ Reproduce (quick)
```bash
python -m venv .venv
.venv\Scripts\activate
pip install pandas scikit-learn matplotlib pyarrow
jupyter lab
# open and run: notebooks/01_load_and_preview.ipynb
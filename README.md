# 📊 Business Intelligence Datasets

A curated collection of business intelligence datasets designed for easy analysis with **Google Colab**, Jupyter, Power BI, Tableau, and any other tool that can read a CSV from a URL.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/getting_started.ipynb)

---

## 📁 Repository Structure

```
datasets/
├── sales/           sales_data.csv          – 100 sales transactions
├── customers/       customer_data.csv       – 50 customer profiles
├── finance/         financial_data.csv      – 11 quarters of P&L & cash flow
├── marketing/       marketing_data.csv      – 29 campaign performance records
└── supply_chain/    supply_chain_data.csv   – 50 procurement & inventory orders

notebooks/
└── getting_started.ipynb   – Interactive Colab/Jupyter starter notebook
```

---

## 📂 Datasets

### 🛒 Sales Data
**File:** `datasets/sales/sales_data.csv`

| Column | Description |
|--------|-------------|
| `order_id` | Unique order identifier |
| `order_date` | Date of the transaction |
| `customer_id` | Reference to customer |
| `product_id` | Reference to product |
| `product_name` | Product name |
| `category` | Product category (Electronics, Furniture, Software, Stationery) |
| `region` | Sales region |
| `sales_rep` | Sales representative name |
| `quantity` | Units ordered |
| `unit_price` | List price per unit (USD) |
| `discount` | Discount fraction applied |
| `revenue` | Net revenue after discount (USD) |
| `profit` | Net profit (USD) |

**Direct link (raw CSV):**
```
https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/sales/sales_data.csv
```

---

### 👥 Customer Data
**File:** `datasets/customers/customer_data.csv`

| Column | Description |
|--------|-------------|
| `customer_id` | Unique customer identifier |
| `first_name` / `last_name` | Customer name |
| `country` / `city` | Location |
| `age` / `gender` | Demographics |
| `segment` | Business segment (Enterprise, SMB, Startup) |
| `acquisition_channel` | How the customer was acquired |
| `first_purchase_date` | Date of first order |
| `total_orders` | Lifetime order count |
| `total_revenue` | Lifetime revenue (USD) |
| `clv_score` | Customer Lifetime Value score |
| `loyalty_tier` | Bronze / Silver / Gold / Platinum |

**Direct link (raw CSV):**
```
https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/customers/customer_data.csv
```

---

### 💰 Financial Data
**File:** `datasets/finance/financial_data.csv`

Quarterly P&L, EBITDA, net income, cash flow, and balance-sheet snapshot metrics from 2022 Q1 through 2024 Q3.

| Column | Description |
|--------|-------------|
| `period` | Quarter label (e.g. `2024-Q2`) |
| `total_revenue` | Total revenue (USD) |
| `gross_profit` | Revenue minus COGS |
| `gross_margin_pct` | Gross margin percentage |
| `ebitda` | Earnings before interest, tax, depreciation & amortisation |
| `net_income` | Bottom-line profit (USD) |
| `net_margin_pct` | Net margin percentage |
| `free_cash_flow` | Operating cash flow minus capex |
| `total_assets` / `equity` | Balance sheet snapshot |

**Direct link (raw CSV):**
```
https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/finance/financial_data.csv
```

---

### 📣 Marketing Data
**File:** `datasets/marketing/marketing_data.csv`

| Column | Description |
|--------|-------------|
| `campaign_id` | Unique campaign identifier |
| `campaign_name` | Campaign name |
| `channel` | Channel (Social Media, Email, Search PPC, Display, Content/Event, Partner) |
| `budget_usd` / `spend_usd` | Budget and actual spend |
| `impressions` / `clicks` / `ctr_pct` | Reach and engagement |
| `conversions` / `conversion_rate_pct` | Conversion metrics |
| `cost_per_click` / `cost_per_conversion` | Efficiency metrics |
| `revenue_generated` | Revenue attributed to campaign |
| `roas` | Return on Ad Spend |
| `leads_generated` / `mqls` / `sqls` | Pipeline metrics |

**Direct link (raw CSV):**
```
https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/marketing/marketing_data.csv
```

---

### 🚚 Supply Chain Data
**File:** `datasets/supply_chain/supply_chain_data.csv`

| Column | Description |
|--------|-------------|
| `order_id` | Procurement order identifier |
| `supplier_id` / `supplier_name` | Supplier details |
| `product_id` / `product_name` / `category` | Product details |
| `warehouse_id` / `warehouse_location` | Receiving warehouse |
| `quantity_ordered` / `quantity_received` | Order fulfillment |
| `unit_cost` / `total_cost` | Cost metrics |
| `lead_time_days` | Days from order to receipt |
| `on_time_delivery` | Whether delivery was on time (Yes/No) |
| `quality_pass_rate` | Percentage of units passing QC |
| `stock_on_hand` / `reorder_point` / `max_stock_level` | Inventory levels |
| `stockout_occurred` | Whether a stockout happened (Yes/No) |

**Direct link (raw CSV):**
```
https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/supply_chain/supply_chain_data.csv
```

---

## 🚀 Quick Start

### Option 1 – Open the starter notebook in Google Colab

Click the badge at the top of this page, or use the direct link:

[**Open Getting Started Notebook in Colab**](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/getting_started.ipynb)

### Option 2 – Load any dataset with pandas (one line)

```python
import pandas as pd

# Sales
sales = pd.read_csv('https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/sales/sales_data.csv', parse_dates=['order_date'])

# Customers
customers = pd.read_csv('https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/customers/customer_data.csv')

# Finance
finance = pd.read_csv('https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/finance/financial_data.csv')

# Marketing
marketing = pd.read_csv('https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/marketing/marketing_data.csv')

# Supply Chain
supply_chain = pd.read_csv('https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/supply_chain/supply_chain_data.csv')
```

### Option 3 – Connect from Power BI, Tableau, or Looker Studio

Use the raw CSV URL directly as a **Web data source**:

| Tool | How to connect |
|------|----------------|
| **Power BI** | Get Data → Web → paste raw CSV URL |
| **Tableau** | Connect → To a Server → Web Data Connector (or Text File via URL) |
| **Looker Studio** | Add data → CSV file upload *or* use Google Sheets → `=IMPORTDATA("url")` |
| **Google Sheets** | `=IMPORTDATA("https://raw.githubusercontent.com/...")` in cell A1 |

---

## 📈 Analysis Ideas

- **Sales performance** – revenue by region, category, sales rep, and time period
- **Customer segmentation** – CLV distribution, acquisition channel effectiveness, churn risk
- **Financial trend analysis** – quarterly revenue growth, margin compression, cash flow forecasting
- **Marketing attribution** – ROAS by channel, cost-per-conversion benchmarking, pipeline contribution
- **Supply chain health** – on-time delivery rates, stockout frequency, lead time variability by supplier

---

## 🔗 All Raw Dataset URLs

| Dataset | Raw URL |
|---------|---------|
| Sales | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/sales/sales_data.csv` |
| Customers | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/customers/customer_data.csv` |
| Finance | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/finance/financial_data.csv` |
| Marketing | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/marketing/marketing_data.csv` |
| Supply Chain | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/supply_chain/supply_chain_data.csv` |

---

## 📝 License

This dataset collection is released for educational and analytical purposes.

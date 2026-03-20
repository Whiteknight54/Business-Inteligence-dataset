# 📊 Business Intelligence Datasets

A curated collection of business intelligence datasets designed for easy analysis with **Google Colab**, Jupyter, Power BI, Tableau, and any other tool that can read a CSV from a URL.

The primary data source is a **Google Drive folder** — this repository provides the structure, documentation, catalog, and ready-to-run notebooks to analyse that data without downloading anything manually.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/getting_started.ipynb)
[![Drive Access Notebook](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/google_drive_access.ipynb)

---

## ☁️ Google Drive Data Source

| Property | Value |
|----------|-------|
| **Folder** | Business Intelligence Datasets |
| **Folder ID** | `1hp5KzLCTRb2V7ZjHPsFw_WAjUEU6m53i` |
| **Link** | https://drive.google.com/drive/folders/1hp5KzLCTRb2V7ZjHPsFw_WAjUEU6m53i?usp=sharing |

The Drive folder is the **source of truth** for large or live datasets. This repository provides the Git-managed layer on top:

```
Google Drive folder  ──────►  Colab / pandas  ──────►  GitHub repo
(raw data files)              (notebooks)              (docs, catalog, sample CSVs)
```

### Accessing Drive data in three lines (Colab)

```python
from google.colab import drive
drive.mount('/content/drive')
df = pd.read_csv('/content/drive/MyDrive/Business Intelligence Datasets/Sales/sales_data.csv')
```

### Accessing a Drive file by direct URL (anywhere)

```python
import pandas as pd
file_id = "YOUR_DRIVE_FILE_ID"   # from gdrive/catalog.json
df = pd.read_csv(f"https://drive.google.com/uc?export=download&id={file_id}")
```

See [`gdrive/catalog.json`](gdrive/catalog.json) for the file IDs of every dataset and [`gdrive/README.md`](gdrive/README.md) for full instructions.

---

## 📁 Repository Structure

```
datasets/
├── sales/           sales_data.csv          – 100 sales transactions (sample)
├── customers/       customer_data.csv       – 50 customer profiles (sample)
├── finance/         financial_data.csv      – 11 quarters of P&L & cash flow (sample)
├── marketing/       marketing_data.csv      – 29 campaign performance records (sample)
└── supply_chain/    supply_chain_data.csv   – 50 procurement & inventory orders (sample)

gdrive/
├── README.md        – How to work with the Google Drive folder
└── catalog.json     – Machine-readable file catalog (Drive file IDs + GitHub fallbacks)

notebooks/
├── getting_started.ipynb       – Load sample CSVs from GitHub
└── google_drive_access.ipynb   – Load data from the Google Drive folder
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

### Option 1 – Open the Google Drive access notebook in Colab (recommended)

This notebook automatically mounts your Drive and loads the real datasets from the Drive folder above, falling back to GitHub sample CSVs if Drive is unavailable:

[**📂 Open Google Drive Access Notebook in Colab**](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/google_drive_access.ipynb)

### Option 2 – Open the sample-data starter notebook

[**📊 Open Getting Started Notebook in Colab**](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/getting_started.ipynb)

### Option 3 – Mount Drive and load data in two lines (Colab)

```python
from google.colab import drive
drive.mount('/content/drive')

import pandas as pd
sales = pd.read_csv('/content/drive/MyDrive/Business Intelligence Datasets/Sales/sales_data.csv')
```

### Option 4 – Load a Drive file by direct URL (no mount needed)

```python
import pandas as pd

# Replace with the actual file ID from gdrive/catalog.json
file_id = "YOUR_DRIVE_FILE_ID"
df = pd.read_csv(f"https://drive.google.com/uc?export=download&id={file_id}")
```

### Option 5 – Load GitHub sample CSVs (no Drive access needed)

```python
import pandas as pd

BASE = 'https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets'

sales        = pd.read_csv(f'{BASE}/sales/sales_data.csv',              parse_dates=['order_date'])
customers    = pd.read_csv(f'{BASE}/customers/customer_data.csv')
finance      = pd.read_csv(f'{BASE}/finance/financial_data.csv')
marketing    = pd.read_csv(f'{BASE}/marketing/marketing_data.csv')
supply_chain = pd.read_csv(f'{BASE}/supply_chain/supply_chain_data.csv')
```

### Option 6 – Connect from Power BI, Tableau, or Looker Studio

| Tool | How to connect |
|------|----------------|
| **Power BI** | Get Data → Web → paste raw CSV URL or Drive download URL |
| **Tableau** | Connect → To a Server → Web Data Connector (or Text File via URL) |
| **Looker Studio** | Add data → Google Drive (directly) or CSV URL |
| **Google Sheets** | `=IMPORTDATA("https://drive.google.com/uc?export=download&id=FILE_ID")` |

---

## 📈 Analysis Ideas

- **Sales performance** – revenue by region, category, sales rep, and time period
- **Customer segmentation** – CLV distribution, acquisition channel effectiveness, churn risk
- **Financial trend analysis** – quarterly revenue growth, margin compression, cash flow forecasting
- **Marketing attribution** – ROAS by channel, cost-per-conversion benchmarking, pipeline contribution
- **Supply chain health** – on-time delivery rates, stockout frequency, lead time variability by supplier

---

## 🔗 All Access URLs

### GitHub sample CSVs (always available)

| Dataset | Raw GitHub URL |
|---------|----------------|
| Sales | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/sales/sales_data.csv` |
| Customers | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/customers/customer_data.csv` |
| Finance | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/finance/financial_data.csv` |
| Marketing | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/marketing/marketing_data.csv` |
| Supply Chain | `https://raw.githubusercontent.com/Whiteknight54/Business-iInteligence-dataset/main/datasets/supply_chain/supply_chain_data.csv` |

### Google Drive folder

| Resource | Link |
|----------|------|
| **Drive folder** | https://drive.google.com/drive/folders/1hp5KzLCTRb2V7ZjHPsFw_WAjUEU6m53i?usp=sharing |
| **File catalog** | [`gdrive/catalog.json`](gdrive/catalog.json) — fill in `file_id` values after uploading to Drive |
| **Drive notebook** | [Open in Colab](https://colab.research.google.com/github/Whiteknight54/Business-iInteligence-dataset/blob/main/notebooks/google_drive_access.ipynb) |

---

## 📝 License

This dataset collection is released for educational and analytical purposes.

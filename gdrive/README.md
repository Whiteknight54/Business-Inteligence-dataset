# 📁 Google Drive Data Source

This folder documents the **Google Drive folder** that backs this repository.

## Drive Folder

| Property | Value |
|----------|-------|
| **Folder name** | Business Intelligence Datasets |
| **Folder ID** | `1hp5KzLCTRb2V7ZjHPsFw_WAjUEU6m53i` |
| **Shareable link** | https://drive.google.com/drive/folders/1hp5KzLCTRb2V7ZjHPsFw_WAjUEU6m53i?usp=sharing |
| **Access** | Public (view) |

---

## How this works

```
Google Drive folder (source of truth)
        │
        │  mount / pandas.read_csv(gdrive_url)
        ▼
Colab / Jupyter notebook (analysis layer)
        │
        │  commit results, notebooks, catalog
        ▼
GitHub repository (version control + documentation)
```

- **Raw data** lives in Google Drive (large files, proprietary data).
- **Notebooks, catalog, and documentation** live in this Git repository.
- Any tool that can reach a Google Drive link — Colab, Sheets, Tableau, Power BI — can read the data directly.

---

## Expected folder structure in Drive

```
📁 Business Intelligence Datasets/
├── 📁 Sales/
│   └── sales_data.csv (or .xlsx)
├── 📁 Customers/
│   └── customer_data.csv
├── 📁 Finance/
│   └── financial_data.csv
├── 📁 Marketing/
│   └── marketing_data.csv
└── 📁 Supply Chain/
    └── supply_chain_data.csv
```

Update `catalog.json` in this folder whenever you add, rename, or remove files in the Drive folder so the notebooks stay in sync.

---

## Generating direct download links for Drive files

For any file in the Drive folder you can build a direct CSV download URL:

```
https://drive.google.com/uc?export=download&id=<FILE_ID>
```

Example (pandas one-liner):

```python
import pandas as pd

file_id = "PASTE_FILE_ID_HERE"
url = f"https://drive.google.com/uc?export=download&id={file_id}"
df = pd.read_csv(url)
```

The file IDs are recorded in `catalog.json` once you add them.

---

## Adding a new dataset

1. Upload the CSV/XLSX to the Drive folder.
2. Right-click → **Get link** → copy the file ID from the URL.
3. Open `catalog.json` and add an entry.
4. Commit and push `catalog.json`.
5. The notebook (`notebooks/google_drive_access.ipynb`) will automatically pick it up.

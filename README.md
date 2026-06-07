# 🛒 Cozoni Product Catalog Scraper — Web Scraping & Data Pipeline

## 📌 Project Overview

This project is an end-to-end **web scraping and product catalog extraction pipeline** built in Python for **Cozoni.us** — a US-based furniture and home décor e-commerce store running on Shopify. The scraper discovers all product collections via both HTML parsing and the Shopify JSON API, extracts product data across all departments, cleans and transforms the raw data, generates internal SKUs, and exports a final master catalog to CSV.

---

## 📊 Key Results

| Metric | Value |
|---|---|
| Collections Discovered | 30 categories |
| Raw Entries Scraped | 910 rows |
| Unique Products (after dedup) | 214 products |
| Duplicate Rows Removed | 696 |
| Output Format | CSV (master catalog) |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| Requests | HTTP requests & API calls |
| BeautifulSoup | HTML parsing & collection discovery |
| Pandas | Data transformation & cleaning |
| Shopify JSON API | Backend product data extraction |

---

## 🔄 Pipeline Workflow

```
Step 1 — Discovery
  ├── Fetch homepage HTML
  ├── Parse collection links via BeautifulSoup
  └── Verify via Shopify /collections.json API → 30 categories found

Step 2 — Extraction
  ├── Loop through all 30 departments
  ├── Fetch products via /collections/{handle}/products.json
  └── Collect: Product Title, Department, Raw Price → 910 raw entries

Step 3 — Transformation
  ├── Convert Raw Price to float (USD)
  ├── Remove duplicate products (keep first occurrence)
  ├── Generate Internal SKU: INF-COZ-XXX-2026
  └── Final clean catalog: 214 unique products

Step 4 — Export
  └── cozoni_raw_catalog_view.csv
  └── cozoni_master_catalog.csv
```

---

## 📋 Departments Scraped (30 Categories)

`accessories` | `armchairs` | `bar-stools` | `best-sellers` | `chairs` | `coffee-tables` | `console-tables` | `desks` | `dining` | `dining-chairs` | `dining-stools` | `dining-tables` | `drawers-trolleys` | `folding-chairs` | `furnishing-accessories` | `kids` | `living` | `lounge-chairs` | `mirrors` | `new` | `office-chairs` | `office-tables` | `ottomans` | `outdoor` | `rugs` | `sales` | `shelving-units` | `side-tables` | `sideboards` | `sofa`

---

## 📁 Repository Structure

```
cozoni-product-catalog-scraper/
│
├── cozoni.ipynb     # Main scraping notebook
├── cozoni_raw_catalog_view.csv    # Raw scraped data (910 rows)
├── cozoni_master_catalog.csv      # Cleaned final catalog (214 products)
└── README.md                      # Project documentation
```

---

## 🚀 How to Run

1. Open the notebook in **Google Colab** or Jupyter
2. Run all cells from top to bottom
3. Output CSVs will be saved automatically

```bash
pip install requests beautifulsoup4 pandas
```

---

## 💡 Key Concepts Demonstrated

- Dual-method collection discovery (HTML scraping + JSON API)
- Paginated API data extraction from Shopify stores
- Data cleaning — deduplication, type conversion, standardization
- Custom Internal SKU generation logic
- ETL pipeline — Extract → Transform → Load (CSV)
- Respectful scraping with headers and delays

---

## 👤 Author

**Md Murtoza Mahir**
Data Analyst | Python | Web Scraping | ETL | Power BI | SQL
📧 murtozamahir.info@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/murtoza-mahir)
🌐 [Portfolio](https://murtoza-mahir.github.io)

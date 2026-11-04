# Pagila SQL Analysis (SQLite)

**Author:** J. Casey Brookshier  
**Tools:** SQL (SQLite), Python, pandas  

---

## 📌 Project Overview

This project performs relational SQL analysis on the Pagila DVD Rental database using a portable SQLite implementation.

The original PostgreSQL Pagila database was exported to CSV format and rebuilt locally using SQLite to create a lightweight, recruiter-friendly version requiring minimal setup.

The objective is to demonstrate practical SQL proficiency across normalized relational data, including multi-table joins, aggregations, business metrics, and reproducible database workflows.

---

## 🧠 Analytical Focus Areas

- Customer lifetime value (CLV)
- Revenue by store
- Revenue by film category
- Rental activity analysis
- Inventory utilization
- Customer rental frequency segmentation

---

## 📊 Key Insights

- A small subset of customers generates a disproportionate share of revenue  
- Revenue varies meaningfully across stores  
- Certain film categories consistently outperform others  
- Rental frequency strongly correlates with total payment volume  
- Multi-table joins reveal behavior patterns not visible in isolated tables  

This project highlights how structured SQL querying can generate actionable business insights from normalized enterprise-style databases.

---
```markdown
## 📁 Repository Structure
```text
pagila-sql-analysis/
│
├── data/                  
│   ├── film.csv
│   ├── rental.csv
│   ├── inventory.csv
│   ├── customer.csv
│   ├── payment.csv
│   ├── store.csv
│   ├── category.csv
│   └── film_category.csv
│
├── scripts/
│   └── load_pagila.py     
│
├── pagila_analysis_sqlite.sql  
├── requirements.txt
└── README.md
```

---

## 🗄️ Database Design

The database follows a normalized relational structure typical of transactional systems:

- Fact tables: rental, payment  
- Dimension tables: customer, film, store, category  
- Bridge tables: film_category  
- Supporting tables: inventory  

This schema enables realistic business analysis through joins, grouping, and aggregation logic.

---

## 🚀 Skills Demonstrated

- Advanced SQL joins  
- Aggregations and GROUP BY analysis  
- Subqueries  
- Revenue analytics  
- Customer analytics  
- Relational database modeling  
- End-to-end reproducible project design  

---

## 💡 Why SQLite?

The original Pagila database runs on PostgreSQL.  
This version removes the need for PostgreSQL installation and allows:

- Fast setup  
- Portable execution  
- Immediate review by recruiters  
- Reproducible analysis with minimal configuration  

---

## ✅ Fully Self-Contained

All required data is included in the `/data` directory.

Clone → Install → Run → Query.

No external database setup required.

---

## 🚀 How to Run (Mac - must have sqlite3 installed)

```bash
git clone https://github.com/caseybrookshier/pagila-sql-analysis.git
cd pagila-sql-analysis

python3 -m venv venv
source venv/bin/activate

python -m pip install --upgrade pip
python -m pip install -r requirements.txt

python scripts/load_pagila.py

sqlite3 pagila.db < pagila_analysis_sqlite.sql
```

---

## 🚀 How to Run (Windows - must have sqlite3 installed)

```bash
# 1. Clone repo
git clone https://github.com/caseybrookshier/pagila-sql-analysis.git
cd pagila-sql-analysis

# 2. Create virtual environment
python -m venv venv

# 3a. If using PowerShell:
venv\Scripts\Activate.ps1
# 3b. If using Command Prompt:
# venv\Scripts\activate.bat

# 4. Install dependencies
python -m pip install --upgrade pip
python -m pip install -r requirements.txt

# 5. Load initial Python data
python scripts\load_pagila.py

# 6a. Ensure SQLite CLI is installed and in PATH, then run (PowerShell):
Get-Content pagila_analysis_sqlite.sql | sqlite3 pagila.db
# 6b. Or in cmd.exe:
sqlite3 pagila.db < pagila_analysis_sqlite.sql
```




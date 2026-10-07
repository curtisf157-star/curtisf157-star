# 👋 Curtis Ferdinand

### 📊 Data Analyst | ⚽ Football Analytics | 📈 Power BI | 🐍 Python | 🗄️ SQL

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Curtis%20Ferdinand-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/curtis-ferdinand-a56232113)
[![GitHub](https://img.shields.io/badge/GitHub-curtisf157--star-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/curtisf157-star)
[![CF Analytics](https://img.shields.io/badge/CF%20Analytics-Football%20Driven%20Data-1D4ED8?style=for-the-badge&logo=google-chrome&logoColor=white)](https://cfanalytics.uk)

---

## 👨🏾‍💻 About Me

I am a developing **Data Analyst** with a background spanning administration, data entry, technical work and football.

After returning to computing and data analysis, I have been developing practical skills across:

* 📊 Microsoft Excel
* 🔄 Power Query
* 📈 Microsoft Power BI
* 🗄️ SQL
* 🐍 Python
* 🧮 Data cleaning and transformation
* 📋 Reporting and KPI analysis
* 📊 Data visualisation

My focus is on turning raw or messy datasets into information that is **accurate, understandable and useful for decision-making**.

> **"Data should never dictate how a player plays; it should inform the strategy around them."**

---

# 🛠️ Technical Skills

### 📊 Data Analysis

![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=flat-square&logo=microsoftexcel&logoColor=white)
![Power Query](https://img.shields.io/badge/Power_Query-742774?style=flat-square&logo=microsoft&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)

* Data cleaning
* Data validation
* Data transformation
* Exploratory data analysis
* KPI development
* Reporting
* Dashboard development
* Data visualisation

### 🗄️ Databases & Programming

![SQL](https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)

* SQL querying
* Relational databases
* SQLite
* Python data analysis
* Pandas
* Data manipulation
* Dataset preparation

---

# 📂 Featured Projects

## 🌍 FIFA World Cup 2026 Data Project

A football analytics portfolio project using World Cup data to demonstrate database design, SQL analysis and Power BI reporting.

### Focus

* 🗄️ Relational database design
* ⚽ Match analysis
* 👤 Player analysis
* 🌍 Team performance
* 📊 Tournament statistics
* 🔎 SQL queries
* 📈 Power BI dashboards
* 🧹 Data preparation and validation

**Repository:**
👉 [View FIFA World Cup 2026 Project](https://github.com/curtisf157-star)

---

## 🧹 HR & E-commerce Data Cleaning (Power Query M)

A paired data-cleaning project that takes two deliberately messy source datasets and produces analysis-ready tables using **Power Query (M)** inside Power BI.

**Report file:** `Query_1_2.pbix`
**M source files:** `hr-cleaning.md`, `ecommerce_cleaning.md`

> The `.md` files are used purely as a plain-text container for the M code — no Power Query/M extension needed to edit them. Copy only the code, never the markdown fences, when pasting back into Power BI.

### Query1 — `hr_clean` (from `hr_attrition_messy.csv`)

* Forces all columns to `text` before parsing, so parsing is deterministic.
* Normalises:
  * **Gender** → `Male` / `Female`
  * **Department** → `Marketing`, `IT`, `HR`, `Operations`, `Engineering`, `Sales`, `Legal`, `Finance`
  * **Region** → `North America`, `Latin America`, `Asia Pacific`, `Middle East`, `Europe`
  * **Attrition** → `Yes` / `No`
* Parses dates across 7 formats:
  `yyyy-MM-dd`, `dd/MM/yyyy`, `MM/dd/yyyy`, `MM-dd-yyyy`, `dd-MM-yyyy`, `dd MMM yyyy` (en-GB), `MMM dd, yyyy` (en-US).
* Parses salary, including `$`, `,`, `k` suffixes, and junk tokens (`n/a`, `tbd`, `confidential`, `null`, `na`).
* Projects final columns to match `clean.py` / `02_clean_hr.sql`.

### Query2 — `ecommerce_clean` (from `ecommerce_retail_transactions_raw.csv`)

* Deduplicates on `Order_ID` using the same caveat as the SQL
  (`ROW_NUMBER() … ORDER BY Order_Date` on the **raw string**).
* Normalises:
  * **Payment_Method** → `Net Banking`, `Cash on Delivery`, `Credit Card`, `Debit Card`, `UPI`, `PayPal`
  * **Country** → `USA`, `UK`, `Canada`, `Australia`, `Germany`, `UAE`, `India`
  * **Order_Status** → `Delivered`, `Shipped`, `Pending`, `Cancelled`, `Returned`
* Parses `Order_Date` with the same 7-format cascade as Query1.
* `Quantity` is nulled if `<= 0`; `Discount_Percent` defaults to `0` when missing.
* Projects final columns to match `clean.py` / `03_clean_ecommerce.sql`.

### How to load into Power BI

1. Open `Query_1_2.pbix` in **Power BI Desktop**.
2. **Transform Data** → **Home** → **New Source** → **Blank Query** → **Advanced Editor**.
3. Paste the contents of `hr-cleaning.md` (code only). Rename the query to **Query1**.
4. Repeat step 2, paste `ecommerce_cleaning.md`, rename to **Query2**.
5. In each query, replace `FilePath` with your own path, e.g.
   ```m
   FilePath = "C:\Users\<you>\Downloads\clean-data\hr_attrition_messy.csv"

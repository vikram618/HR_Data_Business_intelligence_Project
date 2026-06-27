
# HR Analytics: Employee Attrition Analysis

## 📌 Project Overview
This project analyzes employee attrition using an HR dataset, covering the full analytics pipeline: data cleaning, exploratory analysis, SQL-based business querying, and an interactive Power BI dashboard. The goal is to identify **who is leaving, why they're leaving, what it's costing the business, and what actions HR/leadership should take.**

## 🎯 Business Questions Answered
1. **Who is leaving?** — Segmented by Department, JobRole, Age Group, and Gender
2. **Why are they leaving?** — Correlating attrition with Job Satisfaction, Overtime, Income, and Promotion history
3. **What is it costing us?** — Estimated annual replacement cost by department
4. **What should we do about it?** — Data-backed, actionable recommendations

## 🗂️ Dataset
- **Source:** IBM HR Analytics Employee Attrition dataset (1,480 employees, 38 columns)
- **Note:** A deliberately "dirtied" version was used for practicing data-cleaning skills — includes injected missing values, inconsistent categorical labels, mixed data types, outliers, and duplicate rows. The cleaned version (`HR_Analytics_CLEAN`) is used for all analysis and reporting.

## 🛠️ Tech Stack
| Stage | Tools |
|---|---|
| Data Cleaning | Python (pandas, numpy) |
| Exploratory Analysis | Python (pandas) |
| Business Querying | SQL (SQLite) |
| Dashboard / Visualization | Power BI (DAX measures, interactive visuals) |
| Documentation | Markdown, Word (insights summary) |

## 🧹 Data Cleaning Steps
- Standardized inconsistent missing-value tokens (`NA`, `N/A`, `null`, `?`, `missing`) into proper `NaN`
- Fixed case/whitespace inconsistencies across categorical columns (`.str.strip().str.title()`)
- Mapped abbreviations and synonyms to canonical categories (e.g. `HR` → `Human Resources`, `Y`/`1`/`True` → `Yes`)
- Converted misformatted numeric columns (text injected into numeric fields) using `pd.to_numeric(errors='coerce')`
- Removed unrealistic outliers (e.g. Age > 65, negative tenure, salary of 0 or 9,999,999) using domain-driven bounds and IQR methods
- Dropped duplicate rows and rows missing critical fields (`Gender`, `Department`, `BusinessTravel`)

## 📊 Key Insights
- **Overall attrition rate: 15.9%**
- **Sales Representatives** have the highest attrition at **39.1%** — more than double any other role
- **Overtime is the strongest driver**: attrition triples for employees working overtime (30.9% vs. 9.9%)
- Employees aged **18–25** leave at **36%**, indicating an early-career retention gap
- **R&D** has the lowest attrition rate (13.7%) but the **highest total cost** (~$3.75M/year) due to headcount size, while Sales costs ~$2.74M/year despite fewer employees
- **Total estimated annual attrition cost: ~$6.8M**

## 💡 Recommendations
1. Prioritize the Sales Representative role — review overtime load and quota pressure; it's both the highest attrition rate and a major cost driver
2. Cap or redistribute overtime company-wide — the single most actionable lever identified in the data

## 🚀 How to Reproduce
1. Clone the repo and open `notebooks/data_cleaning_eda.ipynb` to run the cleaning pipeline
2. Load `data/HR_Analytics_clean.csv` into SQLite and run `sql/business_queries.sql` to reproduce the business answers
3. Open `dashboard/HR_Attrition_Dashboard.pbix` in Power BI Desktop to explore the interactive dashboard


## 📬 Contact
*(Add your name / LinkedIn / email here)*

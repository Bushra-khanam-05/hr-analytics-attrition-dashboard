# HR Analytics & Attrition Dashboard

## 📊 Project Overview
An end-to-end HR analytics project analyzing employee attrition patterns using SQL Server and Power BI. The goal was to identify which departments, roles, and employee profiles are at highest attrition risk — and surface actionable insights for HR teams.

---

## 🔍 Problem Statement
HR leadership lacked a data-backed understanding of why employees were leaving and which segments were most at risk. Retention decisions were reactive and based on intuition rather than data.

---

## 📁 Dataset
- **Source:** [IBM HR Analytics Attrition Dataset — Kaggle](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Records:** 1,470 employees
- **Features:** 35 attributes including Department, JobRole, Age, MonthlyIncome, OverTime, JobSatisfaction, WorkLifeBalance, YearsAtCompany

---

## 🛠️ Tools Used
| Tool | Purpose |
|---|---|
| SQL Server (SSMS) | Data import, cleaning, and analysis queries |
| Power BI Desktop | Dashboard design and DAX measures |
| DAX | Custom KPI measures |

---

## 🧮 SQL Analysis
Ran 10 analytical queries covering:
- Overall attrition rate
- Attrition by Department, Job Role, Age Group
- Overtime vs Attrition impact
- Job Satisfaction breakdown
- High-risk employee profiles
- Tenure buckets (critical retention window)
- Work-life balance vs attrition
- Income comparison: attrited vs retained

---

## 📐 DAX Measures Created
```dax
Total_Employees = COUNTROWS(hr_attrition)

Attrited_Employees =
COUNTROWS(FILTER(hr_attrition, hr_attrition[Attrition] = "Yes"))

Attrition_Rate =
DIVIDE([Attrited_Employees], [Total_Employees]) * 100
```

---

## 📊 Dashboard Visuals
| Visual | Type | Insight |
|---|---|---|
| Total Employees | KPI Card | 1,470 total workforce |
| Attrited Employees | KPI Card | 237 employees left |
| Attrition Rate | KPI Card | 16.12% overall attrition |
| Attrition by Department | Bar Chart | Sales highest at 21% |
| Overtime vs Attrition | Donut Chart | 53.6% who left worked overtime |
| Attrition by Age Group | Bar Chart | Under 25 highest at 39% |
| Attrition by Job Role | Bar Chart | Sales Reps highest at 40% |

---

## 💡 Key Insights
- **Sales Representatives** have the highest attrition rate at **40%**
- **Employees under 25** are the most at-risk age group (**39% attrition**)
- **53.6% of attrited employees** were working overtime — a critical signal
- **Human Resources** department has **19% attrition** despite small headcount
- **Research Directors and Managers** have the lowest attrition (**3–5%**)
- Employees with **low job satisfaction + overtime = significantly higher churn**

---

## 📌 Business Recommendations
1. **Reduce overtime** for Sales Representatives and Lab Technicians immediately
2. **Focus retention efforts** on employees in their first 1–3 years (highest churn window)
3. **Improve onboarding** for employees under 25 — mentorship programs, career pathing
4. **Monitor job satisfaction scores** quarterly — use as early warning indicator
5. **HR department** needs attention despite small size — high attrition % signals internal issues

---

## 📂 Repository Structure
```
hr-analytics-attrition-dashboard/
│
├── hr_analytics_sqlserver.sql       # All SQL queries (SQL Server)
├── HR_Analytics_Attrition_Dashboard.pbix  # Power BI dashboard file
├── dashboard_screenshot.png         # Dashboard preview
└── README.md                        # Project documentation
```

---

## 🚀 How to Run
1. Download the dataset from Kaggle (link above)
2. Run `hr_analytics_sqlserver.sql` in SSMS to create DB and import data
3. Open `HR_Analytics_Attrition_Dashboard.pbix` in Power BI Desktop
4. Update the SQL Server connection to `localhost` → `hr_analytics`
5. Refresh data and explore the dashboard

---

*Project by [Bushra Khanam](https://www.linkedin.com/in/bushra-khanam05/) | Data Analyst*

# healthcare-waitlist-analysis
# 🏥 Healthcare Waitlist Analysis Dashboard

## 📌 Overview
This project analyzes patient waitlist data to identify bottlenecks, delays, and inefficiencies in healthcare service delivery.

> ⚠️ Note: This dataset is a **dummy dataset** created for learning and portfolio purposes.

---

## 🎯 Business Problem
Healthcare providers are experiencing increasing patient wait times, leading to:
- Reduced service efficiency
- Poor patient experience
- Resource allocation challenges

---

## 📊 Dataset Description
The dataset includes:
- Patient ID
- Age group
- Case type (Inpatient / Outpatient / Day Case)
- Specialty
- Wait time band
- Date

---

## 🧠 Data Modeling
- Star schema used
- Fact table: Patient Waitlist
- Dimension tables:
  - Date
  - Specialty
  - Age Group

---

## 📈 Key KPIs & DAX Measures

### Total Waitlist
```DAX
Total Waitlist = COUNT('Waitlist'[Patient_ID])

### Previous Year Waitlist
```DAX
PY Waitlist = 
CALCULATE(
    [Total Waitlist],
    SAMEPERIODLASTYEAR('Date'[Date])
)

### Waitlist change %
```DAX
Waitlist Change % = 
DIVIDE([Total Waitlist] - [PY Waitlist], [PY Waitlist])

### Average Wait Time
```DAX
Avg Wait Time = AVERAGE('Waitlist'[Wait_Time])
---

## 📊 Visualizations
- KPI Cards (Total Waitlist, YoY Change)
- Donut Chart (Case Type Distribution)
- Bar Chart (Waitlist by Specialty)
- Matrix Table (Age Group vs Wait Time)
---

## 🔍 Key Insights
- Waitlist increased by 12% YoY
- Outpatients represent ~72% of total cases
- Long wait times (6–18 months) dominate
---

## 💡 Business Recommendations
- Increase outpatient capacity
- Prioritize high-delay specialties
- Improve scheduling and triage systems
---

## 🛠 Tools Used
- Power BI
- DAX
- Data Modeling
---

## 📌 Outcome

This dashboard helps stakeholders identify operational bottlenecks and improve healthcare delivery efficiency.

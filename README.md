# Daikibo Industrials — Data Analytics Virtual Experience (Forage)

![Forage](https://img.shields.io/badge/Forage-Virtual%20Experience-blue?style=flat-square)
![Python](https://img.shields.io/badge/Python-3.x-yellow?style=flat-square&logo=python)
![Tableau](https://img.shields.io/badge/Tableau-Dashboard-orange?style=flat-square&logo=tableau)
![Excel](https://img.shields.io/badge/Excel-Data%20Analysis-green?style=flat-square&logo=microsoft-excel)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat-square)

A end-to-end data analytics project completed as part of the **Daikibo Industrials Virtual Experience Program** on [Forage](https://www.theforage.com/). The program simulates real-world forensic data analysis tasks across two key business problems: **factory machine downtime** and **gender pay equality**.

---

## 📁 Project Structure

```
daikibo-analytics/
│
├── data/
│   ├── daikibo-telemetry-data.json      # Raw telemetry data (May 2021)
│   └── Equality_Table.xlsx              # Gender pay equality scores
│
├── outputs/
│   ├── daikibo_dashboard.jpg            # Dashboard screenshot (Task 2)
│   ├── daikibo_dashboard.pdf            # Dashboard PDF export
│   └── Equality_Table_completed.xlsx    # Completed equality classification (Task 5)
│
└── README.md
```

---

## 🏭 Background

**Daikibo Industrials** operates 4 factories globally:

| Factory | Location |
|---|---|
| Daikibo Factory Meiyo | Tokyo, Japan |
| Daikibo Factory Seiko | Osaka, Japan |
| Daikibo Berlin | Berlin, Germany |
| Daikibo Shenzhen | Shenzhen, China |

Each factory runs **9 types of machines**, each sending a telemetry message every 10 minutes. Data was collected throughout **May 2021**.

---

## ✅ Tasks Completed

### Task 2 — Machine Downtime Dashboard

**Goal:** Identify which factory had the most machine downtime and which device types were responsible.

**Approach:**
- Imported `daikibo-telemetry-data.json` (160,704 records) into Tableau
- Created a calculated field `Unhealthy` assigning **10 minutes** of downtime per unhealthy status message
- Built two bar charts — *Down Time per Factory* and *Down Time per Device Type*
- Combined into an interactive dashboard where selecting a factory filters the device chart

**Key Findings:**

| Factory | Downtime (min) |
|---|---|
| 🔴 Daikibo Factory Seiko | **480** |
| Daikibo Shenzhen | 420 |
| Daikibo Factory Meiyo | 110 |
| Daikibo Berlin | 20 |

- **Most affected factory:** Daikibo Factory Seiko (Osaka)
- **Root cause:** 100% of Seiko's downtime was attributed to the **LaserWelder** machine

---

### Task 5 — Gender Pay Equality Classification

**Goal:** Add an `Equality class` column to the equality score dataset, classifying each role's pay gap severity.

**Classification Logic:**

| Score Range | Class |
|---|---|
| −10 to +10 | ✅ Fair |
| −20 to −11 or +11 to +20 | ⚠️ Unfair |
| < −20 or > +20 | 🚨 Highly Discriminative |

**Implementation:** Used an Excel `IF` formula applied across all 37 rows:
```excel
=IF(ABS(C2)<=10, "Fair", IF(ABS(C2)<=20, "Unfair", "Highly Discriminative"))
```

**Key Findings:**
- Pay inequality is most severe at **C-Level, VP, and Senior Manager** roles across all factories
- **Engineering and operational roles** are largely classified as Fair
- Daikibo Factory Seiko and Shenzhen show the highest concentration of Highly Discriminative scores at management level

---

## 🛠️ Tools & Technologies

- **Python** — data extraction and analysis (`pandas`, `openpyxl`, `matplotlib`)
- **Tableau** — interactive dashboard creation
- **Microsoft Excel** — formula-based data classification
- **JSON** — raw telemetry data format

---

## 📊 Dashboard Preview

![Daikibo Dashboard](outputs/daikibo_dashboard.jpg)

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/daikibo-analytics.git
   cd daikibo-analytics
   ```

2. Install Python dependencies:
   ```bash
   pip install pandas openpyxl matplotlib
   ```

3. Open `Equality_Table_completed.xlsx` to view the completed pay equality classification.

4. Open the dashboard files in `outputs/` to view the downtime analysis.

---

## 📜 Certificate

Completed via [Forage](https://www.theforage.com/) — Daikibo Industrials Data Analytics Virtual Experience Program.

---

## 👤 Author

**Your Name**
[LinkedIn](https://linkedin.com/in/your-profile) • [GitHub](https://github.com/your-username)

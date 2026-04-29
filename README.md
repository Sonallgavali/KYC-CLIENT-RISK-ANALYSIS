# 🔍 KYC Client Risk Dashboard — Power BI

A two-page interactive Power BI dashboard for **Know Your Customer (KYC) compliance and AML risk monitoring**, built on a structured client risk dataset with 20+ fields covering risk scoring, sanctions, PEP status, country flags, and sectoral exposure.

---

## 📊 Dashboard Preview

### Page 1 — Executive Overview
![Page 1](KYC-CLIENT-RISK-ANALYSIS/blob/main/page1.png)

### Page 2 — Client Risk Register
![Page 2](assets/page2.png)

---

## 🎯 Objective

To provide compliance teams and risk officers with a centralized view of:
- Client risk distribution across categories (High / Medium / Low)
- Country and sector-level risk concentration
- Individual client flag status (PEP, Sanctions, OFAC, FATF)
- Ownership opacity and sectoral sanctions exposure

---

## 📁 Dataset — `kyc` Table

| Column | Type | Description |
|--------|------|-------------|
| `client_id` | Integer | Unique client identifier |
| `client_name` | Text | Full client name |
| `client_type` | Text | Corporate / Individual / NGO / Financial Institution |
| `country` | Text | Client country of residence/registration |
| `risk_category` | Text | High Risk / Medium Risk / Low Risk |
| `risk_score` | Decimal | Composite risk score (0–10) |
| `is_high_risk` | Boolean | Flag: client classified as high risk |
| `is_pep` | Boolean | Flag: Politically Exposed Person |
| `is_sanctioned` | Boolean | Flag: on a sanctions list |
| `is_high_opacity` | Boolean | Flag: high ownership opacity |
| `pep_flag` | Boolean | Secondary PEP indicator |
| `sanctions_flag` | Boolean | Secondary sanctions indicator |
| `fatf_country_flag` | Boolean | Country on FATF watchlist |
| `ofac_country_flag` | Boolean | Country flagged by OFAC |
| `sectoral_sanctions_flag` | Boolean | Subject to sectoral sanctions |
| `ownership_opacity_score` | Decimal | Opacity score (0–100) |
| `sector` | Text | Business sector |
| `sector_risk` | Text | Sector-level risk classification |
| `sector_risk_score` | Decimal | Sector risk score |
| `High Risk Clients` | Measure | Count of high risk clients |
| `Medium Risk Clients` | Measure | Count of medium risk clients |
| `Low Risk Clients` | Measure | Count of low risk clients |

---
## 📄 Pages

### Page 1 — Executive Overview
| Visual | Fields Used |
|--------|-------------|
| KPI Cards (×6) | Total Clients, Low/Medium/High Risk Clients, Avg Risk Score, % High Risk |
| Donut Chart | `risk_category` → Count of `client_id` |
| Stacked Bar — Country | `country` × `risk_category` → Total Clients (Top 6) |
| Bar Chart — Sector | `sector` → Avg Risk Score |
| Bar Chart — Client Type | `client_type` → Sum of `sector_risk_score` |
| Slicers | `country`, `sector` |

### Page 2 — Client Risk Register
| Visual | Fields Used |
|--------|-------------|
| KPI Cards (×4) | Filtered Clients, Avg Risk Score, % High Risk, Avg Ownership Opacity |
| Detail Table | All 17 client columns with conditional formatting |
| Slicers | `client_type`, `sector`, `risk_score` range |

---

## 🛠 Tools & Technologies

- **Power BI Desktop** — report authoring
- **DAX** — measures and calculated columns
- **Power Query (M)** — data transformation
- **Python / SQL** — data generation and prep

---


## 💡 Key Insights from the Data

- **23.8%** of clients are classified as High Risk — above typical industry threshold of 15%
- **Energy/Oil** and **Defense/Arms** sectors carry the highest average risk scores
- **CH, SD, VE** are the top 3 countries by total client count with significant High Risk concentration
- NGO and Financial Institution client types show elevated `sector_risk_score` totals

---

## 📌 Use Cases

- AML (Anti-Money Laundering) compliance monitoring
- Periodic KYC review prioritization
- Regulatory reporting preparation (FATF, OFAC)
- Risk committee dashboards

---

## 👤 Author

Sonal Gavali
Data Analyst | Risk & Compliance  
[GitHub](https://github.com/Sonallgavali)

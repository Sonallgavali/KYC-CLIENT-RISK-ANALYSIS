# 🔍 KYC Client Risk Dashboard — Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)

A two-page interactive Power BI dashboard for **Know Your Customer (KYC) compliance and AML risk monitoring**, built on a structured client risk dataset with 20+ fields covering risk scoring, sanctions, PEP status, country flags, and sectoral exposure.

---

## 📊 Dashboard Preview

### Page 1 — Executive Overview
![Page 1](KYC-CLIENT-RISK-ANALYSIS/page1.png)

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

## 📐 Data Model

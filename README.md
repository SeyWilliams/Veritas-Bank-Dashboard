# Veritas-Bank-Dashboard
Analyzing Customer Churn and Retention Patterns
# 🏦 Veritas Bank — Customer Churn & Retention Analysis

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat&logo=microsoftexcel&logoColor=white)
![Status](https://img.shields.io/badge/Status-Complete-2EC4B6?style=flat)
![Type](https://img.shields.io/badge/Type-Capstone%20Project-1E2761?style=flat)

A customer churn and retention intelligence project built for **Veritas Bank**, a UK-headquartered retail bank operating across the UK, Germany, and France — turning a raw 10,000-customer transaction dataset into a two-page interactive Power BI dashboard that replaces guesswork with an evidence-based retention strategy.

---

## 📌 Table of Contents

- [Overview](#-overview)
- [Objectives](#-objectives)
- [Data Dictionary](#-data-dictionary)
- [Dashboards](#-dashboards)
- [Key Insights](#-key-insights)
- [Business Questions Answered](#-business-questions-answered)
- [Core KPIs & Formulas](#-core-kpis--formulas)
- [Recommendations](#-recommendations)
- [Tech Stack](#️-tech-stack)
- [Author](#-author)

---

## 💡 Overview

Veritas Bank is facing rising customer churn across its three core markets, driven by intensifying competition from neobanks, a perceived engagement gap in Germany and France, and — critically — no real-time way to see who is at risk before they leave.

This project builds a **centralized churn command center**: one Power BI report that profiles the full 10,000-customer base, isolates exactly which customers are churning and why, and translates those patterns into a prioritized, actionable retention roadmap for leadership.

---

## 🎯 Objectives

- Identify the common characteristics shared by customers who have already churned
- Compare customer behaviour and churn patterns across the UK, Germany, and France
- Segment customers by risk profile and account usage
- Determine the major factors influencing churn — activity status, balance, tenure, age, and product holding
- Build interactive dashboards that support real-time, data-driven retention decisions
- Translate findings into practical, prioritized recommendations to improve retention

---

## 🧩 Data Dictionary

| Field | Description |
|---|---|
| `CustomerId` | Unique identifier for each customer |
| `LastName` | Customer surname |
| `CreditScore` | Customer's creditworthiness score |
| `Country` | Customer's country of residence (UK, Germany, France) |
| `Gender` | Customer's gender |
| `Age` | Customer's age |
| `Tenure` | Number of years the customer has been with the bank |
| `Balance` | Customer's account balance (£) |
| `Products` | Number of bank products held by the customer |
| `CreditCard` | Whether the customer holds a credit card with the bank |
| `ActiveMember` | Whether the customer is an active bank member |
| `Exited` | Churn indicator — whether the customer has left the bank |

---

## 📊 Dashboards

### 👤 Dashboard 1 — Customer Demographics
- **KPI strip:** Total Customers, Churn Rate, Average Credit Score
- **Customers per Country:** distribution across the UK, Germany, and France
- **Customers by Credit Card Status:** credit card ownership split
- **Customers by Active Status:** active vs. inactive member split
- **Customers by Age Group:** full age distribution of the customer base
- **Customer by Gender:** male/female split
- **Customers by Products:** how many products each customer holds

<img width="994" height="749" alt="image" src="https://github.com/user-attachments/assets/6e6646a2-475e-43e1-b4db-b6d863374149" />

*Dashboard 1, built in Power BI — a full profile of the 10,000-customer base before any churn filtering.*

### 📉 Dashboard 2A — Churn Analysis Overview
- **Churn by Country:** churned customers broken down by market
- **Churned by Products:** churn split by number of products held
- **Churn by Age Group:** churn volume across every age band
- **Churn by Balance Group:** churn broken down by account balance tier

<img width="994" height="749" alt="image" src="https://github.com/user-attachments/assets/fee2bd6a-6368-4506-a250-8f138030c658" />

*Churn filtered by country, product holding, age group, and account balance.*

### 🔍 Dashboard 2B — Churn Deep Dive
- **Churn by Age Group:** repeated for cross-reference against tenure and activity
- **Churn by Active Member:** churn broken down by membership activity status
- **Churned by Products:** cross-check view against credit card status
- **Churn by Tenure Group:** churn volume across every tenure band

<img width="994" height="749" alt="image" src="https://github.com/user-attachments/assets/8943ae95-b2fd-469b-8a3c-2fd7b673df6e" />

*Churn filtered by active-member status and customer tenure — the sharpest view in the whole report.*

---

## 📈 Key Insights

- **Inactivity is a near-perfect churn predictor.** 100% of the 1,385 churned customers had gone inactive first — in this dataset, activity status alone almost fully separates stayers from leavers.
- **A clear "at-risk persona" emerges.** 60% of churned customers (829 of 1,385) held a £0 balance — and since every churner was also inactive, "inactive + empty balance" is a high-precision combined warning flag.
- **Rate beats volume when it comes to age.** 30–39-year-olds churn in the highest numbers (490), but 20–29-year-olds churn at the highest *rate* (≈14.7% of that group vs ≈14.4% for 30–39s) — early-career customers are proportionally the most likely to leave.
- **Years 3–8 are the danger zone, not year 1.** 71% of churn happens in years 3–8 of tenure, yet customers who reach year 9+ almost never leave (just 6% of churn) — loyalty is won or lost mid-relationship, not at onboarding.
- **Cross-selling alone won't fix churn.** Churn rate is nearly flat across product tiers (≈14% for 1–2 products, ≈12% for 3) — product count is a weak lever; engagement and balance activity matter far more.
- **Country-level churn tracks the customer base.** The UK shows the highest churn in absolute terms, but that's roughly proportional to its larger customer share (50.1%) — no single market is a standout outlier.

---

## ❓ Business Questions Answered

| Question (from project brief) | Answer |
|---|---|
| What are the common characteristics of churned customers? | Inactive membership status (100%), £0 balance (60%), and 3–8 years of tenure (71%) |
| How does customer behaviour compare across the UK, Germany, and France? | Churn tracks each country's share of the customer base — no major outlier by market |
| How can customers be segmented by risk and account usage? | By activity status + balance tier + tenure band — the combination that best isolates at-risk customers |
| Which factors most influence churn? | Activity status (strongest), balance, tenure, and age — product count is a weak factor |
| Which customer segment should the bank focus on for retention? | Inactive, low-balance customers in years 3–8 of tenure, particularly the 20–29 age group |

---

## 🧮 Core KPIs & Formulas

- **Total Customers** = `DISTINCTCOUNT(CustomerId)`
- **Churn Rate (%)** = `COUNT(Exited = 1) ÷ Total Customers × 100`
- **Average Credit Score** = `AVERAGE(CreditScore)`
- **Churn Rate by Segment** = `COUNT(Exited = 1) within segment ÷ Total Customers within segment × 100`
- **At-Risk Flag** = `ActiveMember = 0 AND Balance = 0` (highest-precision churn indicator identified)

---

## 💡 Recommendations

1. **Real-Time Inactivity Alerts.** Auto-flag any customer with no login or transaction for 60–90 days and route them into an automated win-back journey — personalised message, fee-waiver offer, or a callback from a relationship manager — before dormancy turns into a full exit.
2. **Zero-Balance Reactivation Program.** Trigger outreach the moment an account sits at £0 for 60+ days: a first-deposit cash bonus, temporary fee waiver, or auto-enrolment into a round-up micro-savings product to rebuild both balance and engagement.
3. **Year-3 Loyalty Milestone.** Since 71% of churn happens in years 3–8, introduce a proactive "Loyalty Review" at the 3-year mark — a better rate, cashback, or advisor check-in — to carry customers safely into the low-churn 9+ year zone.
4. **Early-Career Onboarding Journey.** Build a dedicated first-12-months programme for 20–29-year-olds — financial wellness content, fee-free periods, and 30/90/180-day check-ins — to address their higher relative churn rate.
5. **Unified Churn Risk Score.** Combine inactivity + balance + tenure + age into one DAX-driven risk score inside the Power BI model, refreshed daily, with automated alerts to branch and relationship managers for the highest-risk customers.

---

## ⚙️ Tech Stack

- **Data Source:** Customer transaction and profile dataset (CSV/Excel)
- **Transformation:** Power Query (data cleaning, type correction, relationship modeling)
- **Modeling & Metrics:** DAX (churn rate, segmentation flags, risk scoring)
- **Visualization:** Microsoft Power BI (interactive 3-page report with drill-through between Demographics and Churn views)

---

## 👨‍💻 Author

**Emmanuel Sey Williams**
📧 williamsemmanuel7382@gmail.com


📊 **Project Status:** Complete

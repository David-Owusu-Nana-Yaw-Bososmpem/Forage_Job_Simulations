# Forage Actuarial Analyst Job Simulation – Marine Liability Claims Analysis & Pricing

**Company:** Oceanic Shipping Co. (fictional case study)  
**Simulation Provider:** Forage  
**Role:** Actuarial Analyst  
**Focus:** Experience rating, pure premium calculation, exploratory data analysis (EDA), and risk assessment for Marine Liability insurance

---

## Project Overview

This repository contains the completed deliverable for the Forage Actuarial Analyst job simulation.

The objective was to analyse historical Marine Liability claims data for Oceanic Shipping Co., perform exploratory data analysis, apply actuarial pricing principles (frequency × severity), develop an experience-based pure premium model, load for large losses, expenses and profit, and produce a recommended premium together with sensitivity analysis.

The single deliverable is a comprehensive Excel workbook containing:

- Cleaned and enriched claims data
- Exploratory Data Analysis (tables, pivot summaries, commentary)
- Pure premium / experience rating calculations
- Large-loss loading
- Final recommended premium
- Sensitivity analysis

---

## Skills & Techniques Demonstrated

| Area | Techniques Applied |
|------|--------------------|
| **Data Manipulation** | Deriving missing columns (Gross claim amount, Inflation Index, Gross/Net inflation-adjusted claims, Capped net incurred, Attritional flag, Year) |
| **EDA** | Pivot tables by year, claim type, cause of loss, location; average severity trends; claim count distributions |
| **Actuarial Pricing** | Experience rating / pure premium = Frequency × Severity; inflation adjustment to a common year; exposure-based frequency (claims per unit of Gross Tonnage) |
| **Risk Loading** | Separation of attritional vs large losses; large-loss loading using assumed return period |
| **Expense & Profit Loading** | Expense loading (30 % of loss cost) + profit margin (10 %) |
| **Sensitivity Analysis** | Impact of a 6 % increase in claim severity on the final premium |
| **Documentation** | Clear assumptions list, methodology notes, and structured workbook layout |

---

## Dataset Summary

- **100 claims** spanning **2018–2023**
- Key fields: Claim ID, Date of Claim, Type of Claim, Claim Incurred, Claim Status, Gross claim amount, Policy Limits, Deductible, Cause of Loss, Location, Insured Party, Gross Tonnage, Prior Claims History
- Derived fields:
  - Inflation Index (to bring claims to a common purchasing-power base)
  - Gross / Net inflation-adjusted claim amounts
  - Capped net inflation-adjusted incurred (after policy limits / deductibles considerations)
  - Attritional claim flag (claims ≤ $1 m)
  - Calendar Year

**Claim Types:** Cargo Liability, Collision Liability, Damage to Other Vessels, Environmental Pollution, Injury to Third Parties  

**Causes of Loss:** Criminal Activity, Human Error, Natural Disaster, Technical Failure  

**Locations:** Atlantic Ocean, Indian Ocean, Mediterranean Sea, Pacific Ocean, etc.

---

## Methodology

### 1. Data Preparation
- Examined raw claims data and derived the missing values in the required columns (Gross claim amount, Inflation Index series, Gross & Net inflation-adjusted amounts, Capped net incurred, Attritional flag).
- Inflation indices were applied year-by-year to bring all claims to a consistent base for analysis.

### 2. Exploratory Data Analysis (Sheet: `Exploratory`)
- Claim counts and total incurred by year
- Average claim amount (inflation-adjusted) by year
- Distribution of claims by Type of Claim and by Cause of Loss
- Average severity by claim type and by cause of loss
- Identification of trends, concentration, and potential anomalies (e.g., higher average severity in certain years or causes)

### 3. Pure Premium / Experience Rating Model (Sheet: `Pure Premium Work`)

**Key Assumptions (explicitly documented in the workbook):**
1. Commission = 0 %
2. No claims development adjustment required
3. Deductibles remain consistent with historical levels
4. Policies written on a calendar-year (1 Jan – 31 Dec) basis
5. Large loss defined as any claim > $1 m incurred
6. Large-loss event assumed to be a 1-in-20 year occurrence
7. Expenses = 30 % of loss cost
8. Profit requirement = 10 % of the risk premium

**Calculation Steps:**
1. **Inflation adjustment** of historical claims to a common base.
2. **Attritional claims** isolated (flag = 1).  
   - Total capped net inflation-adjusted incurred ≈ **$58.03 m** across 99 attritional claims.  
   - Average severity ≈ **$586,168**.
3. **Claim frequency** calculated on an exposure basis (claims per unit of Gross Tonnage) for each historical year.
4. Average frequency and average severity derived from the historical experience.
5. **2024 expected exposure** provided by the client: **40,000,000 Gross Tonnage**.
6. **Attritional loss cost** = Average Frequency × Average Severity × Expected Exposure.
7. **Large-loss loading** = (Observed large-loss amount) ÷ 20 (return period).  
   - Observed large loss ≈ $5.25 m → Loading ≈ **$262,697**.
8. **Total Risk Premium** = Attritional loss cost + Large-loss loading ≈ **$9.105 m**.
9. **Final Premium** = Total Risk Premium × (1 + 0.30) × (1 + 0.10) ≈ **$13.02 m**.

### 4. Sensitivity Analysis
- Scenario: **+6 % increase in claim severity**.
- New risk premium ≈ **$9.635 m**
- New final premium ≈ **$13.78 m**  
  → Demonstrates the sensitivity of the recommended premium to severity assumptions.

---

## Key Results & Recommendation

| Metric | Value |
|--------|-------|
| Recommended Final Premium (base case) | **≈ $13.02 million** |
| Total Risk Premium (incl. large-loss load) | **≈ $9.10 million** |
| Large-loss loading (1-in-20) | **≈ $0.26 million** |
| Sensitivity (+6 % severity) Final Premium | **≈ $13.78 million** |

**Recommendation:**  
A premium of approximately **$13.0 – $13.8 million** is indicated for the forthcoming policy period under the stated assumptions. The model is moderately sensitive to severity assumptions; ongoing monitoring of claim severity trends and large-loss experience is advised. External factors (shipping market conditions, regulatory changes, climate-related perils) should be considered in future renewals.

---

## Workbook Structure

| Sheet | Contents |
|-------|----------|
| **Claims Data** | Original + fully derived / inflation-adjusted claims data (100 records) |
| **Exploratory** | Pivot tables, average severity by year / type / cause, claim counts, commentary-ready summaries |
| **Pure Premium Work** | Inflation indices, exposure data, frequency & severity calculations, large-loss loading, final premium build-up, sensitivity analysis, full list of assumptions |
| **Report** | Placeholder for narrative management summary (can be extended) |

File: [`Marine_Liability_Claims_Analysis.xlsx`](Marine_Liability_Claims_Analysis.xlsx)

---

## Limitations & Areas for Further Work

- Claims development (IBNR / outstanding reserves) assumed to require no further adjustment.
- Large-loss loading uses a simple 1-in-20 return period; a more sophisticated excess-of-loss or frequency-severity model could be developed with more data.
- No explicit allowance for trend beyond the inflation indices used, or for changes in the insured’s risk profile.
- The Report sheet is currently a placeholder and can be expanded into a full management-ready narrative.

---

## Tools Used

- Microsoft Excel (data manipulation, pivot tables, calculations)
- Actuarial principles: pure premium / experience rating, large-loss loading, expense & profit loading

---


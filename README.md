# Peloton Interactive — Distressed Credit Analysis

A professional-grade distressed credit model for **Peloton Interactive, Inc. (NASDAQ: PTON)**, built to analyse near-term liquidity, capital structure risk, and creditor recovery outcomes. The model is structured in the format used by restructuring advisory firms and distressed debt investors.

---

## Table of Contents

- [Overview](#overview)
- [Investment Thesis & Key Risk](#investment-thesis--key-risk)
- [Model Structure](#model-structure)
- [Key Findings](#key-findings)
- [File Reference](#file-reference)
- [Methodology](#methodology)
- [Data Sources](#data-sources)

---

## Overview

Peloton executed one of the most dramatic operational turnarounds in recent consumer hardware history — moving from burning **$470m of cash in FY2023** to generating **$401m of free cash flow** in the LTM period ending Q3 FY2026. Despite this, the company carries **$1,332.5m of debt concentrated in a 2029 maturity wall**, making it a classic distressed credit story: operationally recovering, but structurally fragile.

This model was built to answer four questions:

1. How has the financial trajectory evolved? *(Historical Financials)*
2. Who does Peloton owe money to, and when? *(Capital Structure)*
3. Will the company run out of cash before 2029? *(Liquidity Runway)*
4. If forced to sell or restructure today, who gets paid back and how much? *(Recovery Analysis)*

---

## Investment Thesis & Key Risk

### The Bull Case
Peloton's EBITDA turnaround is real and accelerating. At $465.8m of LTM EBITDA and a subscription base generating ~$1.66bn of recurring revenue, the company has the cash generation to service its debt and potentially self-fund a meaningful portion of the 2029 maturity. Equity has option value — ~$1.08/share in the base case, ~$3.86/share in the bull case.

### The Bear Case
The 2029 debt wall of **$1,332.5m** is the single point of failure. If credit markets tighten, EBITDA deteriorates, or the company cannot refinance at acceptable terms, recovery collapses: term loan holders recover only **67.2 cents on the dollar**, and unsecured convertible note holders and equity receive **zero**.

### The Key Question
Can Peloton sustain its EBITDA trajectory long enough to refinance $1.3bn of maturities in 2029 on acceptable terms?

---

## Model Structure

The Excel workbook (`data/Peloton_Distressed_Credit_Analysis.xlsx`) contains five sheets:

| Sheet | Purpose |
|---|---|
| **Cover** | Executive summary, key metrics at a glance, table of contents |
| **Historical Financials** | Income statement, balance sheet, and credit metrics — FY2023 through LTM Q3 FY2026 |
| **Capital Structure** | Full debt table, maturity schedule, covenant analysis, credit ratios |
| **Liquidity Runway** | Quarterly cash projection Q3 FY2026–Q3 FY2027; base case vs. stress scenario |
| **Recovery Analysis** | Bear/Base/Bull EV scenarios; creditor waterfall; recovery rates by stakeholder |

### Formatting Conventions

The model follows industry-standard colour coding:

| Colour | Meaning |
|---|---|
| 🔵 Blue text | Hardcoded input (raw data from filings) |
| ⚫ Black text | Formula or calculated value |
| 🟢 Green text | Cross-sheet link |

---

## Key Findings

### Financials (LTM Q3 FY2026)

| Metric | Value |
|---|---|
| Revenue | $2,445m |
| Adjusted EBITDA | $466m |
| EBITDA Margin | 19.0% |
| Free Cash Flow | $401m |
| Cash & Equivalents | $1,126m |
| Total Debt | $1,333m |
| Net Debt | $206m |

### Capital Structure Summary

| Instrument | Outstanding | Rate | Maturity | Priority |
|---|---|---|---|---|
| Term Loan | $982.5m | SOFR + 6.00% | May 2029 | 1st Lien Secured |
| Revolver | $0 drawn ($100m capacity) | Floating | 2029 | 1st Lien Secured |
| Convertible Notes | $350.0m | 5.50% fixed | Dec 2029 | Senior Unsecured |

> ⚠️ **72% of total debt matures in 2029.** Both financial covenants are springing (inactive unless the revolver is drawn). As of Q3 FY2026, the revolver is fully undrawn.

### Liquidity Runway

| Metric | Base Case | Stress Case |
|---|---|---|
| Starting Cash | $1,126m | $1,126m |
| Cumulative FCF (Q3 FY2026–Q3 FY2027) | $306m | $32m |
| Ending Cash (Q3 FY2027) | $1,485m | $1,211m |
| 2029 Debt Maturity | $1,333m | $1,333m |
| Cash vs. Debt Wall | **+$153m** | **-$121m** |
| Liquidity Covenant Headroom | $1,235m | $961m |

### Recovery Analysis

| Stakeholder | Face Value | Bear Recovery | Base Recovery | Bull Recovery |
|---|---|---|---|---|
| Revolver | $100m (undrawn) | 100.0¢ | 100.0¢ | 100.0¢ |
| Term Loan | $982.5m | **67.2¢** | 100.0¢ | 100.0¢ |
| Convertible Notes | $350.0m | **0.0¢** | 100.0¢ | 100.0¢ |
| Equity | — | **$0** | ~$1.08/share | ~$3.86/share |

> Bear case assumes EBITDA $220m × 3x = EV $660m. Base assumes $450m × 4x = $1,800m. Bull assumes $600m × 5x = $3,000m.

---

## File Reference

```
peloton-distressed-analysis/
│
├── README.md                                  ← You are here
│
├── data/
    └── Peloton_Distressed_Credit_Analysis.xlsx   ← Main model (5 sheets)


```

---

## Methodology

In brief:

- **Historical financials** sourced directly from SEC filings; no adjustments beyond management's stated "Adjusted EBITDA" definition
- **Liquidity runway** built as a bottom-up quarterly cash waterfall; stress scenario applies simultaneous EBITDA haircut, capex step-up, and working capital drag
- **Recovery analysis** uses EBITDA × EV multiple methodology standard in leveraged finance; EV multiples calibrated to comparable distressed consumer hardware precedents
- **Covenant analysis** based on credit agreement terms disclosed in the FY2025 10-K

---

## Data Sources

All figures are sourced from publicly available SEC filings and company disclosures:

- Peloton FY2025 Annual Report (10-K)
- Peloton Q3 FY2026 Quarterly Report (10-Q)
- Peloton Q3 FY2026 Earnings Presentation
- SEC EDGAR: [https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=PTON](https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=PTON)

---

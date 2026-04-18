<div align="center">

# Ecommerce Conversion Funnel Analysis
### Tracing $7.69M in Lost Revenue Across a 4-Stage Purchase Journey

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Analytics-150458?logo=pandas&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-Visualization-3F4F75?logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-2ea44f)

**[View Full Notebook](https://github.com/[YOUR_USERNAME]/[YOUR_REPO]/blob/main/Funnel_Analysis.ipynb)** • **[LinkedIn](https://linkedin.com/in/saswata-ghosh06)**

</div>

---

## In One Line

A US-based ecommerce company converts only **10.80%** of sessions into purchases — despite 10,000 monthly sessions and strong top-of-funnel engagement. This analysis maps every drop-off point, quantifies the revenue leak, and translates findings into six prioritized business actions.

> **The core finding:** 69.35% of users who reach checkout never complete the purchase.  
> **The dollar value of fixing it:** $7.69 million.

---

## Table of Contents

- [Business Problem](#business-problem)
- [Dataset and Scope](#dataset-and-scope)
- [Analytical Approach](#analytical-approach)
- [Tools Used](#tools-used)
- [KPI Summary](#kpi-summary)
- [Funnel Performance](#funnel-performance)
- [Channel Analysis](#channel-analysis)
- [Regional Performance](#regional-performance)
- [Time-Based Behavior](#time-based-behavior)
- [Financial Impact](#financial-impact)
- [Recommendations](#recommendations)
- [Business Impact Projection](#business-impact-projection)
- [Repo Structure](#repo-structure)

---

## Business Problem

The company generates consistent traffic but converts 1 in 10 sessions into revenue.

**The question this analysis answers:**  
*Where exactly are users dropping off, why does it happen, and how much does each drop-off cost the business?*

This is not a traffic acquisition problem. The users are arriving. Something in the funnel is breaking before they pay.

---

## Dataset and Scope

| Attribute | Detail |
|---|---|
| Sessions Analyzed | 10,000 |
| Time Period | October 1–31, 2025 |
| Source | Synthetic dataset — self-generated for portfolio analysis |
| Funnel Stages | Browse → Add to Cart → Checkout → Purchase |

**Dimensions analyzed:**

| Dimension | Values |
|---|---|
| Marketing Channel | Organic, Social Media, Email, Google Ads |
| Device Type | Desktop, Mobile, Tablet |
| Region | East, West, North, South |
| Product Category | Beauty, Electronics, Home, Apparel |

---

## Analytical Approach

The analysis follows a structured, layered methodology:

**Step 1 — Data Validation:** Checked for null values, duplicate session IDs, and inconsistent funnel stage sequencing before any metric calculation.

**Step 2 — Funnel Construction:** Defined each stage transition explicitly. A session was counted at a given stage only if it had a recorded event at that stage. Checkout abandonment = sessions with a Checkout event but no Purchase event.

**Step 3 — Segmentation:** Funnel metrics were sliced by channel, region, device, product category, hour, and day to isolate where drop-off varies from the average.

**Step 4 — Financial Quantification:** Used actual AOV ($1,089) to convert percentage drop-offs into dollar figures, making recommendations directly comparable for business prioritization.

**Assumptions made:**
- Each `session_id` maps to one unique user visit
- Revenue is attributed to the Purchase stage only
- Checkout abandonment excludes technical errors (no error logs available in dataset)

---

## Tools Used

| Tool | Purpose |
|---|---|
| Python (Pandas, NumPy) | Data wrangling, funnel calculation, aggregation |
| Matplotlib, Seaborn | Static charts and stage breakdowns |
| Plotly | Interactive funnel dashboard |
| Jupyter Notebook | End-to-end analysis and narrative |
| GitHub | Version control and portfolio publishing |

---

## KPI Summary

| Metric | Value |
|---|---|
| Total Sessions | 10,000 |
| Total Orders | 1,080 |
| **Overall Conversion Rate** | **10.80%** |
| Total Revenue | $1,176,406 |
| Average Order Value (AOV) | $1,089 |
| Avg. Session Duration | 4.08 minutes |

---

## Funnel Performance

<div align="center">
  <img src="https://github.com/user-attachments/assets/a4844afb-d11b-4957-873a-6bf83e0834e4" width="800" alt="Funnel Rates">
  <br>
  <img src="https://github.com/user-attachments/assets/72a4e1df-d967-4ce3-8b85-2af7184bfc4f" width="800" alt="Funnel Dashboard">
</div>

| Funnel Stage | Sessions In | Sessions Out | Conversion Rate | Drop-Off Rate |
|---|---|---|---|---|
| Browse → Add to Cart | 10,000 | 7,059 | 70.59% | 29.41% |
| Add to Cart → Checkout | 7,059 | 3,524 | 49.92% | 50.08% |
| **Checkout → Purchase** | **3,524** | **1,080** | **30.65%** | **69.35% ⚠️** |

**The top of the funnel is healthy.** 7 in 10 browsers add items to cart — product interest is strong.

**The problem compounds mid-funnel.** Half of cart users do not reach checkout. This points to shipping cost friction or a confusing cart-to-checkout transition.

**The final stage is where revenue dies.** 69.35% of users who are already on the payment screen leave without buying. These are not casual browsers. They committed to a purchase and walked away in the last 60 seconds of their journey. This is the single highest-leverage metric in the business.

---

## Channel Analysis

<div align="center">
  <img src="https://github.com/user-attachments/assets/9199b00e-f080-4409-9330-6b6585edeccd"  width="4470" height="1586" alt="Channel Performance">
</div>

| Channel | Total Sessions | Conversion Rate | Total Revenue |
|---|---|---|---|
| Organic | 2,511 | **11.19%** | ~$307K |
| Google Ads | 2,560 | 11.02% | ~$306K |
| Social Media | 2,440 | 10.78% | ~$286K |
| Email | 2,489 | 10.21% | ~$277K |

All four channels perform within a narrow 1% band. Channel is not the primary conversion driver — the broken checkout experience affects all of them equally. Fixing the funnel bottom will lift revenue across every channel simultaneously.

Organic leads narrowly, confirming that intent-driven traffic performs best. For constrained budgets, Organic SEO retains cost efficiency without sacrificing conversion quality.

---

## Regional Performance

<div align="center">
  <img src="https://github.com/user-attachments/assets/81fadb70-6957-491d-bd41-36b527010f91" width="800" alt="Regional Performace">
</div>

| Region | Sessions | Conversion Rate | Total Revenue | AOV |
|---|---|---|---|---|
| South | 2,506 | **11.25%** | $311,019 | $1,103 |
| East | 2,514 | 11.14% | $301,767 | $1,078 |
| North | 2,504 | 10.42% | $288,028 | $1,104 |
| West | 2,476 | 10.38% | $275,592 | $1,072 |

South and East lead in both conversion rate and revenue. North and West underperform despite comparable session volumes — a localization or fulfillment gap, not a traffic gap.

The South region's higher AOV ($1,103) alongside a higher conversion rate suggests users here buy more expensive products and complete purchases more reliably — a pattern worth replicating.

---

## Time-Based Behavior

<div align="center">
  <img src="https://github.com/user-attachments/assets/7b5b9565-18ab-4611-be88-bcaa2877ed4d" width="800" alt="Time-Based Behaviour">
</div>

Session volume is consistent across October, ranging from 270 to 370 sessions per day. Conversion rate fluctuates between 6.27% and 13.54%, a 2x variance that points to external triggers (promotions, events) more than organic patterns.

Mid-week days (Tuesday, Wednesday) show higher conversion rates than weekends. Weekend traffic is browsing behavior. Email and retargeting campaigns should align with mid-week windows.

The daily performance table from the notebook confirms the highest-converting single day was October 23 (13.54%) and the lowest was October 31 (6.27%) — both worth investigating for campaign or seasonal causes.

---

## Financial Impact

The business does not have a discovery problem. Users find products, add them to cart, and reach checkout. Revenue is lost after that.

| Metric | Value |
|---|---|
| Users reaching checkout | 3,524 |
| Users who purchased | 1,080 |
| Users who abandoned at checkout | **2,444** |
| Average Order Value | $1,089 |
| **Recoverable Revenue** | **$7,691,176** |

This $7.69M is not speculative. It represents users who had already decided to buy, reached the payment screen, and stopped. Recovering even 20% of them adds $1.5M without touching traffic or marketing spend.

---

## Recommendations

Ranked by expected impact and implementation speed:

### 1. Fix the Checkout Experience
The 69.35% checkout drop-off controls all other metrics. Simplify the payment flow, reduce the number of steps, enable guest checkout, and add wallet integrations (Google Pay, Apple Pay). This is a product fix with immediate, measurable impact.

### 2. Show Shipping Costs Earlier
Surface delivery costs at the cart stage, not at checkout. Last-minute cost reveals are the most common trigger for abandonment after commitment.

### 3. Deploy Cart Abandonment Recovery
Automate email sequences at 1 hour, 24 hours, and 72 hours after checkout abandonment. A 10% recovery rate on 2,444 abandoned checkouts adds $2.66M in revenue without acquiring a new user.

### 4. Optimize Mobile Checkout
Mobile users drop off at checkout at a disproportionate rate. Add autofill, reduce form fields, and test payment UI on small screens. High reach, low implementation cost.

### 5. Replicate South Region Patterns
South converts at 11.25% with the highest AOV. Audit what differs — product mix, shipping speed, pricing, localized offers — and apply those patterns to North and West.

### 6. Shift Campaigns to Mid-Week
Move promotional pushes to Tuesday and Wednesday evenings. Weekend traffic is browsing behavior. Aligning campaigns with high-intent windows improves conversion without increasing spend.

---

## Business Impact Projection

**If Checkout-to-Purchase conversion improves from 30.65% to 40%:**

| Metric | Current | Projected |
|---|---|---|
| Checkout sessions | 3,524 | 3,524 |
| Purchases | 1,080 | 1,410 |
| Monthly Revenue | $1,176,406 | ~$1,535,000 |
| **Monthly increase** | — | **~$358,000** |
| **Annual impact** | — | **~$4.3M** |

No new traffic. No new products. One metric, moved 10 percentage points.

---

<div align="center">

**Saswata** — Data Analyst  
SQL • Python • Power BI • Tableau  
[LinkedIn](https://linkedin.com/in/saswata-ghosh06) • [GitHub](https://github.com/Saswataghosh06)


</div>

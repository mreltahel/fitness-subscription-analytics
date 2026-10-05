# Fitness Subscription Analytics

## Overview

FitnessHub, a subscription-based fitness platform, has seen rapid customer growth over the past two years but also noticeable early-subscription cancellations. This project analyzes customer and transaction data to answer three business questions for the executive team:

1. After how many months do customers typically cancel their subscriptions?
2. What is the expected subscription revenue over the next 12 months?
3. How long does it take the 2024 and 2025 customer cohorts to recover their customer acquisition cost (CAC)?

**Tools:** Power BI Desktop
**Data:** `data/Fitness_Subscriptions_Dataset.xlsx` (customers and transactions worksheets)

## Key Findings

### 1. Customer Cohort Analysis — When do customers cancel?

The cohort retention matrix (`Customer Cohort` page) shows a consistent pattern across every signup month from January 2024 through December 2025:

- Month 0 → 1: roughly 100% → 85% retained
- Month 1 → 2: roughly 85% → 78% retained
- **Month 2 → 3: roughly 78% → 50% retained — the single largest drop in the subscription lifecycle**

After month 3, the decline becomes much more gradual, a few percentage points per month.

**Takeaway:** nearly a third of each cohort cancels between months 2 and 3. This is the critical window for retention efforts; a targeted intervention (check-in, incentive, or engagement campaign) timed around month 2 is likely to have the largest impact on overall retention.

### 2. Revenue Forecast — What's expected over the next 12 months?

The `Revenue Forecast` page plots monthly subscription revenue from January 2024 onward and applies Power BI's built-in forecast (12-month horizon, seasonality = 12, 95% confidence interval).

- Revenue has grown steadily and smoothly since January 2024, with no visible cyclical pattern tied to particular months or seasons.
- The forecast projects continued growth, reaching approximately **$210,500/month by April 2026** (95% confidence range: roughly $191,000–$230,000).

**Does the forecast show evidence of seasonality?** No. The historical revenue line is a smooth, continuous climb with no repeating bumps or dips at particular times of year. Growth appears to be driven by steady customer acquisition rather than any seasonal cycle.

### 3. CAC vs. LTV — How long to break even?

The `CAC vs. LTV` page compares cumulative customer lifetime value (LTV) against each cohort's own total customer acquisition cost (CAC) for the 2024 and 2025 cohorts, over their first 9 months (the longest window with complete data for both cohorts). Both cohorts are plotted on the same chart, each against its own CAC benchmark.

| Cohort | Break-even point |
|---|---|
| 2024 | ~Month 4–5 |
| 2025 | ~Month 4–5 |

**Takeaway:** both cohorts recover their acquisition cost on a similar timeline, around month 4 to 5. Unit economics appear stable year over year rather than improving or worsening, FitnessHub is acquiring 2025 customers at a scale and cost that tracks closely with the revenue they generate, consistent with the 2024 cohort's performance. This is a reasonable signal for the sustainability of the company's growth strategy, though there is room to improve the break-even timeline itself (for example, through pricing, upsells, or targeting higher-value acquisition channels).

## Executive Summary

FitnessHub's growth strategy appears sustainable: both the 2024 and 2025 customer cohorts recover their acquisition cost on a similar timeline (around month 4–5), and overall subscription revenue is forecast to keep growing steadily with no seasonal headwinds. However, retention is a clear area for improvement — nearly a third of each cohort cancels between months 2 and 3 of their subscription. We recommend the retention team prioritize engagement and intervention efforts specifically targeted at customers approaching their second month, since this is where the largest, most consistent drop-off occurs across every cohort analyzed. Shortening the CAC break-even window (currently 4–5 months) would further strengthen unit economics and could be explored through pricing, upsells, or more efficient acquisition channels.

## Repository Structure

```
fitness-subscription-analytics/
│
├── README.md
├── report.pbix
│
├── data/
│   └── Fitness_Subscriptions_Dataset.xlsx
│
└── screenshots/
    ├── cohort_analysis.png
    ├── revenue_forecast.png
    ├── cac_vs_ltv.png
    └── data_model.png
```

## How to Explore the Report

Open `report.pbix` in Power BI Desktop. The report contains three pages:

- **Customer Cohort** — retention heatmap by signup month and months since signup
- **Revenue Forecast** — monthly subscription revenue with a 12-month forecast
- **CAC vs. LTV** — cumulative LTV vs. total CAC, filterable by 2024/2025 cohort

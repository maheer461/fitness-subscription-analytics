# FitnessHub Subscription Analytics Project

## Overview

FitnessHub has seen rapid customer growth over the past two years, but leadership has observed significant early-lifecycle cancellations without a clear picture of *when* customers churn or whether current acquisition spend is sustainable. This project analyzes customer and transaction data in Tableau to answer three core business questions: when customers typically cancel, what subscription revenue is expected over the next 12 months, and how long it takes the 2024 and 2025 customer cohorts to recover their acquisition cost.

The analysis uses two data sources: a **customers** table (signup, plan, country, acquisition channel, and CAC) and a **transactions** table (individual revenue events per customer). Three Tableau report pages were built to support this analysis: **Customer Cohort**, **Revenue Forecast**, and **CAC vs. LTV**.

---

## 1. Customer Cohort Analysis: When Do Customers Cancel?

A cohort retention matrix was built grouping customers by signup month and tracking the percentage of each cohort still active in each subsequent month of tenure.

**Retention by tenure month:**

| Tenure Month | Retention % |
|---|---|
| 0 | 100% |
| 1 | 85% |
| 2 | 78% |
| 3 | 50% |
| 4 | 47% |

**Key finding:** Retention holds relatively steady through month 2, then drops sharply — a 28-percentage-point decline between month 2 and month 3, the single largest drop in the customer lifecycle. Retention stabilizes after month 4.

**Conclusion:** Customers most commonly cancel around **month 3** of their subscription. This is the critical window where FitnessHub should concentrate retention efforts (e.g., engagement campaigns, check-ins, or incentives timed just before month 3).

---

## 2. Revenue Forecast: What's Expected Over the Next 12 Months?

Monthly subscription revenue was plotted from January 2024 through the latest available data, and Tableau's built-in forecasting model was applied (12-month forecast length, seasonality of 12, 95% confidence interval, using all available history).

**Key finding:** Total forecasted subscription revenue over the next 12 months is **$2,281,315**.

**Seasonality assessment:** Historical revenue grew consistently month over month — from ~$6K in January 2024 to ~$183K in December 2025 — with no recurring dip or spike tied to a particular time of year. Notably, the December 2024 → January 2025 transition showed continued growth ($63K → $69K), not a seasonal decline. The forecast model projects a drop in January 2026 (to ~$165K), but this is not supported by any comparable pattern in the historical data and should be treated as a modeling artifact rather than confirmed seasonality — likely a result of only two years of history being available to detect a reliable yearly cycle. **We do not find clear evidence of seasonality** in subscription revenue at this time; the dominant pattern is steady, sustained growth.

---

## 3. CAC vs. LTV: How Long to Break Even?

Cumulative average revenue per customer (LTV) was tracked by tenure month for the 2024 and 2025 signup cohorts, and compared against the average customer acquisition cost (CAC) of **$178.90**.

| Cohort | Break-even Tenure Month | Cumulative LTV at Break-even |
|---|---|---|
| 2024 | Month 5 | $200.76 |
| 2025 | Month 6 | $186.36 |

**Key finding:** The 2024 cohort recovered its acquisition cost one month faster than the 2025 cohort (month 5 vs. month 6).

---

## Executive Summary

FitnessHub's subscription business is growing quickly — revenue has climbed steadily from roughly $6K to $183K per month over the past two years, and is forecasted to reach approximately **$2.28M** over the next 12 months. However, growth alone does not guarantee sustainability.

The most pressing concern is timing: customers most commonly cancel around **month 3** of their subscription, but it takes until **month 5–6** for a cohort to fully recover its acquisition cost. This means a meaningful share of customers are likely churning *before* they become profitable, directly undermining the payback on acquisition spend. Compounding this, the 2025 cohort is taking a full month longer to break even than the 2024 cohort, suggesting acquisition efficiency may be softening — whether due to rising CAC, a shift in acquisition channel mix, or slower early engagement among newer customers.

**Recommendation:** FitnessHub's near-term revenue trajectory is strong, but the gap between the month-3 churn cliff and the month-5/6 break-even point represents real risk to the growth strategy's sustainability. Leadership should prioritize retention interventions in the first 2–3 months of the customer lifecycle, and investigate why the 2025 cohort's acquisition cost recovery has slowed relative to 2024, before continuing to scale acquisition spend at the current rate.

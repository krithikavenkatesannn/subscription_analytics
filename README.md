# Steamify — Subscription Revenue & Retention Analysis (2023–2024)

## Overview
Steamify is a subscription-based digital streaming platform offering multiple plans: Basic, Premium, Duo, Student, and Annual. This analysis examines subscription performance from 2023 to 2024 across 28K → 19K paid users to understand how retention, pricing, trial conversion, and plan migration evolved over time.

The objective is to identify why Net Revenue Retention fell below 100% and what operational changes can restore sustainable growth.

This project delivers insights and recommendations in the following areas:

- **Subscription Growth & Revenue:** Month-over-month (MoM) and year-over-year (YoY) MRR trends, ARPU, Net Revenue Retention (NRR), and revenue lost.
- **Retention & Churn Behavior:** Customer survival analysis, cohort retention performance, churn by lifecycle stage, and early vs. long-term churn patterns.
- **Plan Performance & Economics:** Revenue, revenue lost, ARPU, LTV, and churn rate broken down by plan type.
- **Trial Conversion & New User Acquisition:** Trial funnel performance, new paid user volume, and new MRR trends.
- **Plan Migration & Expansion Behavior:** Upgrade vs. downgrade rates, plan migration matrix, and expansion revenue trends.

> **NOTE:** The analysis includes dynamic cohort retention (tracking new users only), plan migration matrices, and monthly trend data that can be utilized in Power BI.

---

## Data Processing
- Original dataset in Excel can be found [here](#)
- Steps taken to clean inconsistencies and non-sensical values are detailed [here](#)
- Data analysis and DAX measures in Power BI can be found [here](#)

---

## Executive Summary

![Dashboard Overview](images/overview_dashboard.png)

Steamify shifted from growth to contraction between 2023 and 2024:

- **Paid users declined from 28K to 19K (-32%)** despite ARPU steadily rising from ₹18 (Jan 2023) to ₹21 (Dec 2024), indicating pricing improvements partially offset user loss but failed to stabilize revenue.
- **NRR peaked at 104.44% in February 2023 then declined for 25 consecutive months**, crossing below 100% in March 2024 and hitting a dataset low of 98.45% in October 2024 — confirming the business is in structural contraction.
- **Revenue leakage widened dramatically:** Revenue lost increased from ₹212K to ₹298K (+40%), while new MRR contributed only ~₹9K/month, creating a 33× gap between revenue lost and revenue gained.
- **Churn rate held stable at 4–5% through all of 2023**, then crept upward to a persistent 5–6% band from July 2024 onwards — the deterioration is slow and structural, not a sudden event.
- **Early churn improved significantly (26% → 6%)**, suggesting onboarding improvements worked. However, long-term retention collapsed — among new users, M11 retention dropped from 60% to 42%, indicating mid-lifecycle failure.
- **Two-thirds of churn happens within the first two renewals (67.75%)** — new users adopt successfully but fail to build sustained engagement.
- **Trial conversion was volatile throughout** — dipping as low as 6.4% (Aug 2023) and 6.9% (Apr 2024) — with no sustained recovery, reducing new subscriber inflow.

> **NOTE:** MoM MRR growth turned consistently negative starting January 2024, confirming the decline is structural, not seasonal. All cohort retention metrics below track new users from their signup month.

---

## Insights Deep Dive

### Subscription Growth & Revenue

Steamify processed over 28K paid users at peak (Dec 2023), declining to 19K paid users (Dec 2024), generating an average ARPU of ₹21 and NRR of 99.22% by end of period.

In terms of revenue, 2023 saw peak MRR at ~₹520K (Dec 2023), with strong positive MoM growth ranging from +1.8% to +25.4%. 2024 saw consistent decline, with MRR falling from ₹510K (Jan) to ~₹379K (Dec), and negative MoM growth in 8 of 12 months (worst: -8.0% in Feb, -6.4% in Sep).

The year-over-year trend reversed sharply — NRR peaked at 104.44% in February 2023, declined steadily across 25 months, crossed below 100% in March 2024 (100.04%), and hit the dataset low of 98.45% in October 2024. ARPU, by contrast, rose consistently from ₹18 to ₹21 across the same period — meaning Steamify was earning more per user while losing users faster.

Revenue lost increased from ₹212K (2023) to ₹298K (2024), representing a +40% increase in churn-related revenue leakage. Meanwhile, new MRR remained flat at ~₹9K/month, creating a 33× gap that makes growth impossible without retention improvements.

**Month-over-Month Trends:**

| Period | MRR Range | MoM Growth Range | NRR Range | Churn MRR Range |
|---|---|---|---|---|
| 2023 (Feb–Dec) | ₹218K → ₹520K | +1.8% to +25.4% | 102–104% | ₹10K → ₹24K |
| 2024 (Jan–Dec) | ₹510K → ₹379K | -8.0% to +3.9% | 98–101% | ₹24K → ₹27K |

Key observations:
- 2023 growth phase: Every month showed positive MoM growth, with March (+25.4%) and July (+12.6%) as standout months, likely driven by seasonal promotions or feature launches.
- 2024 contraction phase: Negative MoM growth in 8 of 12 months. February (-8.0%) and September (-6.4%) recorded the sharpest declines.
- Churn MRR nearly tripled from early 2023 (₹10K) to peak 2024 (₹27K), indicating worsening retention efficiency over time.
- NRR crossed below 100% in March 2024 and never recovered, staying at 98–99% through year end.
- October 2024 NRR hit 98.45% — the lowest point in the dataset, confirming structural deterioration.

---

### Retention & Churn Behavior

The following retention metrics track cohorts of new users from their signup month. Survival curve and retention rates reflect only new users, not existing subscribers.

**Lifecycle retention decline for new users (2023 vs 2024 cohorts):**

| Metric | 2023 Cohorts | 2024 Cohorts | Change |
|---|---|---|---|
| Early churn % (first 30 days) | 26% | 6% | ✅ +20 pp improvement |
| M1 retention (new users) | 77% | 65% | ❌ -12 pp |
| M6 retention (new users) | ~63% | 51% | ❌ -12 pp |
| M11 retention (new users) | 60% | 42% | ❌ -18 pp |

**Churn concentration among new users:**
- 67.75% of all churn from new user cohorts occurs within the first 2 renewals — new users adopt but don't stay.
- Only 0.62% of new users (2023 cohorts) survived beyond 10 renewals, improving slightly to 3.52% for 2024 cohorts.

**Monthly churn by plan (2024, all users):**

| Plan | Churn Rate |
|---|---|
| Premium | 6.52% |
| Student | 5.67% |
| Basic | 5.49% |
| Duo | 4.59% |
| Annual | 1.08% |

Key takeaway: Onboarding improvements for new users succeeded (early churn 26% → 6%), but new users who survive past month 1 still leave at high rates before month 6. The mid-lifecycle engagement gap — not acquisition — is the primary driver of contraction. Churn rate also crept from a stable 4–5% band in 2023 to a persistent 5–6% band by late 2024, confirming the problem is worsening, not stabilizing.

---

### Plan Performance & Economics

**Revenue concentration & LTV by plan (2024):**

| Plan | Revenue | Revenue Lost | ARPU | LTV | Churn Rate | % of New Users |
|---|---|---|---|---|---|---|
| Basic | ₹1.9M | ₹102K | ₹69 | ₹1,359 | 5.49% | 45% |
| Premium | ₹1.8M | ₹120K | ₹78 | ₹1,539 | 6.52% | 29% |
| Duo | ₹1.3M | ₹62K | ₹136 | ₹2,663 | 4.59% | 3% |
| Annual | ₹0.3M | ₹3K | ₹120 | ₹2,357 | 1.08% | 17% |
| Student | ₹0.2M | ₹10K | ₹21 | ₹421 | 5.67% | 6% |

Key observations:
- Highest-grossing plans overall: Basic (₹1.9M) and Premium (₹1.8M) together account for ₹3.7M in revenue (68% of total), but both show elevated churn (5.5–6.5%).
- Top two revenue-generating plans (Basic + Premium) contribute 68% of total revenue but also represent 70% of revenue lost (₹222K of ₹298K).
- Highest LTV plans: Duo (₹2,663) and Annual (₹2,357) — yet they represent only 20% of new users (17% Annual + 3% Duo).
- Lowest churn plan: Annual at 1.08% — 6× more stable than Premium — making it the most reliable revenue source.
- Highest churn plan: Premium at 6.52%, nearly double the rate of Annual and 1.5× higher than Basic.
- Lowest LTV plan: Student at ₹421, with 5.67% churn, suggesting poor unit economics.

---

### Trial Conversion & New User Economics

**Trial funnel metrics (2023 vs 2024):**

| Metric | 2023 | 2024 | Change |
|---|---|---|---|
| Trial users (monthly avg) | ~1.4K | ~1.5K | Stable (+7%) |
| Trial → Paid conversion | 7.9% | 8.0% | Volatile, no sustained improvement |
| New paid users (monthly avg) | ~454 | ~545 | Flat |
| New MRR (monthly avg) | ~₹8K | ~₹9K | Flat |
| Revenue lost (monthly avg) | ~₹18K | ~₹25K | +39% |

**New user distribution by plan (2024):**

| Plan | % of New Users |
|---|---|
| Basic | 45% |
| Premium | 29% |
| Annual | 17% |
| Student | 6% |
| Duo | 3% |

Key observations:
- Trial acquisition remains stable (~1.5K users/month), indicating sustained interest in Steamify.
- Trial conversion was volatile throughout both years — dipping as low as 6.4% (Aug 2023) and 6.9% (Apr 2024) — with no consistent recovery trend.
- New paid users flat at ~545/month — insufficient to offset monthly churn MRR of ₹24K–₹27K.
- New MRR (~₹9K/month) is 33× smaller than annualized revenue lost (₹298K) — the growth engine cannot compensate for churn.
- 45% of new users choose Basic — the lowest-LTV plan among non-student tiers. Only 20% choose high-retention plans (Annual + Duo).

---

### Plan Migration & Expansion Behavior

**Upgrade vs. downgrade trend (2023):**

| Period | Upgrade Rate | Downgrade Rate |
|---|---|---|
| Jan 2023 | 13.5% | 5.8% |
| Mar 2023 | 7.6% | 4.0% |
| May 2023 | 8.6% | 3.8% |
| Jul 2023 | 12.1% | 3.6% |
| Sep 2023 | 11.8% | 4.0% |
| Nov 2023 | 3.9% | 2.9% |

**Plan migration matrix highlights:**
- Premium → Basic: 4.0% of Premium users downgrade.
- Premium → Duo: 1.5%.
- Duo → Basic: 0.5%.
- Basic → Premium: only 2.8% upgrade.
- Student → Basic: 3.5%.

Key observations:
- Upgrade rates declined sharply from ~13.5% (early 2023) to ~3.9% (late 2023) — a 71% relative collapse in willingness to pay more.
- Downgrade rates increased over time — users moving from Premium/Duo toward Basic/Student, reducing ARPU.
- Plan migration is net negative — more users move down than up, eroding average revenue per user.
- By 2024, downgrade rates began converging with upgrade rates, further compressing expansion revenue.

---

### Renewal Timing Distribution

| Renewal Timing | Number of Users |
|---|---|
| 1–7 days | 35.5K |
| Immediate | 22.0K |
| 15–30 days | 19.3K |
| 8–14 days | 12.2K |
| 31–60 days | 5.8K |

Key observations:
- Immediate and 1–7 day renewals dominate (57.5K users combined), indicating most users who stay do so quickly after billing.
- Delayed renewals (15–60 days) correlate with higher churn risk — users who take longer to renew are more likely to downgrade or churn.
- 5.8K users take 31–60 days to renew — this segment represents the highest churn risk and should be targeted for re-engagement.
- Downgrades are rising among delayed renewers, suggesting users are reconsidering value during the gap between billing and renewal decision.

---

## Recommendations

### Subscription Growth & Revenue

**Maximize retention of high-LTV plans (Annual & Duo):** Since Annual (1.08% churn, ₹2,357 LTV) and Duo (4.59% churn, ₹2,663 LTV) show superior economics, prioritize these plans in promotions. Ensure sufficient onboarding support for these tiers, highlight their value proposition, and consider seasonal discounts (between September and December) or limited-time offers to convert trial users directly into Annual plans.

**Stabilize Premium plan to protect high-value revenue:** Premium generates ₹1.8M revenue but has the highest churn rate (6.52%). Audit feature differentiation vs. Basic, add exclusive content or features, and test win-back offers for downgrading Premium users. Reducing Premium churn by 1.5 points would recover ~₹270K annually.

**Improve retention of new users & fix mid-lifecycle gap:** 67.75% of churn from new user cohorts happens within first 2 renewals. Launch post-trial engagement campaigns at weeks 4, 8, and 12 for new users. Identify usage drop-off signals (e.g., <3 logins/week) and trigger re-engagement flows. Improving M6 retention for new users from 51% to 60% would add ~₹500K in annualized revenue.

---

### Trial Conversion & New User Acquisition

**Stabilize and improve trial-to-paid conversion:** Trial conversion has been volatile (6.4%–9.3%) with no sustained upward trend. Implement in-trial onboarding emails, feature highlights at day 3 and day 7, and personalized offers before trial expiration. The goal is a consistent floor above 8.5%, not occasional peaks.

**Shift new user acquisition toward high-retention plans:** 45% of new users choose Basic (lowest LTV among non-student tiers). Promote Annual plan with discount (e.g., 2 months free) during trial signup. Highlight Duo plan in family/shared account messaging. Target: Increase Annual + Duo share of new users from 20% → 35%.

**Increase new paid user volume above churn rate:** New paid users flat at ~545/month, while monthly churn MRR is ₹24K–₹27K. Target 700+ new paid users/month through trial optimization, referral programs, and retargeting of abandoned trials.

---

### Plan Migration & Expansion

**Rebuild upgrade engine:** Upgrade rates fell from 13.5% → 3.9% — a 71% collapse. Identify upgrade triggers (usage thresholds like 5 devices, 3 simultaneous streams). Add in-app upgrade prompts at natural moments (e.g., "You've reached your device limit — upgrade to Premium for unlimited access"). Test limited-time upgrade discounts.

**Reduce downgrade migration:** Downgrades rising from Premium → Basic and Duo → Student. Add mid-tier benefits (e.g., "Premium Lite") to catch downgrading users before they drop to Basic. Analyze downgrade reasons via exit surveys and address top 2 complaints.

**Close the 33× revenue gap:** New MRR = ₹9K/month vs. revenue lost = ₹298K/year (₹25K/month). Focus on reducing churn by 1–2 points (worth ~₹50K–₹100K annually) before increasing acquisition spend. Set NRR alert at <100% for 2 consecutive months, triggering retention review.

---

### Retention & Engagement

**Fix M3–M6 retention gap for new user cohorts:** M6 retention for new users dropped from 63% → 51%. Launch post-trial engagement campaigns at weeks 4, 8, and 12 for new users. Identify usage drop-off signals (e.g., <3 logins/week, no playlist creation) and trigger re-engagement flows with personalized content recommendations.

**Target delayed renewers (highest churn risk):** 5.8K users take 31–60 days to renew. Send automated reminders at day 30, day 45, and day 50 with personalized offers (e.g., 10% off next month if renewing within 48 hours).

**Leverage early churn improvement as a template:** Early churn among new users improved from 26% → 6% — document what changed (onboarding emails, feature highlights, trial support) and apply the same playbook to the M3–M6 lifecycle stage.

---

### Plan & Pricing Strategy

**Increase Annual plan adoption:** Annual has 1.08% churn and ₹2,357 LTV but only 17% of new users. Test annual-only exclusive features (e.g., offline downloads, early access to new content). Offer 20% discount for annual commitment vs. monthly.

**Re-evaluate Student plan economics:** Student has ₹421 LTV (lowest) and 5.67% churn. Consider bundling with other services, adjusting pricing, or adding exclusive student content to improve retention.

**Test Premium Lite tier:** Downgrades from Premium to Basic suggest a missing mid-tier. Introduce "Premium Lite" at a mid-range price point with limited features (e.g., 2 devices, no 4K) to capture downgrading users before they drop to Basic.

---

### Data Quality & Monitoring

**Monitor NRR monthly with action triggers:** If NRR <100% for 2 consecutive months, trigger retention review and escalate to leadership. If NRR <98% for any month, launch immediate win-back campaigns.

**Track new user cohort retention monthly:** Publish monthly cohort retention table (M1, M3, M6, M12) for new users only to all product teams. Set M6 retention as the primary KPI with a target of 60% by Q4 2025.

**Monitor trial conversion volatility:** Track monthly trial-to-paid conversion with control limits. If conversion drops below 7% for 2 consecutive months, trigger a funnel audit — check onboarding email performance, trial feature access, and expiry offer timing.

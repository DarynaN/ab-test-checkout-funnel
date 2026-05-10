# A/B Test Pipeline — Checkout Funnel

Statistical analysis of A/B experiments across a checkout funnel using proportion z-tests.  
The goal was to evaluate whether product changes significantly impacted user conversion across multiple segments.

---

## Business Questions

1. Did the tested product changes significantly improve conversion rates?
2. Do results differ across devices, countries, continents, and traffic channels?
3. Which segments show statistically significant uplift — and which don't?

---

## Dataset

- Source: Google Drive (CSV)
- Size: ~800,000 checkout funnel events
- Period: November 2020 – January 2021
- Tests: 4 A/B experiments
- Funnel stages: new_account, add_shipping_info, add_payment_info
- Segments: overall, device, continent, country, channel

---

## Tools

`Python` `pandas` `scipy` `statsmodels` `Tableau`

---

## Methodology

- Proportion z-test for conversion rate comparison (control vs. test group)
- Significance threshold: α = 0.05
- Tested across 5 segmentation dimensions per experiment
- Final result table: 1,811 rows covering all test × metric × segment combinations

---

## Experimentation Considerations

- Segment-level significance can differ from aggregate results
- Small sample segments increase false negative risk
- Statistical significance should be interpreted alongside business impact
  
---

## Key Findings

Most tested changes did not produce statistically significant conversion lifts at the overall level.  
Segment-level analysis revealed that significance varied by device and geography — some segments showed meaningful uplift while others showed no effect or negative trends.  
This highlights the importance of segment-level reporting rather than relying solely on aggregate results.

---

## Business Recommendation

- Do not roll out changes globally based on aggregate results alone
- Prioritize segment-level analysis before making product decisions
- Re-test in segments where results were borderline significant with larger sample sizes

---

## Dashboard

[View on Tableau Public →](https://public.tableau.com/app/profile/daryna.nakonechna/viz/ABTestingAnalyticsStatisticalValidation/ViewSignificance)

---

## Files

| File | Description |
|------|-------------|
| `ab_test_analysis.ipynb` | Full analysis notebook |
| `dashboard_screenshot.png` | Tableau dashboard preview |

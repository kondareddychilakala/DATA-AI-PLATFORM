# Power BI Prompt Reporting

## Objective

Enable prompt-assisted Power BI report design while keeping reporting governed through semantic views.

The AI layer should assist with:

- Requirement capture.
- Metric and dimension mapping.
- Report layout suggestions.
- DAX measure recommendations.
- Semantic view selection.
- Governance validation.
- Lineage explanation.

## Example Prompt

```text
Create a monthly customer onboarding dashboard by segment, branch, and status.
```

## Expected Interpretation

```json
{
  "report_name": "Customer Onboarding Dashboard",
  "metrics": ["onboarding_count", "active_customer_count", "rejected_applications"],
  "dimensions": ["month", "segment", "branch", "status"],
  "semantic_view": "denodo_customer_gold_view",
  "filters": ["date_range", "customer_type", "region"],
  "recommended_visuals": [
    "monthly trend",
    "branch comparison",
    "segment distribution",
    "status breakdown"
  ]
}
```

## Governance Rule

Power BI should connect to approved semantic views, not raw operational tables.

```text
Prompt -> BI metadata mapping -> Denodo semantic view -> Power BI model/report
```


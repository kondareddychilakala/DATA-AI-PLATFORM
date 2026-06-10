# Denodo SQL Template Examples

These are sample public-safe templates. They are intentionally generic.

## Customer Count By Date Range

```json
{
  "template_id": "customer_count_by_date_range",
  "intent": "customer_metric",
  "denodo_view": "bv_customer_gold",
  "parameters": ["start_date", "end_date", "status"],
  "pii_level": "low",
  "approved_for_ai": true
}
```

```sql
SELECT
  COUNT(*) AS customer_count
FROM bv_customer_gold
WHERE onboarding_date BETWEEN :start_date AND :end_date
  AND (:status IS NULL OR status = :status);
```

## Transaction Amount By Status

```json
{
  "template_id": "transaction_amount_by_status",
  "intent": "transaction_metric",
  "denodo_view": "bv_transaction_gold",
  "parameters": ["start_date", "end_date", "status"],
  "pii_level": "medium",
  "approved_for_ai": true
}
```

```sql
SELECT
  status,
  COUNT(*) AS transaction_count,
  SUM(amount) AS total_amount
FROM bv_transaction_gold
WHERE transaction_date BETWEEN :start_date AND :end_date
GROUP BY status;
```

## Changed Customers From CDC

```json
{
  "template_id": "changed_customers_after_last_cdc",
  "intent": "cdc_customer_lookup",
  "denodo_view": "bv_customer_cdc_changes",
  "parameters": ["last_load_timestamp"],
  "pii_level": "medium",
  "approved_for_ai": true
}
```

```sql
SELECT
  customer_id,
  change_type,
  change_timestamp
FROM bv_customer_cdc_changes
WHERE change_timestamp > :last_load_timestamp;
```


# MCP Tool Contracts

MCP-style tools provide controlled execution between the AI reasoning layer and enterprise systems.

## Recommended Tools

```text
get_business_glossary
get_denodo_views
get_metric_templates
run_governed_denodo_query
get_table_lineage
get_powerbi_metadata
get_governance_policy
retrieve_document_context
validate_answer
```

## Governed Query Tool

### Request

```json
{
  "template_id": "customer_count_by_date_range",
  "parameters": {
    "start_date": "2026-06-01",
    "end_date": "2026-06-30",
    "status": "ACTIVE"
  },
  "user_context": {
    "role": "business_analyst",
    "region": "default"
  }
}
```

### Response

```json
{
  "rows": [
    {
      "customer_count": 1245,
      "source_system": "core_banking",
      "lineage_ref": "lineage.customer.gold.v1"
    }
  ],
  "columns": ["customer_count", "source_system", "lineage_ref"],
  "answer_text": "Customer count for the selected period is 1,245.",
  "governance_flags": ["approved_metric", "pii_safe"],
  "lineage": ["source -> bronze -> silver -> gold -> denodo_view"],
  "confidence": 0.94,
  "source": "denodo"
}
```

## Document Retrieval Tool

### Request

```json
{
  "query": "What is the customer onboarding definition?",
  "domain": "customer",
  "allowed_roles": ["business_analyst"]
}
```

### Response

```json
{
  "chunks": [
    {
      "document_id": "policy_customer_onboarding",
      "title": "Customer Onboarding Policy",
      "chunk_id": "chunk_004",
      "text": "Customer onboarding is the approved process of registering, validating, and activating a customer relationship.",
      "classification": "internal",
      "owner": "Customer Data Office"
    }
  ],
  "confidence": 0.88,
  "source": "document_rag"
}
```


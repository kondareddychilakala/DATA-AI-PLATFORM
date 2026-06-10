# Governance, Security And Compliance

## Governance Principles

The platform is designed around the following principles:

- No direct LLM access to raw databases.
- Metric answers must come from governed semantic views.
- Document answers must come from approved document sources.
- PII must be masked, restricted, or blocked based on policy.
- Answers must be grounded in retrieved data or documents.
- All AI tool calls must be auditable.

## Security Controls

Recommended controls:

- Role-based access control.
- Data masking.
- PII classification.
- Approved SQL templates.
- Document-level access metadata.
- Prompt and response logging.
- Tool execution logging.
- Result set size limits.
- Query allowlists.
- Prohibited prompt categories.

## Compliance Alignment

The design supports:

- Traceable data access.
- Source lineage.
- Business definition consistency.
- Audit evidence.
- Separation of duties.
- Controlled self-service analytics.
- Reduced risk of hallucinated metrics.

## Answer Validation

Before returning an answer, validate:

- Numeric values match retrieved result rows.
- Response uses only retrieved context.
- PII rules are respected.
- Source lineage is available.
- Confidence meets threshold.
- Restricted data is not exposed.
- Hybrid answers do not mix document assumptions with metric values.


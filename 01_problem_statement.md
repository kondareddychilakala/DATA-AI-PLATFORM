# Problem Statement

Banks want to use AI to improve analytics, reporting, knowledge discovery, and business self-service. However, banking data is highly regulated and cannot be exposed through uncontrolled AI access.

Common challenges:

- Data is spread across core banking, CRM, cards, payments, risk, finance, and reporting systems.
- Business definitions vary across teams.
- Analysts depend on manual SQL, Excel, and report requests.
- Data lineage and ownership are difficult to trace.
- AI responses can hallucinate if not grounded in trusted enterprise context.
- Raw data access creates security and compliance risks.
- Documents, policies, runbooks, and data definitions are disconnected from reporting systems.

## Architecture Challenge

The platform must support AI-assisted access while preserving:

- Governance
- Security
- Lineage
- Compliance
- Business definitions
- PII controls
- Auditability
- Numeric accuracy

## Target Outcome

Create a governed Data + AI platform where:

- Metrics come from approved semantic views.
- Documents come from approved knowledge indexes.
- AI execution is controlled through MCP-style tools.
- Answers are grounded, validated, and auditable.


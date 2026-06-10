# Solution Architecture

## Solution Summary

The solution combines a data lakehouse, semantic layer, MCP tool layer, and hybrid RAG architecture.

```text
Data Foundation + Semantic Governance + Controlled AI Tooling = Trusted Banking AI
```

## Governed Metrics Path

Used for:

- KPIs
- Counts
- Aggregations
- Reporting
- Customer analytics
- Account analytics
- Transaction analytics
- Fraud and collections analytics

Flow:

```text
Prompt
-> Intent and entity extraction
-> Metric classification
-> MCP governed query tool
-> Approved SQL template
-> Denodo semantic view
-> Governed result set
-> Grounded answer
-> Validation
```

## Document RAG Path

Used for:

- Policy explanation
- Business glossary
- Data catalog help
- Architecture documentation
- Operating procedures
- Runbooks

Flow:

```text
Prompt
-> Intent and entity extraction
-> Document RAG route
-> Approved document index
-> Retrieved chunks
-> Grounded answer
-> Validation
```

## Hybrid Path

Used when the prompt requires both metric data and explanation.

Example:

```text
Show customer onboarding count this month and explain what onboarding means.
```

Metric answer comes from Denodo.

Definition comes from document RAG.

The final answer keeps both sources traceable.


# Hybrid RAG Design

## Why Hybrid RAG?

Banking questions are not all the same.

Some questions require governed structured data:

```text
How many customers were onboarded this month?
```

Other questions require document knowledge:

```text
What is the customer onboarding policy?
```

Some questions require both:

```text
Show onboarding count this month and explain the definition of onboarding.
```

Hybrid RAG separates these access patterns.

## Routes

### Route 1: Governed Metrics Path

For structured, numeric, reporting, KPI, and analytics questions.

Source of truth:

- Denodo semantic views.
- Approved SQL templates.
- Curated Gold data products.

### Route 2: Document RAG Path

For unstructured knowledge and explanation questions.

Source of truth:

- Approved documents.
- Policies.
- Glossary.
- Runbooks.
- Architecture notes.

### Route 3: Hybrid Path

For questions requiring both data and explanation.

Rules:

- Numeric results must come from governed data.
- Definitions and explanations must come from retrieved documents.
- Sources must be kept separate in the final answer.

### Route 4: Clarification

Used when:

- Intent confidence is low.
- Required entity is missing.
- Prompt is ambiguous.
- User requests restricted data.

## Router Payload

```json
{
  "prompt": "",
  "intent": "",
  "entities": [],
  "route": "governed_denodo | document_rag | hybrid | clarification",
  "confidence": 0.0,
  "required_tools": [],
  "policy_checks": []
}
```


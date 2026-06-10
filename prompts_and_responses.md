# Sample Prompts And Responses

## Governed Metric Prompt

Prompt:

```text
How many customers were created this month?
```

Route:

```text
Governed Denodo Path
```

Response:

```text
The customer count created this month is 1,245. The result is based on the approved customer gold view in the semantic layer, filtered by onboarding date for the current month.
```

## CDC Prompt

Prompt:

```text
Which customers changed after the last CDC load?
```

Route:

```text
Governed Denodo Path + CDC metadata
```

Response:

```text
The latest CDC load identified 38 changed customer records. The changes were captured from the operational customer source through CDC and made available for downstream lakehouse processing.
```

## Document RAG Prompt

Prompt:

```text
What is the definition of customer onboarding?
```

Route:

```text
Document RAG Path
```

Response:

```text
Customer onboarding is the approved process of registering, validating, and activating a customer relationship according to bank policy. This answer is based on the approved business glossary and onboarding procedure document.
```

## Hybrid Prompt

Prompt:

```text
Show onboarding count this month and explain what onboarding means.
```

Route:

```text
Hybrid Path
```

Response:

```text
The onboarding count this month is 1,245 from the governed customer metric view. The definition of onboarding is retrieved from the approved business glossary. Metric source and definition source are kept separate for traceability.
```

## Power BI Prompt

Prompt:

```text
Create a dashboard for customer onboarding by month, segment, and branch.
```

Route:

```text
Governed BI Metadata Path
```

Response:

```text
Recommended report: Customer Onboarding Dashboard.
Measures: onboarding count, active customer count, rejected applications.
Dimensions: month, segment, branch, status.
Source: governed customer gold semantic view.
Suggested visuals: monthly trend, branch comparison, segment distribution, status breakdown.
```


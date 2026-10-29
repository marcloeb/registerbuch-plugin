---
name: check
description: Check Swiss companies against the official register — status, recent publications, bankruptcies
---

# /check

Check one or more Swiss companies in the SHAB register, each finding with its signed PDF.

Argument: [company names or UIDs, comma-separated]

## Usage

```
/registerbuch:check Muster AG
/registerbuch:check Muster AG, Beispiel Bau GmbH, CHE-123.456.789
```

## Instructions

1. One company → `search_shab` with `query` (or `uid`) and `days: 400`.
2. Several companies → ONE call to `check_companies` with all names. Do not call it once per company.
3. Matching is exact (company name, UID digits, named co-debtor). «Muster» without «AG» finds nothing. If a name finds nothing, say so and suggest the full legal name or the UID.
4. Present each company: published events with type, date and PDF link; for bankruptcies the creditor filing deadline. Name companies without findings explicitly as «nothing published».
5. Follow the `swiss-register` skill for notes, provenance and the purpose limitation.

## Output Format

```
[n] companies checked, [m] with findings

[Company] — [CHE-UID]
  • [date] [event type] — [one-line summary]  [PDF]
    Filing deadline: [date]
[Company] — nothing published in the period
```

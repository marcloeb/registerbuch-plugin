---
name: claim-check
description: Check a text that makes claims about Swiss companies against the official register before it is sent. Activates when the user wants to verify, fact-check or proofread a report, client mail, memo or another model's answer that names Swiss companies, officers, auditors or bankruptcies.
---

# Claim Check

Use `verify_claims` whenever being wrong about a Swiss company would be expensive: a due-diligence memo, a client mail, a board paper, or an answer another model wrote.

## Workflow

1. Take the text as the user gave it. Do not rewrite it before checking.
2. Call `verify_claims` once with the full text. Do not assemble the same answer by hand from `search_shab`, `search_persons` and the other register tools.
3. Present the result **per statement**: the claim, the verdict, and the signed document behind it (date + PDF link).
4. Where the tool abstains because no complete source exists, say so plainly. An abstention is not a confirmation and not a refutation.
5. If the user wants a corrected version, change only the statements the check contradicted, and cite the document for each change.

## Rules

- Never turn the counts in `aggregate` into a percentage or an overall «accuracy score».
- Keep `contentLabel` provenance: register facts, estimates and AI-generated text stay distinguishable.
- Persons: the purpose limitation of the `swiss-register` skill applies. Checking that a named person signs for a named company is fine. Building a profile of that person is not.

## Output

```
[n] statements checked

✓ «[statement]» — confirmed
  SHAB [date], [PDF link]
✗ «[statement]» — contradicted: [what the register says]
  SHAB [date], [PDF link]
– «[statement]» — no complete source ([why])
```

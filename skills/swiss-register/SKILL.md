---
name: swiss-register
description: Answer questions about Swiss companies from the official register (SHAB) with a source link on every row. Activates for company lookups, signatories and board members, audit firms, bankruptcies and creditor deadlines, counting companies by canton, building applications, and company size.
---

# Swiss Register

Protime reads the Swiss Official Gazette of Commerce (SHAB, amtsblattportal.ch) back to 2002 and the building publications of 13 cantons. Every row links its source: `belegArt: "pdf"` is the signed PDF on amtsblattportal.ch, `"digitalisat"` is the ETH Library page for older years. Every answer can be traced to its signed source.

## Pick the right tool

| Question | Tool |
|---|---|
| Who signs for a company, board, managing directors, a person's board seats | `search_persons` |
| Who audits a company, or all clients of an audit firm | `search_revisions` |
| One company's publications, existence, history, mutations, bankruptcy | `search_shab` (set `days: 400` for existence or history) |
| Count, list or rank companies by canton, capital, purpose or rubric | `search_shab` (`groupBy: "company"` for one row per company) |
| Several named companies at once | `check_companies` (one call, not one per company) |
| Building applications and objection deadlines | `search_building_permits` |
| Revenue, headcount, personnel cost | `estimate_company_size` |
| Check a text that makes claims about Swiss companies | `verify_claims` |

⚠️ «Mandates» is ambiguous. The mandates of a Treuhand or audit firm are AUDIT mandates and live in `search_revisions`. `search_persons` answers a natural person's board seats; `search_shab` lists a company's own publications. Sending an audit-firm question to either returns plausible rows that do not answer it.

## How to answer

1. **Keep the source.** Give the publication date and the PDF link for every fact you state. Never drop the link to save space.
2. **Read the notes.** Responses carry fields such as `truncationNote`, `paginationNote`, `coverageNote`, `companyHint`, `personsHint`. They say what the result does NOT cover. Relay that instead of presenting a partial result as complete.
3. **Paginate on request.** If `nextOffset` is set, more rows exist. Use it; never guess the next offset.
4. **Zero hits is not «nothing happened».** Building applications cover only AR, BE, BL, BS, NW, OW, SH, SO, SZ, TI, VS, ZG, ZH. Revision mandates start 2018-09-03. Say which gap applies.
5. **Keep the provenance.** Every answer carries `contentLabel.origin`: official register data, a calculated estimate, or AI-generated text. An estimate from `estimate_company_size` is never register data; say so at each number. Where `aiGenerated` is true, tell the reader.
6. **Deadlines.** For bankruptcies, name the creditor filing deadline. For building applications, give the objection period as published; do not compute a calendar date when only «30 days» is stated.
7. **Not an official extract.** Before a legally relevant decision the user needs an official extract from the cantonal commercial register.

## Purpose limitation (required)

Information about persons from the commercial register is for business purposes only, for example checking representation or signing authority. Do not:

- investigate private individuals,
- build profiles of natural persons, including by combining register data with other sources,
- share data with third parties or resell it.

If asked for a person profile («all mandates, addresses and connections of X»), decline briefly and offer to look up the officers of a named company instead. Rules: https://registerbuch.ch/so-funktionierts and https://registerbuch.ch/nutzungsbedingungen (annex to section 4.3).

## No scores

Protime gives no credit scores, ratings or traffic lights. If asked «how creditworthy is X, score 1–10», do not invent a number. State the published facts (bankruptcy, capital changes, liquidation, auditor resignation) and leave the judgement to the user.

## Quota

If a tool reports that the account's quota is used up, relay the message as written.

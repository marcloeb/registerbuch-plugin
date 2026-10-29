# Protime Register

Swiss commercial register for Claude, by blueSky Information GmbH.

Look up any Swiss company in the Swiss Official Gazette of Commerce (SHAB) back to 2002: registrations, mutations, deletions, bankruptcies with creditor filing deadlines. Ask who signs for a company, which audit firm checks its books, count bankruptcies across a canton, check a list of companies at once, or search building applications in 13 cantons. Every answer links its signed source document. Company-size figures are estimates and marked as such. Not an official register extract.

Before you send a report or client mail that names Swiss companies, let Claude check it claim by claim: each statement comes back with a verdict and the official document behind it, or an honest "no evidence".

## Skills

| Skill | Use |
|---|---|
| `/protime-register:check` | Check one or more Swiss companies |
| `swiss-register` | Loads automatically for register questions |
| `claim-check` | Loads automatically when a text about Swiss companies should be verified |

## Connector

The plugin connects to `https://mcp.protime.ai/register/mcp`. On first use you sign in with your Protime account (OAuth). See `CONNECTORS.md`.

## License and service terms

The plugin files (skills, configuration) are MIT-licensed — see `LICENSE`. The Protime service they connect to is not: its use is governed by the Protime terms of service (https://protime.ai/de/terms-of-service), including usage limits beyond which a paid plan is required.

## Data use

Information about persons from the commercial register is for business purposes only. See https://registerbuch.ch/nutzungsbedingungen and https://protime.ai/de/privacy-policy.

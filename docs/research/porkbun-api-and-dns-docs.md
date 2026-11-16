# Automating domain registration and DNS for customers: what one registrar's docs describe

Status: Porkbun's own pages read on 2026-11-16. One registrar only. Nothing was tested and no account was created. Limits, prices and terms change, so re-check the pages before relying on them.

## Three separate things
The person named as owner of a domain, the registrar account that controls it, and the DNS records can be held by different parties. Automating DNS does not by itself require owning the domain.

## What the pages say (quoted where wording matters)
- Registration: Porkbun's API page describes "A clean REST/JSON API to register, renew, transfer and fully manage domains". Source: https://porkbun.com/api/json/v3/documentation
- Dry run: https://porkbun.com/llms.txt says passing `dryRun: true` rehearses a write without performing it, and that on billable operations (`/domain/create`, `/domain/renew`, `/domain/transfer`) it runs the pre-flight checks.
- Spend limit: the API page describes "One monthly limit on what keys and agents buy and on the credit they add ($100 a month until the account holder sets their own)".
- Sandbox: the API page says "A `pk1_sb_` key runs the full lifecycle against an isolated sandbox with fake credit."
- DNS Connect: the guide says a service can send the customer to Porkbun with the exact records needed; "You never handle the customer's Porkbun password, and you get no standing access." Requests are signed with a JWT using HS256, every application is reviewed, and "The customer can revert from the emailed link for 30 days." Source: https://porkbun.com/llms/guides/connect-a-service-to-porkbun-dns
- Subaccounts: a domain can be pushed into a subaccount so that others can manage it "while you retain ownership and control over transfers." Source: https://kb.porkbun.com/article/182-subaccounts-guide
- Account push: "New Porkbun accounts require an ID verification to be completed to enable account transfers." Source: https://kb.porkbun.com/article/72-how-to-push-a-domain-into-another-account This note did not find an API call for the push.

## Open questions
- Whether Porkbun's terms allow one person to hold several accounts was not settled from official terms.
- Other registrars were not checked.

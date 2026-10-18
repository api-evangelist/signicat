---
name: signicat-verify-an-organisation
description: 'KYB: fetch registry data, roles and beneficial owners for a company, then screen it.'
api: openapi/signicat-data-verification-openapi.yml
operations:
- Organization_GetBasicOrganizationInfo_GET
- Organization_GetRoles_GET
- Organization_GetUbo_GET
- OrganizationGlobal_Screening_GET
generated: '2026-10-18'
method: generated
---

# Look up and screen an organisation (Data Verification API)

KYB: fetch registry data, roles and beneficial owners for a company, then screen it.

## Before you start

- Authenticate with an OAuth 2.0 `client_credentials` access token from `https://api.signicat.com/auth/open/connect/token` (scope `signicat-api`), sent as `Authorization: Bearer <token>` (Signicat "Connecting to Signicat APIs" docs).
- Base URL is the `servers` entry in `openapi/signicat-data-verification-openapi.yml`.
- No idempotency-key mechanism is documented in this contract; do not blindly retry create calls — read back state first.

## Steps

1. `Organization_GetBasicOrganizationInfo_GET` (GET /countries/{country}/organizations/{id}) — basic registry information.
2. `Organization_GetRoles_GET` (GET /countries/{country}/organizations/{id}/roles) — board and signatory roles.
3. `Organization_GetUbo_GET` (GET /countries/{country}/organizations/{id}/ultimate-beneficial-owners) — ultimate beneficial owners.
4. `OrganizationGlobal_Screening_GET` (GET /organizations/screening) — sanctions/PEP/adverse-media screening.

See also: mcp/signicat-mcp.yml (the Signicat docs MCP server can answer questions about these flows).

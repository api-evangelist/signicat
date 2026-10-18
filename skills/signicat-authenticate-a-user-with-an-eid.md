---
name: signicat-authenticate-a-user-with-an-eid
description: Create an eID/wallet authentication session, send the user to it, and read the verified identity.
api: openapi/signicat-eid-hub-openapi.yml
operations:
- CreateSession
- GetSession
- CancelSession
generated: '2026-10-18'
method: generated
---

# Authenticate an end user with an eID (Authentication REST API)

Create an eID/wallet authentication session, send the user to it, and read the verified identity.

## Before you start

- Authenticate with an OAuth 2.0 `client_credentials` access token from `https://api.signicat.com/auth/open/connect/token` (scope `signicat-api`), sent as `Authorization: Bearer <token>` (Signicat "Connecting to Signicat APIs" docs).
- Base URL is the `servers` entry in `openapi/signicat-eid-hub-openapi.yml`.
- No idempotency-key mechanism is documented in this contract; do not blindly retry create calls — read back state first.

## Steps

1. `CreateSession` (POST /sessions) — choose allowed providers, flow and callback URLs; redirect the user to the returned authentication URL.
2. `GetSession` (GET /sessions/{id}) — after the callback, read the session status and the returned subject attributes.
3. `CancelSession` (POST /sessions/{id}/cancel) — abandon a session the user did not complete.

See also: mcp/signicat-mcp.yml (the Signicat docs MCP server can answer questions about these flows).

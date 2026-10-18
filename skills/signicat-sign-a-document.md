---
name: signicat-sign-a-document
description: Upload a document, open a signing session for a signer, and read the session result.
api: openapi/signicat-sign-openapi.yml
operations:
- uploadDocument
- createSigningSession
- getSigningSession
- getDocument
generated: '2026-10-18'
method: generated
---

# Sign a document with Sign API v2

Upload a document, open a signing session for a signer, and read the session result.

## Before you start

- Authenticate with an OAuth 2.0 `client_credentials` access token from `https://api.signicat.com/auth/open/connect/token` (scope `signicat-api`), sent as `Authorization: Bearer <token>` (Signicat "Connecting to Signicat APIs" docs).
- Base URL is the `servers` entry in `openapi/signicat-sign-openapi.yml`.
- No idempotency-key mechanism is documented in this contract; do not blindly retry create calls — read back state first.

## Steps

1. `uploadDocument` (POST /documents) — upload the PDF to sign; keep the returned document id.
2. `createSigningSession` (POST /signing-sessions) — reference the document id and signer/eID settings; redirect the end user to the returned signing URL.
3. `getSigningSession` (GET /signing-sessions/{sessionId}) — poll (or react to an Events webhook) until the session reaches a final status.
4. `getDocument` (GET /documents/{documentId}) — download the signed result.

See also: mcp/signicat-mcp.yml (the Signicat docs MCP server can answer questions about these flows).

---
name: signicat-verify-an-id-document
description: Create a dossier, run an identity-verification process with uploaded images, and read the result.
api: openapi/signicat-id-document-and-biometric-verification-openapi.yml
operations:
- createDossier
- createProcess
- setImages
- startVerification
- getProcess
generated: '2026-10-18'
method: generated
---

# Verify an ID document and selfie (Assure API)

Create a dossier, run an identity-verification process with uploaded images, and read the result.

## Before you start

- Authenticate with an OAuth 2.0 `client_credentials` access token from `https://api.signicat.com/auth/open/connect/token` (scope `signicat-api`), sent as `Authorization: Bearer <token>` (Signicat "Connecting to Signicat APIs" docs).
- Base URL is the `servers` entry in `openapi/signicat-id-document-and-biometric-verification-openapi.yml`.
- No idempotency-key mechanism is documented in this contract; do not blindly retry create calls — read back state first.

## Steps

1. `createDossier` (POST /dossiers) — one container per end user.
2. `createProcess` (POST /dossiers/{dossierId}/processes) — choose the verification provider/process.
3. `setImages` (POST /dossiers/{dossierId}/processes/{processId}/images) — upload document front/back and selfie images when you capture them yourself.
4. `startVerification` (POST /dossiers/{dossierId}/processes/{processId}) — trigger the verification.
5. `getProcess` (GET /dossiers/{dossierId}/processes/{processId}) — read status and the verification result.

See also: mcp/signicat-mcp.yml (the Signicat docs MCP server can answer questions about these flows).

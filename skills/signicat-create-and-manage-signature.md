---
name: signicat-create-and-manage-signature
description: Create a signature transaction and manage its lifecycle through checking status and cancellation.
api: openapi/signicat-mobileid-openapi.yml
operations:
- addSignature
- getSignature
- cancelSignature
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/signicat-mobileid-openapi.yml ; every operationId checked against the contract
---

# signicat-create-and-manage-signature

Create a signature transaction and manage its lifecycle through checking status and cancellation.

## Steps

1. 1. Start a new signature transaction using `addSignature` POST /signatures with required request body fields
2. 2. Check the status of an ongoing signature using `getSignature` GET /signatures/{transactionId} with the transaction ID in the path
3. 3. Cancel an ongoing signature using `cancelSignature` DELETE /signatures/{transactionId} with the transaction ID in the path

## Rules

- Use Bearer token authentication with Authorization header
- Transaction operations are idempotent for status checking and cancellation
- Handle errors according to the provider's error response format

---
name: signicat-create-and-manage-verification-process
description: Create a verification process, start the verification, and retrieve the results.
api: openapi/signicat-id-document-and-biometric-verification-openapi.yml
operations:
- createProcess
- startVerification
- getProcess
- getZipFile
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/signicat-id-document-and-biometric-verification-openapi.yml ; every operationId checked against the contract
---

# signicat-create-and-manage-verification-process

Create a verification process, start the verification, and retrieve the results.

## Steps

1. 1. Create a verification process using `createProcess` with the required dossierId path parameter
2. 2. Start the verification using `startVerification` with dossierId and processId path parameters
3. 3. Retrieve the verification results using `getProcess` with dossierId and processId path parameters
4. 4. Download the full result package using `getZipFile` with dossierId and processId path parameters

## Rules

- Authentication uses Bearer token in Authorization header
- Process operations require dossierId and processId path parameters
- The workflow follows a sequential create-start-retrieve-download pattern

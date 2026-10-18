---
name: signicat-create-and-manage-dossier
description: Create a dossier and manage its user data and files through the complete lifecycle.
api: openapi/signicat-id-document-and-biometric-verification-openapi.yml
operations:
- createDossier
- setUserData
- setFiles
- getDossier
- deleteDossier
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/signicat-id-document-and-biometric-verification-openapi.yml ; every operationId checked against the contract
---

# signicat-create-and-manage-dossier

Create a dossier and manage its user data and files through the complete lifecycle.

## Steps

1. 1. Create a new dossier using `createDossier` operation with required dossier data in the request body
2. 2. Set user data for the dossier using `setUserData` operation with the dossierId path parameter and user data in the request body
3. 3. Add files to the dossier using `setFiles` operation with the dossierId path parameter and files in the request body
4. 4. Retrieve the complete dossier with its data using `getDossier` operation with the dossierId path parameter
5. 5. Clean up by deleting the dossier using `deleteDossier` operation with the dossierId path parameter

## Rules

- Use Bearer authentication with Authorization header as shown in auth schemes
- Operations are idempotent where appropriate (PUT for updates, DELETE for removal)
- Handle pagination when retrieving multiple dossiers with getDossiers
- Check for specific error codes in API responses for proper error handling

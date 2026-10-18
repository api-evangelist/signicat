---
name: signicat-upload-and-manage-document
description: Upload a document to Signicat and manage its metadata
api: openapi/signicat-sign-openapi.yml
operations:
- uploadDocument
- getDocumentInfo
- updateDocumentMetadata
- getDocument
- deleteDocument
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/signicat-sign-openapi.yml ; every operationId checked against the contract
---

# signicat-upload-and-manage-document

Upload a document to Signicat and manage its metadata

## Steps

1. 1. Use `uploadDocument` POST /documents to upload a new document
2. 2. Use `getDocumentInfo` GET /documents/{documentId}/metadata to retrieve document metadata
3. 3. Use `updateDocumentMetadata` PATCH /documents/{documentId}/metadata to store optional descriptive data about the document
4. 4. Use `getDocument` GET /documents/{documentId} to retrieve the document content
5. 5. Use `deleteDocument` DELETE /documents/{documentId} to permanently delete the document and its metadata

## Rules

- Authentication uses Bearer token in Authorization header
- Document operations require proper authorization roles
- Operations on documents use documentId path parameter
- Error handling follows standard HTTP status codes

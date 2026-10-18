---
name: signicat-start-and-track-onboarding
description: Start an onboarding process and track its status using the transaction ID.
api: openapi/signicat-reuseid-onboarding-openapi.yml
operations:
- startOnboarding
- getOnboarding
generated: '2026-10-18'
method: generated
generator: extract-docs-artifacts.py skills (deepseek)
source: openapi/signicat-reuseid-onboarding-openapi.yml ; every operationId checked against the contract
---

# signicat-start-and-track-onboarding

Start an onboarding process and track its status using the transaction ID.

## Steps

1. 1. Call `startOnboarding` POST /reuseid/id-onboardings to initiate the onboarding process
2. 2. Extract the transactionId from the response of `startOnboarding`
3. 3. Call `getOnboarding` GET /reuseid/id-onboardings/{transactionId} with the transactionId to check the onboarding status

## Rules

- Use Bearer token auth with Authorization header
- The transactionId from startOnboarding is required for getOnboarding
- Handle errors from both operations according to API responses

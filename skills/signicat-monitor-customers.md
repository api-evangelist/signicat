---
name: signicat-monitor-customers
description: Create a monitor, add organisations or persons to it, and fetch detected changes.
api: openapi/signicat-ongoing-monitoring-openapi.yml
operations:
- CreateMonitor
- AddOrganization
- AddPerson
- GetMonitor
- GetChangesByMonitorId
generated: '2026-10-18'
method: generated
---

# Set up ongoing monitoring of organisations and persons

Create a monitor, add organisations or persons to it, and fetch detected changes.

## Before you start

- Authenticate with an OAuth 2.0 `client_credentials` access token from `https://api.signicat.com/auth/open/connect/token` (scope `signicat-api`), sent as `Authorization: Bearer <token>` (Signicat "Connecting to Signicat APIs" docs).
- Base URL is the `servers` entry in `openapi/signicat-ongoing-monitoring-openapi.yml`.
- No idempotency-key mechanism is documented in this contract; do not blindly retry create calls — read back state first.

## Steps

1. `CreateMonitor` (POST /info/monitor) — create the monitor.
2. `AddOrganization` (POST /info/monitor/{monitorId}/organisations) and/or `AddPerson` (POST /info/monitor/{monitorId}/persons) — enrol subjects with your reference key.
3. `GetMonitor` (GET /info/monitor/{monitorId}) — confirm configuration.
4. `GetChangesByMonitorId` (GET /info/monitor/{monitorId}/changes) — fetch changes detected since enrolment.

See also: mcp/signicat-mcp.yml (the Signicat docs MCP server can answer questions about these flows).

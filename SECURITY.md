# Security Policy

## Public workflow exports

This repository must never contain:

- n8n credential objects or credential IDs
- assessment IDs, API keys, tokens, or private webhook URLs
- n8n instance IDs or workflow IDs
- production customer or order data

Configure credentials only inside your own n8n instance after importing the public workflow.

Public n8n Academy exercise endpoints may remain in the examples when required
for reproducibility. Instance-specific Data Table IDs, project paths, workflow
IDs, and credential references must always be removed.

## Reporting a security issue

If you identify sensitive information in the repository, do not open a public issue containing the secret. Revoke or rotate the affected credential first, then contact the repository owner privately.

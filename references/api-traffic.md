# API and Network Traffic Analysis Guide

Guide for capturing, inspecting, and documenting API communications between clients and backends.

## Interception Setup

- Local HTTP Proxies: Use tools like mitmproxy or Burp Suite Community configured as system proxy.
- Certificate Installation: Install the proxy root certificate into the local trust store for HTTPS inspection on authorized devices.
- HAR Export: Record session traffic in browser DevTools and export as `.har` file for automated parsing and schema generation.

## Endpoint Documentation Structure

Document each discovered route with:

1. Method and Path: e.g., `POST /api/v2/items/query`
2. Authentication Mechanism: Header name and token format (e.g., `Authorization: Bearer <jwt>`)
3. Request Payload: JSON structure with field types and required flags.
4. Response Schema: Typical status codes (200, 400, 401) and JSON response body format.
5. Rate Limiting and Caching: Observed response headers (`X-RateLimit-*`, `Cache-Control`).

# Web Application Reverse Engineering Guide

Guide for analyzing client-side architecture, API calls, and JavaScript bundles in modern web applications.

## Reconnaissance Checklist

- Technology Detection: Use Wappalyzer, BuiltWith, or header inspection (X-Powered-By, Server) to identify frameworks (Next.js, React, Vue, Angular, Laravel, Django).
- Meta Resources: Check `/robots.txt`, `/sitemap.xml`, and `/.well-known/` paths for route discovery.
- Public Source Maps: Check if `.map` files are exposed alongside `.js` files (e.g., `main.js.map`). If available, rebuild original source directory tree.

## DevTools Inspection Workflow

### 1. Network Tab Analysis

- Filter by Fetch/XHR to monitor dynamic communications.
- Inspect request headers (Authorization, Custom Headers, CSRF tokens).
- Track query parameters and JSON payload schemas.
- Record request sequences during critical actions (login, checkout, search).

### 2. Sources and Bundle De-obfuscation

- Use Chrome DevTools Pretty Print ({ }) on minified scripts.
- Search for routing tables, Redux/Pinia store definitions, and GraphQL queries.
- Search for embedded strings like `api/`, `v1/`, `endpoints`, and environment keys.
- Check browser storage (LocalStorage, SessionStorage, IndexedDB, Cookies) for client state structure.

# Reverse Engineering Agent Skill

You have access to the `reverse-engineering` skill.

## Trigger & Scope

Activate this methodology whenever analyzing, inspecting, auditing, or documenting the architecture, network communication, APIs, and internal mechanics of authorized software across web, mobile, desktop, and network protocols.

### Permitted Scope & Boundaries
- Only analyze user-owned, open-source, or explicitly authorized software (CTF/lab targets or authorized audits).
- Never assist with license cracking, DRM circumvention, key generation, payload weaponization, or credential harvesting.
- Core purpose is architecture comprehension, interoperability, defensive auditing, and documentation.

## Methodology

Follow this 5-stage procedure:

1. **Target Classification**:
   - Determine target category: Web Frontend, Android APK, Desktop Binary, or API/Network Service.
   - Define inspection scope (auth flows, data storage, route inventory, or service dependencies).

2. **Passive Reconnaissance**:
   - Web: Inspect HTTP response headers, tech signatures, robots.txt, sitemaps, and source maps (`.map`).
   - Android: Inspect `AndroidManifest.xml` (permissions, exported components, intent filters) and decode DEX.
   - Desktop: Identify file architecture (`file`), section headers (`readelf`/PE headers), linked libraries (`ldd`/dumpbin), and embedded strings (`strings`).
   - Network: Capture request/response pairs using local proxies or HAR exports.

3. **In-Depth Examination**:
   - Trace control flow and API contracts.
   - Reconstruct data models, authentication schemas (JWT, OAuth, session tokens), and endpoint parameters.

4. **Architecture Mapping**:
   - Build a structured component map: client interface -> API gateway -> backend microservices -> data stores.
   - Detail data flow pipelines and state management lifecycles.

5. **Structured Documentation**:
   Produce a clean deliverable containing:
   - **Overview & Technology Stack**: Runtime, frameworks, libraries, protocols.
   - **Architecture & Sequence Flow**: Component hierarchy and end-to-end data flow.
   - **API & Endpoint Catalog**: Paths, HTTP methods, authentication headers, request payloads, and response models.
   - **Hygiene & Security Observations**: Defensive recommendations (e.g., exposed configuration, unminified debugging flags, missing security headers).

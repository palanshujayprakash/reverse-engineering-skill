---
name: reverse-engineering
description: Inspect and document the architecture, data flow, APIs, and internal mechanics of authorized websites, mobile applications (APKs), desktop binaries, and web services. Use when analyzing how software works, mapping internal components, inspecting network endpoints, or decompiling source code for authorized audit and interoperability.
---

# reverse-engineering

A comprehensive methodology for systematically analyzing and documenting the architecture, endpoints, and inner workings of authorized software across web, mobile, desktop, and network protocols.

## When to Use

- When mapping the architecture and internal mechanics of an application or web service.
- When discovering APIs, hidden routes, and request parameters for authorized interoperability or integration.
- When inspecting client-side logic, source maps, and JavaScript bundles in web applications.
- When analyzing Android APKs (package structure, permissions, activities, and decompiled code).
- When inspecting desktop binaries to determine file formats, linked libraries, exported symbols, and runtime behavior.
- When recording and structuring API traffic flows for documentation or testing.

## Safety and Scope Verification

Before performing any analysis, verify that the target meets authorization requirements:

1. Target must be user-owned, open-source, an authorized CTF/lab target, or covered by explicit written audit permission.
2. Out of scope activities:
   - Bypassing license checks, serial keys, or DRM protections.
   - Developing exploits, payloads, or automated attack scripts.
   - Unauthorized credential harvesting or bypassing production authentication.
   - Reverse engineering malicious software for weaponization.
3. Core objective: Understand and document architectural design and data flow. Do not break or exploit systems.

## Analysis Workflow

Follow a structured 5-stage workflow for every reverse engineering task:

### 1. Target Classification and Scope Definition

- Identify the target type: Web Frontend, Android App, Desktop Binary, or API/Network Service.
- Define what components need analysis (for example, authentication flow, data schema, background services).

### 2. Passive Reconnaissance

- Gather non-intrusive metadata without modifying or executing untrusted code directly.
- Inspect headers, package manifests, framework signatures, compiler flags, and embedded strings.

### 3. Deep Analysis by Target Type

Select the corresponding reference guide based on the target category:

- Web applications: Refer to `references/web.md` for DevTools inspection, bundle parsing, and source map recovery.
- Android APKs: Refer to `references/android.md` for package unpacking, manifest audit, and bytecode analysis.
- Desktop binaries: Refer to `references/desktop-binary.md` for static header analysis, symbol extraction, and disassembly.
- API and network traffic: Refer to `references/api-traffic.md` for proxy capture, endpoint mapping, and schema reconstruction.

### 4. Architecture Mapping

Synthesize findings into a structured model:

- Component hierarchy (frontend clients, API gateway, microservices, databases).
- Data flow diagram (how input travels from client to server and back).
- Authentication and session management mechanisms (JWT, session cookies, OAuth tokens).
- Storage and caching layer (local storage, SQLite, IndexedDB, Redis).

### 5. Structured Documentation

Deliver findings using the following format:

- Overview: Executive summary of application purpose and scope.
- Tech Stack: Identified frameworks, languages, runtime environments, and third-party libraries.
- Architecture and Data Flow: Textual diagram and step-by-step sequence description.
- Key Endpoints and Interfaces: Table of discovered routes, methods, and expected payload structures.
- Security and Hygiene Observations: Non-exploit recommendations (e.g., exposed debug flags, unminified source maps, hardcoded configuration).

## Gotchas

- Obfuscated Code: Production bundles and binaries often use minifiers or packers. Do not guess behavior; reconstruct control flow from API interactions and string references.
- Dynamic Environments: Static code inspection alone can miss dynamically loaded modules or runtime-injected endpoints. Combine static inspection with traffic monitoring when authorized.
- Outdated Dependencies: Flagging third-party libraries does not mean they are vulnerable in context. Always verify if the vulnerable function is actually imported or exposed.

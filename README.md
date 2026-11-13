# Reverse Engineering AI Skill

[![Author](https://img.shields.io/badge/Author-palanshujayprakash-blue.svg)](https://github.com/palanshujayprakash)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Type](https://img.shields.io/badge/Type-Agent--Skill-orange.svg)](#)

A modular, cross-platform AI agent skill designed to help AI agents systematically analyze, inspect, and document the architecture, data flow, APIs, and internal mechanics of authorized software across web, mobile, desktop, and network protocols.

---

## Directory Structure

```text
reverse-engineering-skill/
├── .claude-plugin/
│   ├── marketplace.json      # Claude marketplace catalog manifest
│   └── plugin.json           # Plugin definition and metadata
├── skills/
│   └── reverse-engineering/  # Packaged agent skill directory
│       ├── SKILL.md          # Skill definition & agent execution rules
│       └── references/       # Target-specific analysis guides
│           ├── android.md
│           ├── api-traffic.md
│           ├── desktop-binary.md
│           └── web.md
├── references/               # Root references for direct repository use
│   ├── android.md            # Android APK disassembly & manifest analysis
│   ├── api-traffic.md        # Proxy setup & API schema reconstruction
│   ├── desktop-binary.md     # Static binary identification & disassembly
│   └── web.md                # Web applications, bundles & DevTools guide
├── LICENSE                   # MIT License
├── README.md                 # Project documentation & integration guide
└── SKILL.md                  # Main skill definition & agent execution rules
```

---

## Core Capabilities

- **Web Application Deconstruction**: Inspect JavaScript bundles, source maps, client-side routing, and background Fetch/XHR traffic.
- **Android APK Inspection**: Disassemble APKs with `apktool` and `jadx` to audit manifests, permissions, and network security configs.
- **Desktop Binary Analysis**: Static inspection using `file`, `strings`, `readelf`, PE headers, and entry-point analysis via Ghidra/Radare2.
- **API Traffic Capture**: Map endpoints, schemas, authentication headers, and request flows using local proxies or HAR exports.

---

## Responsible Use & Safety Guardrails

This skill enforces strict security and legal boundaries:

1. **Authorized Targets Only**: Target software must be user-owned, open-source, part of an authorized CTF/lab, or covered by explicit written audit permission.
2. **Strict Non-Goals**:
   - Zero tolerance for DRM/license cracking, keygens, or piracy.
   - No exploit development, payload generation, or weaponization.
   - No unauthorized access or credential harvesting.
3. **Primary Mission**: Architecture comprehension, interoperability, educational understanding, and systematic documentation.

---

## Agent Integration Guide

### 1. Claude Code / Cowork

**Option A — Via Plugin Marketplace:**
```bash
/plugin marketplace add palanshujayprakash/reverse-engineering-skill
/plugin install reverse-engineering@reverse-engineering-marketplace
```

**Option B — Manual Skill Copy:**
```bash
mkdir -p .claude/skills/
cp -r skills/reverse-engineering .claude/skills/
```

### 2. Antigravity / Agent Skills Standard / Codex
Copy the skill into the global or project `.agents/skills` directory:
```bash
mkdir -p .agents/skills/
cp -r skills/reverse-engineering .agents/skills/
```

### 3. Cursor / Windsurf
Add the contents of `SKILL.md` to your project rules:
```bash
mkdir -p .cursor/rules/
cp SKILL.md .cursor/rules/reverse-engineering.mdc
```

### 4. Gemini CLI / Custom LLM Agents
Include `SKILL.md` directly in the system prompt or agent instructions:
```python
with open("SKILL.md") as f:
    skill_instructions = f.read()

agent_prompt = f"You have access to the following skill:\n{skill_instructions}"
```

---

## Author & Contact

Maintained by [@palanshujayprakash](https://github.com/palanshujayprakash).

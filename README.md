# Reverse Engineering AI Skill

[![Author](https://img.shields.io/badge/Author-palanshujayprakash-blue.svg)](https://github.com/palanshujayprakash)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Type](https://img.shields.io/badge/Type-Agent--Skill-orange.svg)](#)

A modular, cross-platform AI agent skill designed to help AI agents systematically analyze, inspect, and document the architecture, data flow, APIs, and internal mechanics of authorized software across web, mobile, desktop, and network protocols.

---

## Directory Structure

```text
reverse-engineering/
├── SKILL.md                  # Main skill definition & agent execution rules
├── README.md                 # Project documentation & integration guide
└── references/
    ├── web.md                # Web applications, bundles & DevTools guide
    ├── android.md            # Android APK disassembly & manifest analysis
    ├── desktop-binary.md     # Static binary identification & disassembly
    └── api-traffic.md        # Proxy setup & API schema reconstruction
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
Copy the `reverse-engineering` directory into your project's skills folder:
```bash
mkdir -p .claude/skills/
cp -r reverse-engineering .claude/skills/
```

### 2. Cursor / Windsurf
Add the contents of `SKILL.md` to your project rules:
```bash
mkdir -p .cursor/rules/
cp SKILL.md .cursor/rules/reverse-engineering.mdc
```

### 3. Gemini CLI / Antigravity / Custom LLM Agents
Include `SKILL.md` directly in the system prompt or agent instructions:
```python
with open("SKILL.md") as f:
    skill_instructions = f.read()

agent_prompt = f"You have access to the following skill:\n{skill_instructions}"
```

---

## Quickstart for Local Setup & Push

To push this repository to GitHub under [palanshujayprakash](https://github.com/palanshujayprakash):

```bash
# 1. Initialize local repository
git init -b main

# 2. Add files and make first commit
git add .
git commit -m "feat: initial commit of reverse engineering skill"

# 3. Create repository and push using GitHub CLI
gh repo create reverse-engineering-skill --public --source=. --remote=origin --push
```

Or using standard Git commands after creating `reverse-engineering-skill` on GitHub:
```bash
git remote add origin https://github.com/palanshujayprakash/reverse-engineering-skill.git
git push -u origin main
```

---

## Author & Contact

Maintained by [@palanshujayprakash](https://github.com/palanshujayprakash).

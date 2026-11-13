# Reverse Engineering AI Skill

[![Author](https://img.shields.io/badge/Author-palanshujayprakash-blue.svg)](https://github.com/palanshujayprakash)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Type](https://img.shields.io/badge/Type-Agent--Skill-orange.svg)](#)

A modular, cross-platform AI agent skill designed to help AI agents systematically analyze, inspect, and document the architecture, data flow, APIs, and internal mechanics of authorized software across web, mobile, desktop, and network protocols.

---

## Universal Agent Support

This repository connects seamlessly across all major AI agent environments:

| Agent / Environment | Configuration / Manifest | Auto-Discovery Path |
| :--- | :--- | :--- |
| **Claude Code & Desktop** | `.claude-plugin/plugin.json` | `skills/reverse-engineering/` or `/plugin` marketplace |
| **Universal Agents** | `AGENTS.md` | Standard root `AGENTS.md` context file |
| **Google Antigravity & Gemini CLI** | `gemini-extension.json`, `.antigravity-plugin/` | Global `.agents/skills/` or extension manifest |
| **Cursor AI** | `.cursor/rules/reverse-engineering.mdc` | Project rule automatically loaded by Cursor |
| **Windsurf / Cascade** | `.windsurf/rules/reverse-engineering.md` | Project rule automatically loaded by Cascade |
| **Cline & Roo Code** | `.clinerules/reverse-engineering.md` | Agent system instructions loaded per session |
| **GitHub Copilot** | `.github/copilot-instructions.md` | Copilot custom instructions for workspace |
| **OpenAI Codex** | `.codex-plugin/plugin.json` | Agent plugin skill discovery |
| **Cognition Devin** | `.devin-plugin/plugin.json` | Devin repository integration manifest |
| **Agent Skills Standard** | `.agents/skills/reverse-engineering/` | Cross-platform open agent skills standard |

---

## Directory Structure

```text
reverse-engineering-skill/
├── .agents/
│   └── skills/reverse-engineering/ # Open Agent Skills specification layout
├── .antigravity-plugin/
│   └── plugin.json                 # Google Antigravity extension manifest
├── .claude-plugin/
│   ├── marketplace.json            # Claude marketplace catalog manifest
│   └── plugin.json                 # Claude Code plugin definition
├── .clinerules/
│   └── reverse-engineering.md      # Cline / Roo Code agent instructions
├── .codex-plugin/
│   └── plugin.json                 # OpenAI Codex plugin manifest
├── .cursor/
│   └── rules/reverse-engineering.mdc # Cursor IDE agent rules
├── .devin-plugin/
│   └── plugin.json                 # Devin agent manifest
├── .github/
│   └── copilot-instructions.md     # GitHub Copilot workspace instructions
├── .windsurf/
│   └── rules/reverse-engineering.md # Windsurf / Cascade IDE rules
├── skills/
│   └── reverse-engineering/        # Main packaged skill folder
│       ├── SKILL.md                # Agent execution instructions
│       └── references/             # Target-specific analysis guides
├── references/                     # Root references
├── AGENTS.md                       # Universal AI Agent instructions
├── gemini-extension.json           # Gemini CLI extension configuration
├── LICENSE                         # MIT License
├── README.md                       # Documentation & integration guide
└── SKILL.md                        # Root skill definition
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

**Option B — Global / Project Skill:**
```bash
# Global install (available across all projects)
mkdir -p ~/.claude/skills/
cp -r skills/reverse-engineering ~/.claude/skills/

# Project install
mkdir -p .claude/skills/
cp -r skills/reverse-engineering .claude/skills/
```

### 2. Antigravity / Agent Skills Standard / Codex
Install globally into `~/.agents/skills`:
```bash
mkdir -p ~/.agents/skills/
cp -r skills/reverse-engineering ~/.agents/skills/
```

### 3. Cursor
The rule is pre-configured in `.cursor/rules/reverse-engineering.mdc`. In any project, copy the rule:
```bash
mkdir -p .cursor/rules/
cp .cursor/rules/reverse-engineering.mdc .cursor/rules/
```

### 4. Windsurf / Cascade
The rule is pre-configured in `.windsurf/rules/reverse-engineering.md`.

### 5. Cline / Roo Code
The instructions are pre-configured in `.clinerules/reverse-engineering.md`.

### 6. GitHub Copilot
Workspace instructions are pre-configured in `.github/copilot-instructions.md`.

---

## Author & Contact

Maintained by [@palanshujayprakash](https://github.com/palanshujayprakash).

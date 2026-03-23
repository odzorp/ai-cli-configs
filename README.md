# AI CLI Tools - Complete Config Reference

Complete documentation for all AI CLI tools installed on this machine.

---

## Table of Contents

1. [OpenCode](#opencode)
2. [Claude Code](#claude-code)
3. [Aider](#aider)
4. [Codex CLI](#codex-cli)
5. [Other Tools](#other-tools)

---

## OpenCode

**Command**: `opencode` (built-in)

### Config Location
`~/.config/opencode/`

### Key Configs
- `opencode.json` - Main config
- `AGENTS.md` - 28 agent definitions
- `skills/` - 115+ skills
- `commands/` - 59 slash commands

### Key Settings
- Model: `opencode/big-pickle`
- MCP: GitHub server configured
- Plugins: sessions, smart-title, ignore, synced, snippets, notify
- Permissions: edit=allow, bash=allow
- Compaction: auto=true, reserved=10000

### Sync
```bash
opencode sync --help
```

---

## Claude Code

**Command**: `claude`

### Config Location
`~/.claude/settings.json`

### Key Settings
- 18 plugins enabled
- Fast Mode: enabled
- Permissions: Bash, Read, Write, Edit all allowed
- Security Hook: blocks dangerous commands (rm -rf /, sudo rm, etc.)

### Plugins
- frontend-design, code-review, context7, superpowers
- github, feature-dev, code-simplifier, ralph-loop
- typescript-lsp, playwright, commit-commands
- claude-md-management, figma, firecrawl
- hookify, slack, skill-creator, atlassian

---

## Aider

**Command**: `aider`

### Config Location
`~/.aider.conf.yml`

### Key Settings
- Model: `openai/gpt-4o`
- API Base: `https://opencode.ai/zen/v1`
- Editor: Cursor
- Edit Format: Diff
- Dark Mode: enabled

### Usage
```bash
aider ./project
```

---

## Codex CLI

**Command**: `codex`

### Config Location
`~/.codex/config.toml`

### Key Settings
- Default Model: `gpt-5.4`
- Approval Policy: `on-request`
- Web Search: `live`
- Personality: `pragmatic`
- Reasoning Effort: `medium`
- History: `summarize` at capacity

### Profiles
- `default` - Standard coding
- `fast` - Low reasoning effort
- `deep` - High reasoning effort
- `qa` - Testing focused
- `yolo` - Full auto (dangerous!)

### Platform
- Windows Sandbox: `elevated`
- TUI Theme: `zenburn`

---

## Other Tools

### Installed via npm -g

| Tool | Package | Version | Command |
|------|---------|---------|---------|
| Claude Code | claude | 0.1.1 | `claude` |
| Codex CLI | @openai/codex | 0.116.0 | `codex` |
| Gemini CLI | @google/gemini-cli | 0.34.0 | `gemini` |
| Qwen | @qwen-code/qwen-code | 0.12.6 | `qwen` |
| Cline | cline | 2.8.1 | `cline` |
| Droid | droid | 0.62.1 | `droid` |
| Kilocode | @kilocode/cli, kilocode | 7.0.46, 1.2.0 | `kilocode` |
| OpenCode | opencode-ai | 1.2.27 | `opencode` |
| OpenCLAW | openclaw | 2026.3.2 | `openclaw` |
| GitHub Copilot | @github/copilot | 0.0.421 | `copilot` |
| Sourcegraph Amp | @sourcegraph/amp | 0.0.1771416360 | `src` |

### Kiro CLI
- Requires WSL on Windows
- Install: `curl -fsSL https://sh.kiro.ai | sh`

---

## Quick Reference

### Start Commands
```bash
# Claude Code
claude

# Codex
codex

# OpenCode (built-in)
opencode

# Aider
aider ./project

# Gemini
gemini

# Qwen (NOT qwen-code!)
qwen

# Cline
cline
```

### Environment Variables
```bash
# GitHub Token (for MCP servers)
GITHUB_TOKEN=ghp_xxx

# Alternative API providers
GROQ_API_KEY=xxx
OPENROUTER_API_KEY=xxx
NVIDIA_API_KEY=xxx
CLOUDFLARE_API_KEY=xxx
```

### Aliases (PowerShell)
```powershell
Set-Alias -Name cc -Value claude
Set-Alias -Name cx -Value codex
Set-Alias -Name qw -Value qwen
Set-Alias -Name gm -Value gemini
```

---

## Troubleshooting

### Qwen Command Name
- Use `qwen`, NOT `qwen-code` or `qwencode-cli`

### Codex Ollama Conflict
- If Ollama provider conflicts exist, remove `[model_providers.ollama]` from config

### Kiro on Windows
- Requires WSL installation
- Run in WSL terminal, not PowerShell

---

*Last updated: 2026-03-23*

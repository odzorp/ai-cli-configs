# AI CLI Tools Setup Guide

Quick reference for AI coding CLI tools installed on this machine.

> **Note**: Installation commands are intentionally minimal — just tell AI "install X" and it figures out the rest. This doc focuses on **configurations** and **platform quirks** that AI can't guess.

---

## Tools Overview

| Tool | Command | Status | Notes |
|------|---------|--------|-------|
| Claude Code | `claude` | ✅ Ready | Anthropic's official CLI |
| Codex CLI | `codex` | ✅ Ready | OpenAI's coding agent |
| OpenCode | `opencode` | ✅ Ready | Built-in to this environment |
| OpenCLAW | `openclaw` | ✅ Ready | Code inspection CLI |
| Gemini CLI | `gemini` | ✅ Ready | Google's AI CLI |
| Qwen | `qwen` | ✅ Ready | Alibaba's coder (NOT `qwen-code` or `qwencode-cli`) |
| Cline | `cline` | ✅ Ready | VS Code extension + CLI |
| Cursor | `cursor` | ✅ Ready | AI IDE (GUI-based) |
| Droid | `droid` | ✅ Ready | Android AI coding |
| Kilocode | `kilocode` | ✅ Ready | CLI tool |
| Kiro CLI | `kiro` | ✅ Ready | Amazon Q Developer CLI (requires WSL on Windows) |
| GitHub Copilot | `copilot` | ✅ Ready | GitHub's AI pair programmer |
| Sourcegraph Amp | `src` | ✅ Ready | Sourcegraph CLI |
| Aider | `aider` | ✅ Ready | Terminal-based AI coding |

---

## Quick Start

```powershell
# Start Claude Code
claude

# Start Codex
codex

# Start Qwen
qwen

# Start Gemini
gemini

# Start Aider
aider ./your-project
```

---

## Platform Notes

### Windows (Primary)
- All tools work natively
- Use PowerShell or Git Bash
- Some tools may need WSL for full functionality

### WSL (Secondary)
- Kiro CLI requires WSL: `curl -fsSL https://sh.kiro.ai | sh`

---

## Environment Variables (if needed)

Some tools use API keys. Set these in your shell profile:

```powershell
# Groq (fast inference)
$env:GROQ_API_KEY = "your-key"

# OpenRouter (free models)
$env:OPENROUTER_API_KEY = "your-key"

# NVIDIA NIM
$env:NVIDIA_API_KEY = "your-key"

# Cloudflare AI
$env:CLOUDFLARE_API_KEY = "your-key"
```

---

## Profiles & Aliases

Add to your PowerShell profile (`$PROFILE`):

```powershell
# AI CLI shortcuts
Set-Alias -Name cc -Value claude
Set-Alias -Name cx -Value codex
Set-Alias -Name qw -Value qwen
Set-Alias -Name gm -Value gemini
```

---

## Troubleshooting

### "Command not found"
```powershell
# Check if tool is installed
npm list -g | grep tool-name

# Reinstall if needed
npm install -g package-name --force
```

### Qwen specifically
```powershell
# Command is "qwen", NOT "qwen-code" or "qwencode-cli"
qwen --version  # Correct ✅
qwen-code --version  # Wrong ❌
```

### Codex MCP servers failing
If MCP servers fail due to missing API keys, they can be disabled by removing the `[mcp_servers]` section from config.

---

## Documentation Structure

```
ai-cli-configs/
├── README.md              # This file
├── configs/
│   └── codex-config.toml # Codex configuration
├── scripts/
│   └── set-env.ps1        # Environment variable template
└── NOTES/
    └── quirks.md          # Platform-specific issues
```

---

## Contributing

Found a quirk or fix? Submit a PR!

---

*Last updated: 2026-03-23*

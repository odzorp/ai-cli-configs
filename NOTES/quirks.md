# Platform Quirks & Fixes

Known issues and workarounds discovered during setup.

---

## Windows-Specific Issues

### 1. Codex: Built-in Provider Override Error

**Error:**
```
model_providers contains reserved built-in provider IDs: `ollama`
```

**Cause:** Codex v1+ has built-in Ollama support. Custom `[model_providers.ollama]` in config conflicts with this.

**Fix:** Remove any `[model_providers.ollama]` section from `~/.codex/config.toml`.

---

### 2. Codex: `wire_api` Deprecation

**Error:**
```
wire_api = "chat" is deprecated
```

**Cause:** Old config used `"chat"`, new version expects `"responses"`.

**Fix:** In `~/.codex/config.toml`, replace all instances:
```toml
wire_api = "chat"  # OLD
wire_api = "responses"  # NEW
```

---

### 3. Qwen: Wrong Command Name

**Problem:** `qwencode-cli` or `qwen-code` doesn't work.

**Cause:** Package name is `@qwen-code/qwen-code`, bin command is just `qwen`.

**Fix:**
```powershell
qwen --version  # Correct ✅
```

---

### 4. NPM Bin Symlinks Broken

**Problem:** Command not found after `npm install -g`.

**Fix:**
```powershell
npm install -g package-name --force
```

---

### 5. Kiro CLI on Windows

**Problem:** Kiro is Amazon Q Developer CLI and requires Linux.

**Solution:** Install in WSL:
```bash
# In WSL
curl -fsSL https://sh.kiro.ai | sh
kiro --version
```

---

## General Notes

### Codex MCP Servers
MCP servers require API keys. If keys aren't set, MCP servers will fail to start but Codex still works.

To disable MCP entirely, remove `[mcp_servers]` section from config.

### OpenCode vs Codex
- **OpenCode**: Already integrated in this environment
- **Codex**: OpenAI's CLI, needs separate install

Both can work simultaneously.

---

## Useful Commands

```powershell
# Check all AI CLIs installed
npm list -g | Select-String -Pattern "claude|codex|gemini|qwen|copilot"

# Check specific tool
tool-name --version

# Reinstall if broken
npm install -g package-name --force
```

---

*Last updated: 2026-03-23*

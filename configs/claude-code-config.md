# Claude Code Configuration

Claude Code is installed via npm and has extensive customization.

## Config Files

| File | Purpose |
|------|---------|
| `~/.claude/settings.json` | Main settings |
| `~/.claude.json` | User data and state |
| `~/.claude/credentials.json` | API credentials |

## Current Settings

```json
{
  "enabledPlugins": {
    "frontend-design@claude-plugins-official": true,
    "code-review@claude-plugins-official": true,
    "context7@claude-plugins-official": true,
    "superpowers@claude-plugins-official": true,
    "github@claude-plugins-official": true,
    "feature-dev@claude-plugins-official": true,
    "code-simplifier@claude-plugins-official": true,
    "ralph-loop@claude-plugins-official": true,
    "typescript-lsp@claude-plugins-official": true,
    "playwright@claude-plugins-official": true,
    "commit-commands@claude-plugins-official": true,
    "claude-md-management@claude-plugins-official": true,
    "figma@claude-plugins-official": true,
    "firecrawl@claude-plugins-official": true,
    "hookify@claude-plugins-official": true,
    "slack@claude-plugins-official": true,
    "skill-creator@claude-plugins-official": true,
    "atlassian@claude-plugins-official": true
  },
  "fastMode": true,
  "autoUpdatesChannel": "latest",
  "permissions": {
    "deny": [],
    "allow": ["Bash", "Read", "Write", "Edit"]
  }
}
```

## Key Settings

### Enabled Plugins (18 total)
- `frontend-design` - UI/UX design assistance
- `code-review` - Code review capabilities
- `context7` - Context management
- `superpowers` - Extended capabilities
- `github` - GitHub integration
- `feature-dev` - Feature development
- `code-simplifier` - Code simplification
- `ralph-loop` - Loop/iteration handling
- `typescript-lsp` - TypeScript LSP support
- `playwright` - Playwright testing
- `commit-commands` - Commit message generation
- `claude-md-management` - Markdown management
- `figma` - Figma integration
- `firecrawl` - Web scraping
- `hookify` - Custom hooks
- `slack` - Slack integration
- `skill-creator` - Skill creation
- `atlassian` - Jira/Confluence integration

### Performance
- **Fast Mode**: Enabled (faster responses)
- **Auto Updates**: "latest" channel

### Permissions
- **Bash**: Allowed
- **Read**: Allowed
- **Write**: Allowed
- **Edit**: Allowed
- No restrictions on tool usage

### Security Hooks

Claude Code has a PreToolUse hook that blocks dangerous commands:

```javascript
// Blocks: rm -rf /, sudo rm, dd if=, mkfs
```

## Additional Directories

```
~/.claude/
├── .credentials.json      # API credentials
├── backups/               # Configuration backups
├── cache/                 # Cache files
├── commands/              # Custom commands
├── debug/                 # Debug logs
├── downloads/              # Downloaded files
├── history.jsonl          # Command history
├── ide/                   # IDE configuration
├── plugins/               # Plugin storage
├── projects/              # Project data
├── session-env/           # Session environment
├── shell-snapshots/       # Shell state snapshots
├── skills/               # Additional skills
├── telemetry/             # Telemetry data
├── todos/                # Todo list
└── stats-cache.json       # Usage statistics
```

## Comparison with OpenCode

| Setting | Claude Code | OpenCode |
|---------|-----------|----------|
| Fast Mode | true | - |
| Edit Permission | allow | allow |
| Bash Permission | allow | allow |
| MCP GitHub | via plugin | via MCP config |
| Auto-compaction | - | true (10k reserved) |

---

*Last updated: 2026-03-23*

# OpenCode Configuration

OpenCode is the primary CLI tool in this environment, featuring extensive customization with agents, skills, commands, and MCP integrations.

## Config Files

| File | Purpose |
|------|---------|
| `~/.config/opencode/opencode.json` | Main configuration |
| `~/.config/opencode/opencode.rc` | AgentVision startup hook |
| `~/.config/opencode/opencode-mem.jsonc` | Memory/session data |
| `~/.config/opencode/AGENTS.md` | Agent definitions and instructions |

## Current Configuration

```json
{
  "autoupdate": true,
  "model": "opencode/big-pickle",
  "mcp": {
    "github": {
      "type": "local",
      "command": ["npx", "-y", "@modelcontextprotocol/server-github"],
      "environment": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "{env:GITHUB_TOKEN}"
      }
    }
  },
  "plugin": [
    "opencode-sessions",
    "opencode-smart-title",
    "opencode-ignore",
    "opencode-synced",
    "opencode-snippets",
    "opencode-notify"
  ],
  "permission": {
    "edit": "allow",
    "bash": "allow"
  },
  "compaction": {
    "auto": true,
    "prune": true,
    "reserved": 10000
  }
}
```

## Key Settings

### Model
- **Default**: `opencode/big-pickle` (OpenCode's flagship model)
- Can use custom models via MCP or direct API

### MCP Integration
- **GitHub MCP Server**: Configured with `GITHUB_TOKEN` environment variable
- Uses local npx execution

### Plugins
- `opencode-sessions` - Session management
- `opencode-smart-title` - Smart terminal titles
- `opencode-ignore` - Git-aware file ignoring
- `opencode-synced` - GitHub sync functionality
- `opencode-snippets` - Code snippet management
- `opencode-notify` - Desktop notifications

### Permissions
- **Edit**: Allowed
- **Bash**: Allowed
- (More restrictive than Claude Code's default)

### Compaction (Context Management)
- **Auto-compaction**: Enabled
- **Prune**: Enabled
- **Reserved tokens**: 10,000 (context window buffer)

## AgentVision Integration

The `opencode.rc` file initializes AgentVision on startup:
- Visual agent state representation
- Requires Python with `agentvision` module

## Directory Structure

```
~/.config/opencode/
├── AGENTS.md           # Agent instructions (28 agents)
├── agents/             # Agent definitions
│   ├── code-reviewer.md
│   └── qa-engineer.md
├── commands/           # 59 slash commands
│   ├── agentvision/
│   ├── build-fix.md
│   ├── checkpoint.md
│   ├── code-review.md
│   ├── e2e.md
│   ├── eval.md
│   └── ...
├── skills/             # 115 skills (categorized)
│   ├── README.md
│   ├── 00-andruia-*/
│   ├── ab-test-*/
│   ├── accessibility-*/
│   ├── ...
│   └── zustand-*/
├── plugins/             # Custom plugins
├── prompts/            # Custom prompts
├── tools/              # Tool configurations
├── instructions/       # Instruction sets
├── memory/             # Memory storage
├── cicd-pipeline/      # CI/CD skill
├── cypress-e2e/         # Cypress skill
├── jest-unit/           # Jest skill
├── playwright-api/      # Playwright API skill
├── playwright-e2e/      # Playwright E2E skill
├── vitest-testing/      # Vitest skill
├── k6-performance/     # k6 performance testing
├── graphql-testing/     # GraphQL testing
├── postman-api/         # Postman skill
├── pytest-patterns/      # Pytest skill
├── rest-assured-api/   # REST Assured skill
├── supertest-api/        # Supertest skill
├── owasp-security/       # OWASP security
└── qa-testing-mobile/   # Mobile QA skill
```

## Sync Configuration

OpenCode can sync configs to GitHub:
- Repository: `odzorp/ai-cli-configs`
- Uses `opencode-synced` plugin
- See: `opencode sync --help`

## Environment Variables

```bash
# GitHub Token for MCP server
GITHUB_TOKEN=ghp_xxx

# OpenCode uses its own API key (configured at install)
```

---

*Last updated: 2026-03-23*

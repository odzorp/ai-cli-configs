# Aider Configuration

Aider is a terminal-based AI coding assistant configured to use OpenCode's Zen API.

## Config File

`~/.aider.conf.yml`

## Current Configuration

```yaml
# Aider Configuration for Philip Odzor
# Using OpenCode Zen via OpenAI-compatible API

model: openai/gpt-4o
openai-api-key: sk-nRERw4OkRH23QemzeWvlmtCQ00ZvPvvYOIg6qWC7k8xVfx2Sfgix9qAtYYxJ05MF
openai-api-base: https://opencode.ai/zen/v1

editor: cursor
edit-format: diff
dark-mode: true
```

## Key Settings

### Model & API
- **Model**: `openai/gpt-4o` (OpenAI's GPT-4o)
- **API Base**: OpenCode's Zen API endpoint
- **API Key**: Uses OpenCode's Zen API key

### Editor
- **Editor**: Cursor (configured as default editor)
- **Edit Format**: Diff (git-style diff edits)

### Appearance
- **Dark Mode**: Enabled

## Usage

```bash
# Start aider with a project
aider ./your-project

# Start with specific model
aider --model openai/gpt-4o ./project

# Use diff edit format (default)
aider --edit-format diff ./project
```

## Environment Variables

Aider reads from environment:
- `OPENAI_API_KEY` - Alternative API key method
- `EDITOR` - Fallback editor selection

## Features

- Git-aware editing (commits changes automatically)
- Multiple file editing
- Voice chat support
- Ask mode vs Edit mode
- Polyglot support (many languages)

## Tips

1. Aider works best with git repositories
2. Use `/edit` command for targeted edits
3. Use `/ask` for questions without file changes
4. Use `/commit` to commit current changes

---

*Last updated: 2026-03-23*

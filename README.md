# Nope OpenCode Setup & Skills

AI-assisted development toolkit with custom settings, plugins, skills, and the Ralph automation loop.

> Work in progress! Constantly learning and updating as we go.

## Prerequisites

Before using this toolkit, install the following:

| Tool | Install Command | Purpose |
|------|-----------------|---------|
| **Node.js** | `brew install node` | Runtime for OpenCode |
| **OpenCode CLI** | `npm install -g opencode` | AI coding assistant |
| **jq** | `brew install jq` | JSON parsing for scripts |

Verify installation:
```bash
which opencode && which jq && echo "✅ Ready!"
```

## Quick Start

### 1. Clone & Install Globally

```bash
# Clone the repo
git clone https://github.com/adriiita/nope-opencode.git

# Install the Ralph script globally
mkdir -p ~/.local/bin
cp nope-opencode/nope-ralph.sh ~/.local/bin/
chmod +x ~/.local/bin/nope-ralph.sh

# Add to PATH (add this line to ~/.zshrc)
export PATH="$HOME/.local/bin:$PATH"
```

### 2. Use in Your Project

```bash
# Go to your project folder
cd ~/my-project

# Copy the config file (MUST be named opencode.json)
cp ~/path/to/nope-opencode/nopeopencode.json ./opencode.json

# Start OpenCode and create a PRD
opencode
# Type: /prd-create [your feature description]
# Type: /ralph-convert

# Run the automation loop
nope-ralph.sh
```

## Repository Map

| File | Description |
|------|-------------|
| [nopeopencode.json](nopeopencode.json) | Template config (copy to project as `opencode.json`) |
| [nope-ralph.sh](nope-ralph.sh) | Ralph automation script |
| [commands/](commands/) | Slash commands for OpenCode |
| [skills/](skills/) | Skill definitions |

## Commands

| Command | Description |
|---------|-------------|
| `/prd-create` | Create a Product Requirements Document |
| `/ralph-convert` | Convert PRD to Ralph format |
| `/ralph-iterate` | Execute one Ralph iteration |
| `/compound` | Compound engineering workflow |
| `/playground-create` | Create interactive HTML playground |
| `/review-code` | Code review workflow |

## Skills

- [browser-automation](skills/browser-automation/SKILL.md)
- [compound](skills/compound/SKILL.md)
- [playground](skills/playground/SKILL.md)
- [prd](skills/prd/SKILL.md)
- [ralph](skills/ralph/SKILL.md)
- [ui-skills](skills/ui-skills/SKILL.md)

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `command not found: nope-ralph.sh` | Install to PATH (see Quick Start) |
| `No prd.json found` | Run `/prd-create` then `/ralph-convert` first |
| `jq: command not found` | Install jq: `brew install jq` |
| OpenCode can't find config | Rename to `opencode.json` in project root |

## License

Open for use, customization, and remixing.

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

### 1. Install the Script Globally

```bash
# Install nope-ralph.sh to your PATH
mkdir -p ~/.local/bin
curl -o ~/.local/bin/nope-ralph.sh https://raw.githubusercontent.com/adriiita/nope-opencode/main/nope-ralph.sh
chmod +x ~/.local/bin/nope-ralph.sh

# Add to PATH (add this line to ~/.zshrc if not already there)
export PATH="$HOME/.local/bin:$PATH"
```

### 2. Set Up Your Project

```bash
# Create your project folder
mkdir my-app && cd my-app

# Clone nope-opencode INSIDE your project (as a subfolder)
git clone https://github.com/adriiita/nope-opencode.git

# Copy the config to your project root
cp nope-opencode/nopeopencode.json ./opencode.json
```

Your project structure should look like:
```
my-app/                      ← Project root (run commands from here)
├── nope-opencode/           ← Toolkit folder
│   ├── skills/
│   ├── commands/
│   └── nopeopencode.json
├── opencode.json            ← Config at project root
├── ralph/                   ← Created by the workflow
│   ├── prd.json
│   └── progress.txt
└── src/                     ← Your app code
```

### 3. Create a PRD and Run Ralph

```bash
# From your project root (NOT inside nope-opencode)
cd my-app

# Start OpenCode
opencode

# Create your PRD
# Type: /prd-create [your feature description]
# Type: /ralph-convert

# Run the automation loop
nope-ralph.sh
```

## Repository Map

| File | Description |
|------|-------------|
| [nopeopencode.json](nopeopencode.json) | Template config (copy to project root as `opencode.json`) |
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
| `command not found: nope-ralph.sh` | Install to PATH (see Quick Start step 1) |
| `No prd.json found` | Run from project root (where `opencode.json` is), not inside `nope-opencode/` |
| `jq: command not found` | Install jq: `brew install jq` |
| OpenCode can't find config | Copy `nopeopencode.json` to project root as `opencode.json` |

## License

Open for use, customization, and remixing.

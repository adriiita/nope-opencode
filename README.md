# Nope OpenCode Toolkit

A toolkit for AI-assisted development with OpenCode, featuring skills, commands, and the Ralph automation loop.

## Prerequisites

```bash
# Install required tools
brew install node jq
npm install -g opencode

# Verify
which opencode && which jq && echo "✅ Ready!"
```

## Setup (One-Time)

```bash
# 1. Clone the toolkit
git clone https://github.com/adriiita/nope-opencode.git
cd nope-opencode

# 2. Install the Ralph script globally
mkdir -p ~/.local/bin
cp nope-ralph.sh ~/.local/bin/
chmod +x ~/.local/bin/nope-ralph.sh

# 3. Add to PATH (add to ~/.zshrc)
export PATH="$HOME/.local/bin:$PATH"
```

## Usage (For Each New Project)

```bash
# 1. Set the toolkit path (adjust to where you cloned nope-opencode)
NOPE_TOOLKIT=~/nope-opencode

# 2. Create your project folder (OUTSIDE nope-opencode)
mkdir ~/my-app && cd ~/my-app

# 3. Copy the config file (MUST be named opencode.json)
cp $NOPE_TOOLKIT/nopeopencode.json ./opencode.json

# 4. Start OpenCode and create PRD
opencode
# Type: /prd-create [your feature description]
# Type: /ralph-convert

# 5. Run the automation loop
nope-ralph.sh
```

## Project Structure

```
nope-opencode/              ← Toolkit (clone once, don't modify)
├── skills/                 ← OpenCode skills
├── commands/               ← Slash commands
├── nopeopencode.json       ← Config template
└── nope-ralph.sh           ← Ralph script

~/my-app/                   ← Your project (separate folder)
├── opencode.json           ← Copied from toolkit
├── ralph/                  ← Created by Ralph
│   ├── prd.json
│   └── progress.txt
└── src/                    ← Your app code
```

## Commands

| Command | Description |
|---------|-------------|
| `/prd-create` | Create a PRD |
| `/ralph-convert` | Convert PRD to Ralph format |
| `/ralph-iterate` | Execute one Ralph iteration |

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
| `command not found: nope-ralph.sh` | Run setup step 2 & 3 |
| `No prd.json found` | Run `/prd-create` then `/ralph-convert` first |
| OpenCode can't find config | Ensure `opencode.json` exists in project root |

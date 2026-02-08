# Nope OpenCode Toolkit

A toolkit for AI-assisted development with OpenCode.

## Prerequisites

```bash
brew install node jq
npm install -g opencode
```

## Setup

```bash
# Clone and enter
git clone https://github.com/adriiita/nope-opencode.git
cd nope-opencode

# Rename config (OpenCode requires this name)
mv nopeopencode.json opencode.json

# Install script globally
cp nope-ralph.sh ~/.local/bin/
chmod +x ~/.local/bin/nope-ralph.sh
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

## Usage

```bash
# From inside nope-opencode (or any project with opencode.json)
opencode

# In OpenCode:
# /prd-create Build a tic-tac-toe game
# /ralph-convert

# Then run:
nope-ralph.sh
```

## Commands

| Command | Description |
|---------|-------------|
| `/prd-create` | Create a PRD |
| `/ralph-convert` | Convert PRD to prd.json |
| `/ralph-iterate` | Execute one iteration |

## Troubleshooting

| Issue | Solution |
|-------|----------|
| `command not found: nope-ralph.sh` | Run the setup steps |
| `No prd.json found` | Run `/prd-create` then `/ralph-convert` first |

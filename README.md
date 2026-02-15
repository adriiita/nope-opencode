# Nope OpenCode Toolkit

A toolkit for AI-assisted development with OpenCode.

## Prerequisites

```bash
brew install node jq
npm install -g opencode
```

## Setup

### 1. Clone the toolkit

```bash
git clone https://github.com/adriiita/nope-opencode.git
cd nope-opencode
```

### 2. Configure OpenCode

Copy the config to OpenCode's config directory:

```bash
mkdir -p ~/.config/opencode
cp nopeopencode.json ~/.config/opencode/opencode.json
```

### 3. Authenticate with Antigravity

```bash
opencode auth login
```

Login with your Google account and select **"Configure models in opencode.json"** to auto-configure all models.

> **Tip:** Want bleeding-edge features? The config uses `opencode-antigravity-auth@beta`. Switch to `@latest` for stable.

### 4. Install Ralph globally

```bash
cp nope-ralph.sh ~/.local/bin/
chmod +x ~/.local/bin/nope-ralph.sh
echo 'export PATH="$HOME/.local/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

## Usage

```bash
# From any project directory with opencode.json
opencode

# In OpenCode:
# /prd-create Build a tic-tac-toe game
# /ralph-convert

# Then run:
nope-ralph.sh
```

### Quick test

```bash
opencode run "Hello" --model=google/antigravity-claude-opus-4-6-thinking --variant=max
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
| `command not found: nope-ralph.sh` | Run setup step 4 |
| `No prd.json found` | Run `/prd-create` then `/ralph-convert` first |
| OpenCode can't find config | Copy config: `cp nopeopencode.json ~/.config/opencode/opencode.json` |

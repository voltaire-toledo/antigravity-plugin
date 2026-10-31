# VT Antigravity Plugin Toolkit

A complete, cross-platform developer toolkit and plugin bundle for **Google Antigravity CLI (`agy`)**.

## Features

- ⚡ **Ultra-Fast Statusline**: Sub-15ms statusline renderer in pure standard Python (Nerd Font battery gauge, KV Cache hit dial, turn token burn and cost).
- 🧠 **Team Skills**: Bundled specialized skills including `statusline-manager`.
- 📜 **Shared Team Rules**: Automatic injection of team directives via `rules/AGENTS.md`.
- 🪝 **Lifecycle Hooks Scaffolding**: Support for `PreToolUse`, `PostToolUse`, `PreInvocation`, `PostInvocation`, and `Stop` hooks via `hooks.json`.
- 🔌 **MCP Server Ready**: Built-in `mcp_config.json` scaffolding to expose MCP services across the team.

---

## Directory Architecture

```text
VT-Antigravity-Plugin/
├── plugin.json                 # Plugin manifest declaring name and version
├── hooks.json                  # Lifecycle hooks configuration
├── mcp_config.json             # MCP servers configuration
├── rules/
│   └── AGENTS.md               # Team rules injected when plugin is active
├── skills/
│   └── statusline-manager/     # Specialized statusline diagnostic & management skill
│       └── SKILL.md
├── scripts/
│   ├── statusline.py           # Sub-15ms ANSI truecolor statusline renderer
│   └── test_statusline.py      # Diagnostic runner for statusline telemetry
└── installers/
    ├── install.ps1             # Windows installer & auto-configurator
    └── install.sh              # macOS/Linux installer & auto-configurator
```

---

## Installation for Team Members

### Requirements
- Python 3.8+ (standard library only; no `pip` dependencies needed)
- A terminal emulator configured with a **Nerd Font** (e.g. JetBrains Mono NF, MesloLGS NF)

### Windows (PowerShell)
Open PowerShell and run:
```powershell
.\installers\install.ps1
```
*Creates a Directory Junction in `~/.gemini/config/plugins/vt-antigravity-plugin` and updates `settings.json`.*

### macOS / Linux (Bash)
Open a terminal and run:
```bash
./installers/install.sh
```
*Creates a symbolic link in `~/.gemini/config/plugins/vt-antigravity-plugin` and updates `settings.json`.*

---

## Testing & Verifying Statusline

Run the diagnostic runner to simulate an incoming CLI payload:
```bash
python scripts/test_statusline.py
```
Expected output:
```text
 󰙶 Gemini 2.5 Pro [high]   Context 14.0k / 1M (1.4%)   KV Cache 12.5k ● (89.0% saved)   Last Turn: 1.9k tokens ($0.0009) 
```

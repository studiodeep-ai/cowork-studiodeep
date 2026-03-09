# StudioDeep Claude Plugins

Personal Claude Code plugin marketplace. All plugins live under `plugins/`.

## Structure

```
claude-plugins/
├── .claude-plugin/
│   └── marketplace.json   # Marketplace manifest (studiodeep-plugins)
└── plugins/
    └── media-prompter/    # Edit plugin files here
        ├── .claude-plugin/
        │   └── plugin.json
        ├── commands/
        │   └── media-prompt.md
        └── skills/
            └── media-prompter/
                ├── SKILL.md
                └── references/
                    └── styles.md
```

## Development

Edit files directly under `plugins/<plugin-name>/`. To test changes without reinstalling, use dev mode — it reads source files directly:

```bash
claudemp   # alias for: claude --plugin-dir .../plugins/media-prompter
```

Each new Claude Code session started with `claudemp` picks up the latest file edits. No install step needed.

To validate the plugin structure:

```bash
claude plugin validate plugins/media-prompter
```

## Publishing to local install

The plugin is installed at user scope (available in all projects). After editing source files, push changes to the installed cache:

```bash
claude plugin update media-prompter
```

Installed cache lives at: `~/.claude/plugins/cache/studiodeep-plugins/media-prompter/`

Bump the version in `plugins/media-prompter/.claude-plugin/plugin.json` when making significant changes.

## Adding a new plugin

1. Create `plugins/<new-plugin>/` with the standard structure
2. Add it to `.claude-plugin/marketplace.json` under `"plugins": [...]`
3. Commit the changes
4. Run `claude plugin install <new-plugin>` to install it

## Marketplace registration

The marketplace is registered at user scope — it was added once with:

```bash
claude plugin marketplace add /Users/timdpaep/LocalDev/studiodeep/claude-plugins --scope user
```

This only needs to be done once per machine. On a new machine, re-run that command then `claude plugin install media-prompter`.

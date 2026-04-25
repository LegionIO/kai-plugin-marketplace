# Kai Plugin Marketplace (LegionIO)

Open-source plugin catalog for [Kai Desktop](https://github.com/LegionIO/kai-desktop).

## About

This repository hosts `marketplace.json` — a catalog of community plugins available for installation through Kai's built-in plugin marketplace.

## Adding a Plugin

To list your plugin in this marketplace, submit a PR adding an entry to `marketplace.json`:

```json
{
  "name": "your-plugin-name",
  "displayName": "Your Plugin",
  "description": "What your plugin does",
  "repo": "your-org/kai-plugin-name",
  "version": "1.0.0",
  "author": "Your Name",
  "tags": ["category"],
  "icon": "lucide-icon-name"
}
```

### Fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | Must match the `name` in your plugin's `plugin.json` |
| `displayName` | Yes | Human-readable name shown in the marketplace UI |
| `description` | Yes | Short description of what the plugin does |
| `repo` | Yes | GitHub `owner/repo` — Kai downloads pre-built releases from this |
| `version` | Yes | Semantic version string (Kai downloads from release tag `v{version}`) |
| `author` | No | Author or organization name |
| `tags` | No | Array of category tags for filtering |
| `icon` | No | Lucide icon name for the marketplace UI |

### Plugin Release Requirements

Plugins must publish GitHub releases with:
- **Tag**: `v{version}` (e.g., `v1.0.0`)
- **Asset**: `{name}-v{version}.tar.gz` (e.g., `cron-v1.0.0.tar.gz`)
- **Contents**: Pre-built plugin files (`plugin.json`, `main.js`, `renderer.js`, etc.)

Kai downloads and extracts the release asset directly — no build step runs on the user's machine.

## Schema Version

The `schemaVersion` field at the root of `marketplace.json` indicates the catalog format version. Current version: `1`.

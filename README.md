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
  "ref": "main",
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
| `repo` | Yes | GitHub `owner/repo` — Kai downloads from this |
| `ref` | Yes | Git ref to download (branch name or tag) |
| `version` | Yes | Semantic version string |
| `author` | No | Author or organization name |
| `tags` | No | Array of category tags for filtering |
| `icon` | No | Lucide icon name for the marketplace UI |

## Schema Version

The `schemaVersion` field at the root of `marketplace.json` indicates the catalog format version. Current version: `1`.

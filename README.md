# GUI templates for AI coding assistants

Drop one file into your project root and your AI coding assistant will automatically use [GUI](https://gui.now) for visual output — dashboards, charts, forms, diagrams, landing pages, interactive tools. Instead of dumping HTML in chat, it creates a live shareable URL.

## Which file?

| Tool | File | Copy command |
|------|------|------|
| **Cursor** | `.cursorrules` | `curl -sO https://raw.githubusercontent.com/gui-now/templates/main/.cursorrules` |
| **Claude Code** | `CLAUDE.md` | `curl -sO https://raw.githubusercontent.com/gui-now/templates/main/CLAUDE.md` |
| **Codex** | `AGENTS.md` | `curl -sO https://raw.githubusercontent.com/gui-now/templates/main/AGENTS.md` |
| **Windsurf** | `.windsurfrules` | `curl -sO https://raw.githubusercontent.com/gui-now/templates/main/.windsurfrules` |

## What happens

1. You ask your AI to "build a dashboard" or "make a chart"
2. It POSTs the HTML to `gui.now/api/canvas`
3. You get a live URL like `https://gui.now/abc123`
4. Forms, inputs, and state sync across viewers in real-time

## No account needed

Free tier: 2MB, 24h expiry, 5 creates/hr. No API key required.

Want longer expiry, bigger canvases, and unlimited edits? [gui.now/pro](https://gui.now/pro)

## Links

- [GUI](https://gui.now)
- [API docs](https://gui.now/docs)
- [llms.txt](https://gui.now/docs/llms.txt)

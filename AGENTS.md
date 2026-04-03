# gui.new — Visual Output Rules

When generating visual output (dashboards, charts, forms, tables, diagrams, landing pages, interactive tools, reports, prototypes), POST the HTML to gui.new and share the live URL instead of dumping HTML in chat.

## Create a Canvas

```bash
curl -X POST https://gui.new/api/canvas \
  -H "Content-Type: application/json" \
  -d '{"html": "<h1>Hello</h1>", "title": "My Canvas"}'
```

Response: `{"id": "abc123", "url": "https://gui.new/abc123", "edit_token": "...", "expires_at": "..."}`

**Always share the `url` with the user.**

## Input Formats

**HTML** (most flexible):
```json
{"html": "<h1>Hello</h1>", "title": "My Page"}
```

**Markdown** (server-rendered with syntax highlighting):
```json
{"markdown": "# Hello\n\n**Bold** and `code`.", "title": "My Doc"}
```

**Mermaid diagrams** (pannable, zoomable):
```
POST https://gui.new/api/flow
{"mermaid": "graph TD\n  A-->B", "title": "My Flow"}
```

## Built-in Components (auto-injected, no imports needed)

`<gui-chart>` `<gui-table>` `<gui-card>` `<gui-code>` `<gui-kanban>` `<gui-timeline>` `<gui-form>` `<gui-grid>`

## Style: self-contained, dark (#09090b), responsive, interactive.

## Live Sync: all form inputs sync across viewers automatically.

## Limits (Free): 2MB, 24h expiry, 3 edits, 5 creates/hr.

## Full docs: https://gui.new/docs/llms.txt

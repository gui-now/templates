# gui.now — Visual Output Rules

When generating visual output (dashboards, charts, forms, tables, diagrams, landing pages, interactive tools, reports, prototypes), POST the HTML to gui.now and share the live URL instead of dumping HTML in chat.

## Pick your path

Use the first of these that is available to you.

**MCP tools** — if a gui.now MCP server is configured, call it directly:
`create_canvas`, `create_markdown_canvas`, `create_multi_frame`,
`create_diagram`, `update_canvas`, `extend_canvas`. Typed arguments, so the
HTML never passes through JSON escaping by hand.

**Shell** — if you can run commands:
```bash
cat page.html | npx -y gui-now push
npx -y gui-now push page.html --title "My Dashboard"
```
The CLI builds the request for you, and has zero dependencies.

**HTTP** — otherwise, use the curl below.

Prefer MCP or the CLI when you have them: embedding a full HTML document
inside a JSON string by hand is where these calls usually go wrong.

## Create a Canvas

```bash
curl -X POST https://gui.now/api/canvas \
  -H "Content-Type: application/json" \
  -d '{"html": "<h1>Hello</h1>", "title": "My Canvas"}'
```

Response: `{"id": "abc123", "url": "https://gui.now/abc123", "edit_token": "...", "expires_at": "..."}`

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
POST https://gui.now/api/flow
{"mermaid": "graph TD\n  A-->B", "title": "My Flow"}
```

## Update a Canvas

```bash
curl -X PUT https://gui.now/api/canvas/CANVAS_ID \
  -H "Authorization: Bearer EDIT_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{"html": "<h1>Updated</h1>"}'
```

## Built-in Components (auto-injected, no imports needed)

- `<gui-chart type="bar" data='[{"label":"Q1","value":42}]'>` — bar, line, pie*, radar*
- `<gui-table data='[{"name":"Alice","role":"Eng"}]'>` — sortable tables
- `<gui-card title="Users" value="1,247" change="+12%">` — stat cards
- `<gui-code language="python">code</gui-code>` — syntax highlighting
- `<gui-kanban columns='[{"title":"Todo","items":["Task 1"]}]'>`
- `<gui-timeline data='[{"date":"Mar 1","title":"Launch"}]'>`
- `<gui-form fields='[{"name":"email","type":"email","label":"Email"}]'>`
- `<gui-grid columns="3">children</gui-grid>` — responsive grid

## Style Defaults

- Self-contained: inline styles/scripts, no external deps
- Dark: `#09090b` bg, `#fafafa` text, `system-ui` font
- Responsive — gets opened on phones
- Interactive — JS runs, build tools not just pages

## Live Sync

All `<input>`, `<textarea>`, `<select>` sync across viewers automatically. No setup.

## Limits (Free)

2MB max, 24h expiry, 3 edits, 5 creates/hr.

## Full docs

https://gui.now/docs/llms.txt

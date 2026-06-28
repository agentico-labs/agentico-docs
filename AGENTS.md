# Documentation project instructions

## About this project

- This is the documentation site for **effy**, a multi-tenant agent manager built on the [eve](https://eve.dev) framework.
- It is built on [Mintlify](https://mintlify.com). Pages are MDX files with YAML frontmatter; configuration lives in `docs.json`.
- Source of truth for product behavior is the effy repo (`agent/`). Ground every technical claim in real code — do not invent flags, env vars, or tool names.
- For Mintlify product knowledge (components, configuration, writing standards), install the Mintlify skill: `npx skills add https://mintlify.com/docs`
- The Mintlify MCP server `https://mcp.mintlify.com` can edit content and settings; `https://www.mintlify.com/docs/mcp` answers questions about using Mintlify.

## Terminology

- Write **effy** in lowercase, including at the start of a sentence.
- Use **tenant**, **user**, and **scope** (the `(tenant, user)` pair) consistently — not "account" or "org".
- A **persona** is trusted configuration; **memory** is untrusted user data. Keep that distinction explicit when describing the prompt.
- The agent is built on **eve**; link to `https://eve.dev/docs` for framework details rather than re-documenting eve.

## Style preferences

- Use active voice and second person ("you").
- Keep sentences concise — one idea per sentence.
- Use sentence case for headings.
- Bold for UI elements: Click **Settings**.
- Code formatting for file names, commands, paths, and code references.
- Prefer Mermaid diagrams for flows and lifecycles over ASCII art.
- No marketing language, filler, or emoji.

## Content boundaries

- Memory, personas, and tools persist in **Supermemory** (`lib/supermemory.ts`), scoped per `(tenant, user)`. Memory is agentic — injected each turn from Supermemory's consolidated profile. Don't describe the stores as in-memory; document `SUPERMEMORY_API_KEY` as required.
- Do not document `EFFY_DEV_AUTH` as anything other than a local-only flag that must never run in production.

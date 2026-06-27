# effy docs

Documentation for [effy](https://github.com/agentico-labs/effy), a multi-tenant agent manager built on the [eve](https://eve.dev) framework. Built with [Mintlify](https://mintlify.com).

## Develop locally

Install the Mintlify CLI and run the dev server from the repo root (where `docs.json` lives):

```bash
npm i -g mint
mint dev
```

Preview at `http://localhost:3000`.

Useful checks before pushing:

```bash
mint broken-links   # validate internal links
mint validate       # validate docs.json and frontmatter
```

## Structure

```
docs.json            # site config and navigation
index.mdx            # introduction
quickstart.mdx
architecture.mdx     # lifecycle + sequence diagrams
concepts/            # multi-tenancy, personas, memory, custom-tools
guides/              # sdk, authentication, deployment
reference/           # tools, configuration
ai-tools.mdx         # how these docs are served as MCP + skill.md
```

## Publishing

Install the Mintlify GitHub app from your [dashboard](https://dashboard.mintlify.com/settings/organization/github-app). Changes deploy to production automatically on push to the default branch.

## Served for AI tools

Once deployed, Mintlify serves this site as an MCP server (`/mcp`), an agent skill (`/skill.md`), and `llms.txt` — no extra config. See [Use these docs in your agent](/ai-tools).

# mcpgate

> **Self-hosted MCP gateway with PII pseudonymization and two-layer policy hooks.** Connects Claude, ChatGPT, Codex, Gemini, and any MCP-compatible agent to 40+ enterprise tools — without sending your data through a vendor cloud.

[mcpgate.de](https://mcpgate.de) · [Docs](https://mcpgate.de/docs/) · [Live demo (no signup)](https://demo.mcpgate.de) · [Pricing](https://mcpgate.de/pricing/) · [Compare](https://mcpgate.de/compare/) · [Docker Hub](https://hub.docker.com/r/mcpgate/mcpgate)

[![License: BSL 1.1](https://img.shields.io/badge/License-BSL%201.1-blue.svg)](https://github.com/Mcpgate-de/mcpgate/blob/main/LICENSE) [![Docker](https://img.shields.io/badge/docker-mcpgate%2Fmcpgate-2496ED.svg?logo=docker)](https://hub.docker.com/r/mcpgate/mcpgate) [![Self-hosted](https://img.shields.io/badge/deployment-self--hosted-green.svg)](https://mcpgate.de/docs/quickstart/)

---

## What mcpgate does

One self-hosted MCP endpoint between your AI agents and your company tools. Claude opens a Jira ticket, drafts a Confluence page, posts to Slack — all routed through a gateway you operate, with central authentication, audit, and **PII pseudonymization that prevents real customer names from ever reaching the LLM provider**.

### The differentiators

| Feature | How it works |
|---|---|
| **PII pseudonymization with rehydration** | Sensitive fields (emails, names, phone numbers, customer IDs) are replaced with stable pseudonyms before the request reaches the LLM. Mapping stays on-prem, encrypted, 24h TTL. When the agent calls back into the source system, the real values are rehydrated — write-flows still work, the LLM never saw the originals. |
| **Two-layer policy hooks** | Company-wide hooks set by the operator (RBAC-style guardrails) plus per-user hooks each user defines from their own AI client. YAML, hot-reloaded in seconds, no code. |
| **40+ first-party integrations** | Jira, GitLab, GitHub, Notion, Confluence, Slack, Google Workspace, Microsoft 365, Power BI, Grafana, Sentry, Amplitude, Figma, Miro, BigQuery, Metabase, Jenkins, Transifex, Joan, Home Assistant, WordPress, App Store Connect, Google Play, AppFollow, Apple Ads, Apple Business, AWS (SES), Supernova, Google Ads, Google Analytics, Google Search Console, Google Tag Manager, Bing Webmaster, Sistrix, and more. Plus OpenAPI import for any REST API and YAML extension for any MCP server. |
| **Minimal data on your server** | Pass-through architecture. No tool payloads, messages or documents are stored. The gateway keeps an audit log (90 days, hashed identifiers) and the encrypted pseudonym mapping for rehydration (24h) — both on your own server. |
| **Action-level governance** | Dynamic action discovery shipped May 2026: `gateway_search_actions` + `gateway_activate` with risk-gated activation (low / medium / destructive). Actions can be flagged `default_active: false` for compliance allow-lists. |

## Where to start

- **Want to try it?** [Live demo](https://demo.mcpgate.de) — no signup.
- **Want to self-host?** [Two-minute quickstart](https://mcpgate.de/docs/quickstart/) — one Docker Compose command, zero config.
- **Want to compare?** [Fact-checked side-by-sides](https://mcpgate.de/compare/) against Obot, Docker MCP Gateway, IBM ContextForge, MintMCP.

## Repos

- **[mcpgate](https://github.com/Mcpgate-de/mcpgate)** — self-hosting distribution (Docker Compose, configs, hooks, ops docs). This is a mirror of [`gitlab.com/mcpgate/mcpgate`](https://gitlab.com/mcpgate/mcpgate) — issues there get the most attention.

## Built by

mcpgate is built and operated by the mcpgate team in Berlin. The product is licensed under BSL 1.1 (source-available; each release converts to Apache-2.0 four years after publication). Free in production for up to 5 users; a commercial license above.

Questions, bug reports, or comparison-page corrections welcome at [hello@mcpgate.de](mailto:hello@mcpgate.de).

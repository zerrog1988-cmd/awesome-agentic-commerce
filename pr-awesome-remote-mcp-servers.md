# Prepared PR — punkpeye/awesome-remote-mcp-servers

Status: READY TO FILE. Blocker: opening the PR needs a GitHub account; never from
Shawn's. Unblocker: house GitHub identity. Cost: free.

Why this repo and not punkpeye/awesome-mcp-servers (verified from that repo's
CONTRIBUTING.md, 2026-10-21): "This list is for servers with a public GitHub
repository — something you install and run yourself. If your server is remote-only
(just a hosted URL, no installable package), it belongs in
awesome-remote-mcp-servers instead." Our MCP is remote-only, so the remote list is
the correct shelf.

Format (verified from the remote list's README, 2026-10-21): entries are
`- [Name](site URL) \`mcp-endpoint-url\`` followed by a blank line and
`<auth marker> - Description.` Entries sit alphabetically inside a category.
Auth legend: 🔓 none / 🔑 API key / 🔐 OAuth. Ours is 🔓 — the handshake and
tools/list are open with no key; tools/call returns an x402 challenge.
Category: `### 💰 Finance`. Placement: alphabetically under "E" in Finance.
Note from the list: "Entries are only listed after the endpoint answers an MCP
initialize handshake" — ours does (streamable-http /mcp, verified in production).

## PR title
Add Erebian Detector APIs

## Entry (insert alphabetically in `### 💰 Finance`)
- [Erebian Detector APIs](https://erebian-frontdoor.verizence.workers.dev/site) `https://erebian-frontdoor.verizence.workers.dev/mcp`

  🔓 - Solana wallet audits and mint manipulation scans for agents; tool calls return an x402 payment challenge (USDC on Base) instead of free compute.

## PR body
Adds Erebian Detector APIs, a remote MCP server for Solana token/wallet diligence:
wallet_audit (a wallet's verified trading record, $0.05/call) and mint_scan
(manufactured-print manipulation check, $0.02/call). tools/list is open; tools/call
returns the x402 payment challenge — payment settles in USDC on Base via the REST
endpoints. No API key, no account.

## Domain-migration note
When erebian.eu.org activates, update both URLs to the permanent domain.

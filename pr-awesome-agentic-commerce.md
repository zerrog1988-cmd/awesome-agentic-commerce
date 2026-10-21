# Prepared PR — Merit-Systems/awesome-agentic-commerce

Status: READY TO FILE. Blocker: opening the PR needs a GitHub account; the only GitHub
connector available is Shawn's personal account, and PRs are never opened from it.
Unblocker: a house GitHub identity. Cost: free. No account needed to *read* the list.

Repo rules (verified from the repo README, 2026-10-21): "Add high-signal links to
resources powering the agent economy. Submit a PR with a concise description; group
items under existing sections when possible." Entry format: `- [Name](url) - description`.

## PR title
Add Erebian Detector APIs to Ecosystem

## Change (single line, appended at the end of the `## Ecosystem` section of README.md)
- [Erebian Detector APIs](https://erebian-frontdoor.verizence.workers.dev) - x402 APIs on Base (USDC) that sell measured Solana evidence to agents: wallet performance audits ($0.05), manufactured-print mint scans ($0.02), batch mint screens of up to 20 mints ($0.10), and first-minute launch tapes ($0.01), plus an MCP server whose tool calls return the x402 payment challenge.

## PR body
Adds Erebian Detector APIs to the Ecosystem section.

Erebian sells measured Solana evidence to agents over x402 (v1 + v2, USDC on Base,
PayAI facilitator): a wallet performance audit ($0.05/call), a manufactured-print
mint scan ($0.02/call), a batch mint screen ($0.10/call, up to 20 mints), and a
first-minute launch tape ($0.01/call). The same detectors are exposed over MCP at
https://erebian-frontdoor.verizence.workers.dev/mcp — tools/call returns the x402
challenge instead of free compute.

Machine surfaces: https://erebian-frontdoor.verizence.workers.dev/.well-known/agent-card.json ·
https://erebian-frontdoor.verizence.workers.dev/.well-known/x402 ·
https://erebian-frontdoor.verizence.workers.dev/openapi.json
Endpoints validated "Implementation Looks Correct" on Agentic.Market (2026-10-21).

## Domain-migration note
URLs use the workers.dev front door. When erebian.eu.org activates, edit the line's
URL to the permanent domain.

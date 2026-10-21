# Prepared PR — Haustorium12/gold-402, directory/mcp-servers.md (MCP Servers shelf)

Status: READY TO FILE. Blocker: opening the PR needs a GitHub account; never from
Shawn's. Unblocker: house GitHub identity. Cost: free.

Repo rules (verified from CONTRIBUTING.md + directory/mcp-servers.md, 2026-10-21):
same as the APIs shelf — PR title `Add [Name]`; entry
`[Name](url) — One factual sentence, starting uppercase, ending with a period.`;
entry at the bottom of the correct section; endpoints are probed for a live 402
(their MCP shelf probes the server; our tools/call returns the challenge).
Ours goes at the bottom of `## Crypto & DeFi Intelligence` (after the
Checkpoint402 MCP entry, before the section's closing `---`).

## PR title
Add Erebian Detector APIs MCP

## Entry
- [Erebian Detector APIs MCP](https://erebian-frontdoor.verizence.workers.dev/mcp) — Remote streamable-http MCP server exposing the Erebian wallet-audit and mint-scan detectors as tools, where tools/call returns the x402 payment challenge instead of free compute and calls settle in USDC on Base through the REST endpoints at $0.05 and $0.02 per call. Example tool call: wallet_audit {"wallet":"FqamE7xrahg7FEWoByrx1o8SeyHt44rpmE6ZQfT7zrve"}. ([Discovery](https://erebian-frontdoor.verizence.workers.dev/.well-known/x402)) ([OpenAPI](https://erebian-frontdoor.verizence.workers.dev/openapi.json))

## PR body
Example: POST https://erebian-frontdoor.verizence.workers.dev/mcp with a tools/call
for wallet_audit — the server answers with the x402 payment challenge (it returns
the challenge only; it never serves free compute).

Adds the Erebian MCP server to Crypto & DeFi Intelligence in directory/mcp-servers.md.
tools/list is open (wallet_audit, mint_scan); payment is x402 v1 + v2, USDC on Base,
PayAI facilitator, payTo 0x562e8ab844dd22363a2045c5efd7d9fe74c7f082.

## Domain-migration note
When erebian.eu.org activates, update the MCP URL + links to the permanent domain.

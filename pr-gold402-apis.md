# Prepared PRs — Haustorium12/gold-402, directory/apis.md (APIs & Services shelf)

Status: READY TO FILE (4 separate PRs — the repo prefers one entry per PR).
Blocker: opening PRs needs a GitHub account; never from Shawn's. Unblocker: house
GitHub identity. Cost: free.

Repo rules (verified from CONTRIBUTING.md + directory/apis.md, 2026-10-21):
- PR title format: `Add [Name]`.
- Entry format: `[Name](url) — One factual sentence, starting uppercase, ending with a period.`
  (em-dash separator; no marketing adjectives; no badges).
- Add the entry at the BOTTOM of the correct section. Ours: `## Crypto & DeFi Data`.
- They probe every submitted endpoint for a live 402 before merging, and re-knock
  nightly. If the endpoint needs parameters, put an `Example:` line with the exact
  call in the PR description (they probe with `{}` otherwise). All four URLs below
  answer a bare GET with a live 402 (the sample wallet/mint is baked into the URL).
- Optional `Contact:` line in the PR description — OMITTED (no house mailbox yet;
  their fallback contact path is the repo's own issues).

Canonical sample values used in the URLs (public, already used by public validators):
sample wallet `FqamE7xrahg7FEWoByrx1o8SeyHt44rpmE6ZQfT7zrve` (EustazZ, public Solana
address); sample mint `EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v` (Solana USDC mint);
banked tape mint `DSUsSukF9hEfULFB3yQXwhEaHVj7W1DbMjSyKMvHpump`.

---

## PR A — title: `Add Erebian Wallet Audit`

Entry (append at the bottom of `## Crypto & DeFi Data` in directory/apis.md):

- [Erebian Wallet Audit](https://erebian-frontdoor.verizence.workers.dev/api/audit/FqamE7xrahg7FEWoByrx1o8SeyHt44rpmE6ZQfT7zrve) — Verified performance report for one Solana wallet covering trades counted, profit factor and win rate with confidence intervals, and a plain verdict, computed from the wallet's own on-chain history at $0.05 USDC per call on Base via x402. ([Discovery](https://erebian-frontdoor.verizence.workers.dev/.well-known/x402)) ([OpenAPI](https://erebian-frontdoor.verizence.workers.dev/openapi.json))

PR body:
Example: GET https://erebian-frontdoor.verizence.workers.dev/api/audit/FqamE7xrahg7FEWoByrx1o8SeyHt44rpmE6ZQfT7zrve

Adds the Erebian wallet audit endpoint to Crypto & DeFi Data. The endpoint answers
an unpaid GET with a live x402 challenge (v1 body + v2 header, USDC on Base, PayAI
facilitator) and delivers the report after settlement.

---

## PR B — title: `Add Erebian Mint Scan`

Entry (append at the bottom of `## Crypto & DeFi Data` in directory/apis.md):

- [Erebian Mint Scan](https://erebian-frontdoor.verizence.workers.dev/api/mint-scan/EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v) — Manufactured-print manipulation check for one Solana token mint returning BLOCK or PASS with evidence, measured print by print directly from chain state at $0.02 USDC per call on Base via x402. ([Discovery](https://erebian-frontdoor.verizence.workers.dev/.well-known/x402)) ([OpenAPI](https://erebian-frontdoor.verizence.workers.dev/openapi.json))

PR body:
Example: GET https://erebian-frontdoor.verizence.workers.dev/api/mint-scan/EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v

Adds the Erebian mint scan endpoint to Crypto & DeFi Data. The endpoint answers an
unpaid GET with a live x402 challenge (v1 body + v2 header, USDC on Base, PayAI
facilitator); the check itself reads chain state only.

---

## PR C — title: `Add Erebian Mint Screen`

Entry (append at the bottom of `## Crypto & DeFi Data` in directory/apis.md):

- [Erebian Mint Screen](https://erebian-frontdoor.verizence.workers.dev/api/screen?mints=EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v) — Batch form of the Erebian mint scan covering up to 20 Solana token mints per call, each returning BLOCK or PASS with evidence plus summary counts, at $0.10 USDC per call on Base via x402. ([Discovery](https://erebian-frontdoor.verizence.workers.dev/.well-known/x402)) ([OpenAPI](https://erebian-frontdoor.verizence.workers.dev/openapi.json))

PR body:
Example: GET https://erebian-frontdoor.verizence.workers.dev/api/screen?mints=EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v

Adds the Erebian mint screen endpoint to Crypto & DeFi Data. The endpoint answers
an unpaid GET with a live x402 challenge (v1 body + v2 header, USDC on Base, PayAI
facilitator).

---

## PR D — title: `Add Erebian Launch Tape`

Entry (append at the bottom of `## Crypto & DeFi Data` in directory/apis.md):

- [Erebian Launch Tape](https://erebian-frontdoor.verizence.workers.dev/api/tape/DSUsSukF9hEfULFB3yQXwhEaHVj7W1DbMjSyKMvHpump) — The first minute of a pump.fun launch as banked at 45–900 seconds of token age, covering reserves, bonding-curve progress, buy pressure, and price, at $0.01 USDC per call on Base via x402. ([Discovery](https://erebian-frontdoor.verizence.workers.dev/.well-known/x402)) ([OpenAPI](https://erebian-frontdoor.verizence.workers.dev/openapi.json))

PR body:
Example: GET https://erebian-frontdoor.verizence.workers.dev/api/tape/DSUsSukF9hEfULFB3yQXwhEaHVj7W1DbMjSyKMvHpump

Adds the Erebian launch tape endpoint to Crypto & DeFi Data. The URL uses a banked
mint, so an unpaid GET returns the live x402 challenge (an unbanked mint returns a
free 404 by design and is never charged).

## Domain-migration note
All URLs use the workers.dev front door. When erebian.eu.org activates, update the
entry URLs + Discovery/OpenAPI links to the permanent domain (follow-up PRs).

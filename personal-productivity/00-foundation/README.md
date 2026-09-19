# Episode 0 — Foundation: a local AI that drives a browser

**Part shipped:** a model running on your own machine that can open a browser, read a page, click, type, and report back. No cloud account, no subscription.

**Reference build:** Windows 11, RTX 4070 Super 12 GB, 64 GB RAM. Smaller cards work, slower — see the build guide.

## Pinned versions
| Part | Version |
| --- | --- |
| LM Studio | 0.4.24 |
| Model | Qwen3.6-35B-A3B, Q4_K_M, context **32768** |
| Node.js | LTS (rehearsal version to be pinned in v1.0) |
| @playwright/mcp | **0.0.82** — do not use `@latest` |

## Build
1. **Install LM Studio** — lmstudio.ai → Download for Windows → defaults. *Test:* Discover tab lists models.
2. **Download and load the model** — search `qwen3.6-35b-a3b`, Q4_K_M (~20 GB). Before Load, set **Context Length = 32768**. *Test:* "Say hello" gets a reply.
3. **Install Node.js** — nodejs.org → LTS → defaults. *Test:* `node --version` prints a version.
4. **Wire Playwright into LM Studio** — right panel → Install → Edit mcp.json → paste [`mcp.json`](mcp.json), replacing `yourname` with your Windows user name. *Test:* `mcp/playwright` toggle appears with browser tools listed.
5. **First run** — new chat, playwright ON, send the example.com prompt from [`prompts.md`](prompts.md). *Test:* heading "Example Domain", link "Learn more".

Then run the two demos in [`prompts.md`](prompts.md).

## Files
- [`mcp.json`](mcp.json) — the only config this episode needs
- [`prompts.md`](prompts.md) — every prompt verbatim, with expected results and the known failure

## The build guide (PDF)
Every step with screenshots, hardware tiers, troubleshooting, and corrected notes after each stream: free at https://wattengineworks.com

*Built, not rented.*

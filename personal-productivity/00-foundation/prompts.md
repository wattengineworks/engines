# Episode 0 — prompts

Setup for every prompt: LM Studio, Qwen3.6-35B-A3B loaded at **32768** context, `mcp/playwright` ON, every other integration OFF, **new chat**, no system prompt. Send each prompt exactly as written.

## First run — example.com

    Open https://example.com and tell me the page heading and the text of the link on the page.

Expected: `browser_navigate` → `browser_snapshot` → heading "Example Domain", link "Learn more". Under 10 s of thinking on an RTX 4070 Super.

## Demo 1 — Cloudflare status

    Open https://www.cloudflarestatus.com and tell me whether Cloudflare has any active incidents or outages right now. If so, list them.

Expected: `browser_navigate` → `browser_snapshot` → active incidents by name and status, or "no active incidents". About 11 s of thinking.

## Demo 2 — Hacker News search

    Go to https://news.ycombinator.com, use the search box at the bottom of the page to search for "local LLM", and give me the titles of the top 3 results with their links.

Expected: navigate → snapshot → click → type → snapshot → three real titles with links. Longer than Demo 1; under a minute on the reference build.

## Known failure

At 16384 context, Demo 2 stops after `browser_snapshot` with no answer and LM Studio reports:

    request (20212 tokens) exceeds the available context size (16384 tokens)

Fix: context 32768 (see the build guide, Step 2).

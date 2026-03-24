---
name: pangolinfo-ai-serp
description: >
  Programmatic Google SERP + AI Overviews (including AI Mode multi-turn) via
  Pangolinfo APIs, with optional page screenshots. Use when you need structured
  results (JSON) for pipelines/agents. Requires PANGOLIN_TOKEN or
  PANGOLIN_EMAIL + PANGOLIN_PASSWORD.
homepage: https://www.pangolinfo.com
metadata:
  openclaw:
    emoji: "🔎"
    os: ["darwin", "linux"]
    requires:
      env: ["PANGOLIN_TOKEN"]
      notes: "Auth: set PANGOLIN_TOKEN (recommended) OR set PANGOLIN_EMAIL + PANGOLIN_PASSWORD"
---

# Pangolinfo AI SERP (Google SERP + AI Overviews)

Search Google programmatically via **Pangolinfo** APIs.
Extract **Google AI Overviews**, run **AI Mode** searches with **multi-turn follow-ups**, and optionally capture **screenshots**.

## Migration note (Amazon)

Amazon scraping is now a separate skill: **Pangolinfo Amazon Scraper**.

If you previously used Amazon features from the combined skill, install the new Amazon skill and switch your `--mode` usage accordingly.

## Prerequisites

- **Python 3.6+** (standard library only)
- A **Pangolinfo account**: https://www.pangolinfo.com
- Auth env vars (choose one):
  - `PANGOLIN_TOKEN` (recommended)
  - or `PANGOLIN_EMAIL` + `PANGOLIN_PASSWORD`

```bash
export PANGOLIN_TOKEN="..."
# or
export PANGOLIN_EMAIL="..."
export PANGOLIN_PASSWORD="..."
```

## Minimal examples

AI Mode search:

```bash
python3 scripts/pangolinfo.py --q "what is quantum computing" --mode ai-mode
```

Standard SERP + AI Overview extraction (+ optional screenshot):

```bash
python3 scripts/pangolinfo.py --q "openclaw" --mode serp --screenshot
```

Multi-turn dialogue (AI Mode follow-ups):

```bash
python3 scripts/pangolinfo.py --q "python web frameworks" --mode ai-mode \
  --follow-up "compare flask vs django" \
  --follow-up "which is better for beginners"
```

## Output

The script prints structured JSON to stdout.

Key output fields:
- `organic_results[]`
- `ai_overview[]` (only when returned)
- `screenshot` (only when requested and available)
- `task_id`, `success`

## Links

- Homepage: https://www.pangolinfo.com
- Legacy skill page (will redirect): https://clawhub.ai/tammy-hash/pangolinfo-scrape

## Deep-dive references

- [references/ai-mode-api.md](references/ai-mode-api.md)
- [references/ai-overview-serp-api.md](references/ai-overview-serp-api.md)
- [references/error-codes.md](references/error-codes.md)

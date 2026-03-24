# Pangolinfo OpenClaw Skills

<div align="center">

**Programmatic scraping + structured JSON for agent workflows.**  
[Website](https://www.pangolinfo.com/) • [Documentation](https://docs.pangolinfo.com/) • [Get API Key](https://tool.pangolinfo.com/)

</div>

---

## What’s inside

This repository contains two OpenClaw skills maintained by Pangolinfo:

1. **Pangolinfo AI SERP**
   - Path: `./pangolinfo-ai-serp`
   - Purpose: Google SERP + AI overviews, including multi-turn AI mode follow-ups
   - Output: structured JSON (optional screenshot URL)
   - Docs: [`pangolinfo-ai-serp/SKILL.md`](./pangolinfo-ai-serp/SKILL.md)

2. **Pangolinfo Amazon Scraper**
   - Path: `./pangolinfo-amazon-scraper`
   - Purpose: Amazon product / keyword / category / ranking scraping via multiple parsers
   - Output: structured JSON
   - Docs: [`pangolinfo-amazon-scraper/SKILL.md`](./pangolinfo-amazon-scraper/SKILL.md)

---

## Features

- Real-time data for pipelines and agents
- LLM-ready JSON outputs for OpenClaw workflows
- Automation-friendly CLI examples and references included
- Clear separation by use-case (SERP vs Amazon) for easier maintenance

> Note: availability and unblock performance depend on target site behavior and your Pangolinfo plan/credits.

---

## Authentication

Both skills use Pangolinfo APIs. Configure one of the following:

- Recommended: `PANGOLIN_TOKEN`
- Alternative: `PANGOLIN_EMAIL` + `PANGOLIN_PASSWORD`

```bash
export PANGOLIN_TOKEN="..."
# or
export PANGOLIN_EMAIL="you@example.com"
export PANGOLIN_PASSWORD="..."
```

---

## Quick usage

Each skill includes copy-paste examples in its `SKILL.md`.

AI SERP example:

```bash
python3 pangolinfo-ai-serp/scripts/pangolinfo.py \
  --q "openclaw" \
  --mode serp \
  --screenshot
```

Amazon example:

```bash
python3 pangolinfo-amazon-scraper/scripts/pangolinfo.py \
  --url "https://www.amazon.com/dp/B00EXAMPLE00" \
  --parser amzProductDetail
```

---

## Contributing

Issues and PRs are welcome. Please include reproducible inputs and expected output fields.

---

## License

MIT © Pangolinfo

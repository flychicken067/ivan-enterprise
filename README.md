**English** | [中文](README.zh-CN.md)

# ivan-enterprise

AI-powered weekly intelligence digest for enterprise leaders — filtered through the **三张账单 (Three Bills)** framework.

**Philosophy:** Follow operators, not consultants. Only people who make decisions, not people who comment on decisions.

## What You Get

A weekly memo delivered to Telegram with:
- 3 signals from operators (CEOs, founders, CTOs) filtered through 维护税/聚焦税/版权税
- 1 concrete action for the week
- 1 article candidate flagged for ivan-article pipeline

See [`examples/sample-digest.md`](examples/sample-digest.md) for a complete real output — 2026-W14 digest covering Satya Nadella's IT replacement announcement, Parker Conrad's SaaS consolidation thesis, and Anthropic's emotion vectors paper through the three-bills lens.

## Quick Start

```bash
git clone https://github.com/flychicken067/ivan-enterprise.git ~/.claude/skills/ivan-enterprise
cd ~/.claude/skills/ivan-enterprise/scripts && npm install
```

Then in Claude Code: `/ivan-enterprise` or say "帮我出企业简报"

## The Three Bills Framework

Every signal is filtered through one of three hidden business costs:

| Bill | Chinese | What it reveals |
|------|---------|-----------------|
| 🔧 Maintenance Tax | 维护税 | Cost of keeping old systems alive |
| 🎯 Focus Tax | 聚焦税 | Cost of attention fragmentation |
| ©️ Copyright/IP Tax | 版权税 | Hidden cost of content and data |

## Default Sources

**X/Twitter (Operators only, 11 accounts):**
Satya Nadella, Aaron Levie, Parker Conrad, Sam Altman, Jensen Huang, Dharmesh Shah, Jason Lemkin, Patrick Collison, Dario Amodei, Brian Chesky, Marc Benioff

**Podcasts (Operator-led, 3):**
How I Built This, Acquired, My First Million

**Primary Sources:**
Company engineering blogs, earnings calls, CEO letters — NOT McKinsey, NOT HBR, NOT Gartner

## Comparison to follow-builders

| | follow-builders | ivan-enterprise |
|--|----------------|-----------------|
| Philosophy | Follow builders, not influencers | Follow operators, not consultants |
| Audience | AI researchers & founders | Enterprise CEOs & operators |
| Output | Weekly AI digest | Weekly decision memo |
| Lens | What are builders making? | What do the three bills reveal? |
| Language | English | Chinese |

Part of the **ivan-\*** skill family. See also: [ivan-article](https://github.com/flychicken067/ivan-article), [ivan-finance](https://github.com/flychicken067/ivan-finance)

Inspired by [follow-builders](https://github.com/zarazhangrui/follow-builders) (MIT license) — the consume-side complement to ivan-article's produce side.

## License

MIT

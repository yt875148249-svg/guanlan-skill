<div align="center">

# 观澜 · guanlan.skill

> Read the current, not the surface — decoding a 30-minute state broadcast into checkable judgments.

[![License: CC BY-SA 4.0](https://img.shields.io/badge/docs-CC%20BY--SA%204.0-lightgrey.svg)](LICENSE)
[![Skill](https://img.shields.io/badge/format-SKILL.md-black.svg)](SKILL.md)

**An open methodology that turns a nightly official news broadcast into three things: which stage a policy is at, which sentence is a signal, and what to watch next.** No insider access. Only public text: who spoke, when, which word changed, and which sentence never appeared.

[中文](README.md) · [Example](#example) · [Install](#install) · [How it works](#how-it-works)

</div>

---

## Example

> **Source line**: a single broadcast carried 10 items; the first 6 were the same party document in different formats — explanatory note, full text, standalone booklet, study responses, a commentator piece, and a short editorial.

**Ordinary reading**: it is important, high-level.

**Guanlan reading**: a 30-minute program normally fits 15–20 stories. Giving six slots to one document is not "emphasis" — it is **the extreme form of a priority ordering**. The more formats a topic gets (document + booklet + commentary + editorial), the more audiences it needs to reach. One level down: the outline comes from the communiqué (skeleton), the detail from the decision text (operations), and the real motive from the *explanatory note* — **what the communiqué does not say is the increment.**

`Method 54 repetition · 58 ordering-as-allocation · 72 document-layer reading`

Every judgment in a report carries a method number. If it cannot be numbered, it is downgraded to an observation item.

---

## Install

Guanlan is pure Markdown: no dependencies, no network, no model API.

```bash
git clone https://github.com/<your-name>/guanlan-skill.git ~/.claude/skills/guanlan
```

Works with any agent that reads a `SKILL.md` directory (Claude Code / Hermes / Cursor). For a plain chat model, paste `prompts/daily.md` and append the transcript.

---

## How it works

```
transcript
  ├─ 1 · segment      count items, note ordering and format anomalies
  ├─ 2 · locate       level S0–S6 + one of 13 stage words
  ├─ 3 · scan         time / space / actor / tool / goal / constraint / finance / meta
  ├─ 4 · detect       6 signal classes + wording diff + method number
  └─ 5 · write        facts + judgment + cross-check table + watchlist
                        └─ watchlist → next day: confirmed or falsified → write back
```

**Step 5's loop is the whole point: a reading without verification is just commentary.**

| Layer | Contents |
|---|---|
| `SKILL.md` | the execution standard (~350 lines) |
| `references/01-methodology.md` | 79 methods, each operationalized |
| `references/02-signals.md` | 6 signal classes + 45 measured wording diffs |
| `references/03-levels-words.md` | levels, 13 stage words, controlled vocabulary |
| `references/04-chains.md` | 9 transmission chains + 18 strategic axes |
| `references/05-checklist.md` | 24 pre-publish checks + 8 data disciplines |
| `references/06-failure-log.md` | real misjudgments and the rules they produced |
| `examples/` | full input→output, plus counter-examples |

---

## What it does not do

- With only one day of text, it will not produce wording-diff conclusions — doing so would be fabrication
- "Nominal-layer delivery" (a consensus with no signed text, no list, no effective date) is never reported as delivered
- It outputs **probabilities and structure**, not facts, not insider knowledge
- It is a **text** method: useless for anything that never reached the page
- **No third-party blind test exists.** All quality evidence is internal prediction→verification loops, published including the failures

---

## License

Documentation and methodology: **CC BY-SA 4.0**. Code: **MIT**.

> All inputs are publicly broadcast texts. Output is analysis, not investment advice.

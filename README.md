# AgentGameLab Skills

> Agent skills we actually run every day, packaged as one installable Claude Code plugin.
> 我们每天在用的 Agent Skill，打包成一个可安装的 Claude Code plugin。

We're a small AI-native game studio. These skills aren't demos — they're the ones that survived contact with daily work: getting the model to understand what we meant, keeping the agent harness from rotting, and learning new domains fast enough to ship in them.

## Install

```
/plugin marketplace add AgentGameLab/skills
/plugin install agentgamelab-skills@agentgamelab
```

Or clone into your skills directory — every skill here is a plain `SKILL.md` folder, so any harness that reads the SKILL.md convention (Cursor / Cline / Codex CLI / your own loader) can use them without the plugin layer:

```
git clone https://github.com/AgentGameLab/skills.git
cp -r skills/skills/tuneup ~/.claude/skills/
```

## What's inside

| Skill | One line | Use it when |
|---|---|---|
| [**tuneup**](skills/tuneup/SKILL.md) | Turns a fuzzy request into a high-information-density prompt — triage → 4-quadrant forging → domain-expert lens → theory anchors | You keep rephrasing the same ask and the model keeps missing it |
| [**harness-evolve**](skills/harness-evolve/SKILL.md) | One pass: track frontier research → self-audit config → act within L1/L2/L3 risk tiers → append-only run log | Your agent's config only gets touched when it breaks |
| [**learn-coach**](skills/learn-coach/SKILL.md) | Upgrades "give the answer" into "teach until understood" — Feynman recall / Socratic questioning / scaffolding / productive failure | You want a mental model you keep, not an answer you forget |
| [**game-copy-polish**](skills/game-copy-polish/SKILL.md) | Game writing craft (narrative spine + 8 techniques + 4 genre standards) + mechanical AI-pattern scanner (`check_prose.py`) | Your game copy reads like AI wrote it — or you want to make sure it doesn't |

### tuneup

`/tuneup <task>` optimizes your input and immediately executes it, automatically adding the relevant expert perspective. `/tuneup <需求>` 优化后直接执行，交付任务结果。

The user who most needs it doesn't know the word "prompt" — they're just repeating themselves. tuneup notices that pattern and steps in. Triage routes every request (fast lane / main lane / ER lane); the main lane silently classifies by complexity × precision and forges a conversational, template, structured-XML, or Lisp-style prompt accordingly. Finance / legal / medical / irreversible-decision asks hard-trigger a domain-expert lens **plus** a mandatory safety boundary.

### harness-evolve

Turns your harness (config files, routing rules, memory layout, persona docs) from break-fix into scheduled review. Every candidate change — whether from new research or the self-audit — passes the same three tiers: **L1** safe files auto-ship, **L2** needs reversibility + scope minimization + positive expected value (core behavior files open a draft PR instead of pushing), **L3** (DB migrations, auth, CI/CD, deleting rules) is observe-only, never automatic.

### learn-coach

The biggest failure mode of LLM teaching is saying too much at once — any pedagogy gets crushed under an 800-word monologue. Every rule in this skill fights that instinct. Chinese-first with plain-language glosses for every term; ships with an eval set. Reverse exemption: lookup questions, production firefighting, or an explicit "just tell me" get a straight answer with no teaching loop.

### game-copy-polish

Two halves: **Part A** teaches the craft (McKee controlling idea, Greimas actants, Church FADT for game-story isomorphism, eight writing techniques, four genre × voice standards), **Part B** catches the symptoms (a 639-line pure-Python scanner that flags 翻案腔 pivots, AI jargon, punctuation density, nominalization, metaphor clusters, sentence-length uniformity, and more). Chinese-first; built for card games, roguelikes, and any game that ships flavor text.

## Notes

- Skills are markdown. Read them before you install them — that's the whole point of the format.
- `tuneup`, `learn-coach`, and `game-copy-polish` are written Chinese-first; `harness-evolve` is bilingual. All four work in English.
- `tuneup`, `harness-evolve`, and `learn-coach` were previously published as separate repos ([tuneup](https://github.com/AgentGameLab/tuneup) · [harness-evolve](https://github.com/AgentGameLab/harness-evolve) · [learn-coach](https://github.com/AgentGameLab/learn-coach)). Those stay up as redirects; this repo is now the canonical home.

## License

MIT © AgentGameLab

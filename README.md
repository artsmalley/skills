# Agent Skills — Art Smalley

Skills for AI agents covering Lean Thinking and Toyota Production System methods, by [Art Smalley](https://artoflean.com) — author of *Four Types of Problems*, *Understanding A3 Thinking*, *Creating Level Pull*, and *Toyota Kaizen Methods*. I learned these methods working at Toyota in Japan decades ago and have taught them ever since. These files teach them to your AI agent.

A skill file is standardized work for an AI: the method, the sequence, the key points, and the guardrails, written down so the agent follows the real practice instead of improvising a plausible-sounding version of it.

## Skills

| Skill | What it does |
|---|---|
| [tbp-coach](./skills/tbp-coach/SKILL.md) | Coaches you through **your own real problem** using the Toyota Business Practices 8-step method. One step at a time, leads with questions, never solves the problem for you. |
| [five-why-coach](./skills/five-why-coach/SKILL.md) | Coaches a 5 Why root cause analysis of **your own real problem** — one causal chain, one why at a time, with evidence and a verification method demanded at every link. |
| [fishbone-coach](./skills/fishbone-coach/SKILL.md) | Coaches a fishbone (Ishikawa) cause-and-effect analysis — structured hypothesis mapping across categories, not brainstorming, with branch-by-branch rigor and prioritization for verification. |

More are planned: a problem-solving partner (works the problem with you), an A3/problem report writer, and a critique skill for reviewing existing problem-solving work.

## Installation

<details>
<summary><strong>Claude Code</strong></summary>

```bash
claude plugin marketplace add artsmalley/skills
claude plugin install tbp-coach@artsmalley
```

Or from inside a session: `/plugin` → browse → install `tbp-coach`.

</details>

<details>
<summary><strong>Codex, Cursor, and other agents</strong></summary>

```bash
npx skills add artsmalley/skills
```

The installer asks which skills you want and which agents to install them on.

</details>

<details>
<summary><strong>Claude.ai and Claude Cowork</strong></summary>

Claude.ai loads skills at the account level, not from GitHub:

1. Download this repository (green **Code** button → Download ZIP) and unzip it.
2. Zip the single skill folder you want (e.g. `tbp-coach/` — the folder itself, containing `SKILL.md`).
3. In claude.ai: **Settings → Capabilities → Skills → Upload skill**, and upload that zip.

</details>

<details>
<summary><strong>Any AI chat (no install)</strong></summary>

Open the skill's `SKILL.md` file on GitHub, copy the whole text, paste it as the first message of a new chat, and add: "Act according to this skill. I have a real problem to work on."

Works in any capable AI chat — ChatGPT, Claude, Gemini, Copilot. No account setup, no install.

</details>

## How these skills behave

- **Method fidelity.** Steps are locked — the agent does not invent, rename, or reorder them.
- **Guardrails are part of the method.** The coach may analyze data you provide; it may not invent data, and it may not hand you the root cause or the countermeasure. That discipline is the method.
- **The real work happens away from the chat** — at the gemba, in interviews, in gathering facts. The skills send you there.

## Author

Art Smalley — [artoflean.com](https://artoflean.com). Questions and feedback: open an issue on this repository.

## License

[CC BY 4.0](./LICENSE.md) — free to use, share, and adapt, with credit to Art Smalley.

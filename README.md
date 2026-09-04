# Agent Skills — Art Smalley

Skills for AI agents covering Lean Thinking and Toyota Production System methods, by [Art Smalley](https://artoflean.com) — author of *Four Types of Problems*, *Understanding A3 Thinking*, *Creating Level Pull*, and *Toyota Kaizen Methods*. I learned these methods working at Toyota in Japan decades ago and have taught them ever since. These files teach them to your AI agent.

A skill file is standardized work for an AI: the method, the sequence, the key points, and the guardrails, written down so the agent follows the real practice instead of improvising a plausible-sounding version of it. Each skill is a single folder with a `SKILL.md` file, following the open [Agent Skills](https://agentskills.io/specification) standard that Claude, Codex, ChatGPT, Cursor, and others read. One folder, any agent.

## Skills

| Skill | What it does | Use it when |
|---|---|---|
| [tbp-coach](./skills/tbp-coach/SKILL.md) | Coaches you through **your own real problem** using the Toyota Business Practices 8-step method. One step at a time, leads with questions, never solves the problem for you. | You have a whole problem to work end to end — from clarifying it through countermeasures and standardization. |
| [five-why-coach](./skills/five-why-coach/SKILL.md) | Coaches a 5 Why root cause analysis — one causal chain, one why at a time, with evidence and a verification method demanded at every link. | You already have one suspected cause and need to drill it to its root. Depth first. |
| [fishbone-coach](./skills/fishbone-coach/SKILL.md) | Coaches a fishbone (Ishikawa) cause-and-effect analysis — structured hypothesis mapping across categories, not brainstorming, with branch-by-branch rigor and prioritization for verification. | Several plausible cause areas and no evidence yet pointing to one. Breadth first, then hand the winner to 5 Why. |

More are planned: a problem-solving partner (works the problem with you rather than coaching), an A3/problem report writer, a critique skill for reviewing existing problem-solving work, and skills for other TPS methods. Version history for every skill is in [CHANGELOG.md](./CHANGELOG.md).

## Where these skills run

The same `SKILL.md` works everywhere. What differs is how you load it.

| Surface | How it loads | Setup |
|---|---|---|
| Claude Code (CLI, VS Code, desktop app) | Plugin from this repo, or a folder in `~/.claude/skills/` | One command |
| Codex CLI, Codex IDE extension, ChatGPT desktop (Codex mode) | Folder in `~/.agents/skills/` | One command |
| Cursor, Copilot CLI, and other agents | Wherever that agent keeps skills | One command |
| claude.ai and Claude Cowork | Zip upload to your claude.ai account | Two minutes |
| ChatGPT (Chat and Work modes) | Zip upload to the Skills library | Two minutes |
| Any AI chat — Gemini, Copilot, anything | Paste the file as the first message | None |
| Custom GPTs, Gemini Gems, Copilot Studio agents, Microsoft Teams | Paste the file body into the agent's instructions | Ten minutes |
| Your own application (Claude API or any model API) | System prompt, or the Claude Skills API | Code |

Details for each below.

## Installation

<details>
<summary><strong>Claude Code</strong> — CLI, VS Code and JetBrains extensions, desktop app</summary>

Install as a plugin from this repository's marketplace:

```bash
claude plugin marketplace add artsmalley/skills
claude plugin install tbp-coach@artsmalley
claude plugin install five-why-coach@artsmalley
claude plugin install fishbone-coach@artsmalley
```

Or from inside a session: `/plugin` → browse the `artsmalley` marketplace → install.

Manual alternative: copy a skill folder into `~/.claude/skills/` (personal, all projects) or into `.claude/skills/` inside a repository (shared with everyone who clones it, and loaded by Claude Code cloud sessions).

Then just describe your problem, or say "TBP coach", "5 whys", or "fishbone" — the skill triggers on the description in its frontmatter. Claude Code also lists installed skills as slash commands: `/tbp-coach`, `/five-why-coach`, `/fishbone-coach`.

Note: Claude Code plugins and `~/.claude/skills/` serve Claude Code only. Cowork and claude.ai do not read that folder — see the claude.ai section.

</details>

<details>
<summary><strong>Codex, Cursor, Copilot CLI, and other agents</strong></summary>

```bash
npx skills add artsmalley/skills
```

The installer asks which skills you want and which agents to install them on, and puts the folders where each agent expects them.

Manual alternative for Codex: copy a skill folder into `~/.agents/skills/` (user-wide) or `.agents/skills/` in a repository. Invoke with `$tbp-coach` or list with `/skills`. (Older guides show `~/.codex/skills` — that path is retired.)

</details>

<details>
<summary><strong>claude.ai and Claude Cowork</strong></summary>

Claude.ai and Cowork share one skill shelf: your claude.ai account. They do not read local folders or GitHub.

1. Download this repository (green **Code** button → **Download ZIP**) and unzip it.
2. Zip the single skill folder you want — `tbp-coach/` itself, containing `SKILL.md`.
3. In claude.ai: **Settings → Capabilities → Skills → Upload skill**, and upload that zip. In the Claude desktop app, the same shelf is under **Customize** in the sidebar.

The skill is then available in every claude.ai chat and every Cowork session, and syncs at session start. Repeat for each skill you want.

</details>

<details>
<summary><strong>ChatGPT</strong> — Chat and Work modes</summary>

ChatGPT has its own Skills library, separate from Codex.

1. Zip the single skill folder (as above) and name the file `skill.zip`.
2. In ChatGPT: sidebar → **Skills** → upload.
3. Invoke with `@tbp-coach` in a chat.

ChatGPT validates and repackages the upload, and may ask for a display name and icon on the way in.

</details>

<details>
<summary><strong>Any AI chat, no install</strong></summary>

Open the skill's `SKILL.md` on GitHub, copy the whole text, paste it as the first message of a new chat, and add:

> Act according to this skill. I have a real problem to work on.

Works in any capable AI chat — Claude, ChatGPT, Gemini, Copilot, Grok, a local model. No account setup, no install. This is also the fastest way to try a skill before deciding whether to install it.

</details>

<details>
<summary><strong>Custom GPTs, Gemini Gems, Copilot Studio agents, Microsoft Teams</strong></summary>

Every agent builder has an instructions field. Paste the body of `SKILL.md` (everything below the frontmatter) into it, name the agent after the skill, and publish it to whoever should have it. The coaching behavior travels with the text.

Copilot Studio and Teams specifics, learned the hard way building these as Teams agents:

- **Plain text only in the Instructions field.** Markdown headings, emphasis, and em dashes corrupt in the Studio editor. Strip the `#` marks and use ALL-CAPS section labels instead — those survive.
- **Paste near-verbatim.** A compressed rewrite of the skill underperformed the full text on the same test problems. The length is doing work.
- **Publish to Teams** from Studio once the test pane behaves; each user then gets the coach as a chat in Teams, and the organization gets a coaching standard instead of whatever each person's prompt happens to say.

A Custom GPT or a Gem is the same idea with less friction: new GPT → paste into Instructions → save. Share the link.

</details>

<details>
<summary><strong>Your own application</strong> — Claude API or any model API</summary>

Two ways, depending on how portable you need to be.

**Any provider — use the skill as the system prompt.** Read `SKILL.md`, drop the frontmatter, and pass the body as the system prompt. Works with Claude, OpenAI, Gemini, Bedrock, Azure, local models. This is what my own coaching web apps do.

```python
from pathlib import Path
import anthropic

skill = Path("skills/tbp-coach/SKILL.md").read_text().split("---", 2)[2]
client = anthropic.Anthropic()

response = client.messages.create(
    model="claude-opus-5",
    max_tokens=16000,
    system=skill,
    messages=[{"role": "user", "content": "Our line stopped three times yesterday for the same jam."}],
)
print(response.content[0].text)
```

**Claude API — native Skills.** Upload the folder once; Claude loads it on demand inside a code-execution container, the same way claude.ai does.

```python
from anthropic.lib import files_from_dir
import anthropic

client = anthropic.Anthropic()

skill = client.skills.create(files=files_from_dir("skills/tbp-coach"))

response = client.beta.messages.create(
    model="claude-opus-5",
    max_tokens=16000,
    betas=["code-execution-2025-08-25"],
    container={"skills": [{"type": "custom", "skill_id": skill.id, "version": "latest"}]},
    tools=[{"type": "code_execution_20260521", "name": "code_execution"}],
    messages=[{"role": "user", "content": "Coach me through a problem using TBP."}],
)
```

Managed Agents and the Claude Agent SDK accept the same skill folders. See Anthropic's [Skills guide](https://platform.claude.com/docs/en/build-with-claude/skills-guide) for current details.

</details>

## How these skills behave

- **Method fidelity.** Steps are locked — the agent does not invent, rename, or reorder them.
- **Guardrails are part of the method.** The coach may analyze data you provide; it may not invent data, and it may not hand you the root cause or the countermeasure. That discipline is the method.
- **The real work happens away from the chat** — at the gemba, in interviews, in gathering facts. The skills send you there and expect you to come back with what you found.
- **Adaptive, not scripted.** The coach reads the learner's competence and confidence per step and adjusts tone, explanation depth, and step size. It never lowers the evidence standard.
- **Safety first on every go-and-see.** Containment and area safety before observation; on-machine work only by qualified people under site procedures.

## What is in this repository

```
skills/
  tbp-coach/        SKILL.md + LICENSE.md
  five-why-coach/   SKILL.md + LICENSE.md
  fishbone-coach/   SKILL.md + LICENSE.md
.claude-plugin/     marketplace manifest for Claude Code
.github/workflows/  validates every skill against the Agent Skills spec on each push
CHANGELOG.md        per-skill version history
```

Every skill passes the official `skills-ref` validator in CI, so a folder you copy out of here is spec-clean on any surface.

## Versioning

Conservative. Ordinary revisions increment by 0.01 (1.02 → 1.03). The major number moves only for a fundamental change in how a skill works, and rarely. The reasoning for each change is in [CHANGELOG.md](./CHANGELOG.md).

## Feedback

These are working tools, not finished ones. If a coach lets you skip a step, accepts a vague cause, or hands you an answer it should have made you find, that is a defect — open an issue with the transcript. Requests for other TPS methods are welcome too.

## Author

Art Smalley — [artoflean.com](https://artoflean.com). Questions and feedback: open an issue on this repository.

## License

[CC BY 4.0](./LICENSE.md) — free to use, share, and adapt, with credit to Art Smalley. Each skill folder carries its own copy so it travels standalone.

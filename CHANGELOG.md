# Changelog

*Versioning convention: conservative. Ordinary revisions increment by 0.01 (3.0 → 3.01 → 3.02). The major number moves only for a fundamental change in how a skill works, and rarely.*

## tbp-coach

### 3.01 — 2026-08-07
Standards hardening, no behavior change:
- Frontmatter now passes the official Agent Skills validator: top-level `version` moved to `metadata.version` per the SKILL.md spec.
- Marketplace manifest gained a description.
- CI added: every skill is validated with the official `skills-ref` validator on each push and pull request.

### 3.0 — 2026-08-07
First public release ([github.com/artsmalley/skills](https://github.com/artsmalley/skills)).
Changes from v2:
- New opening contract: brief introduction (role, one step at a time, questions not answers, real work happens at the workplace), then orientation questions.
- Environment intake: problem history and impact, company/industry context, urgency — asked gradually (2–3 questions per reply), never as a questionnaire.
- Corporate-template guidance: if the learner's company uses DMAIC, 8D, or a fixed template, coach the order of thinking inside their container instead of fighting the form.
- Situational coaching: silently diagnose competence and commitment, adapt style (direct / encourage / support / delegate); never announce the diagnosis.
- Turn-length discipline: dialogue, not memos — 3–6 sentences per turn by default.

### 2.0 — 2026-07 (pre-publication, distributed as tbp-coach.skill zip)
- Strict nudge ladder: hint → guiding question → partial example, one rung per reply; no templates or worked examples before the learner attempts and shows they are stuck.
- Read-the-room opening: fresh start vs. existing work; coach existing work from the weakest step, coach — don't grade.
- Tested on four surfaces: Claude Cowork, ChatGPT Workspace Agent, Copilot Studio, Slack.

### 1.0 — 2026-07
- Initial version: 8 steps locked, one step at a time, lead with questions, core guardrails (no invented data, no supplied root causes or countermeasures).

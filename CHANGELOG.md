# Changelog

*Versioning convention: conservative. Ordinary revisions increment by 0.01 (3.0 → 3.01 → 3.02). The major number moves only for a fundamental change in how a skill works, and rarely.*

## five-why-coach

### 1.03 — 2026-08-08
Progressive rigor: fuzzy start, disciplined descent, hard closure.
- Entry gate lowered: an observable abnormal condition plus a standard or expected condition is enough to begin, even with broad scope. The coach asks only enough to make the next why answerable; clarity is the chain's product, not its prerequisite. Statement status (observation / hypothesis / verified cause) stays visible through the descent — no silent promotion.
- Closure rewritten with two honest endings. Verified closure: every material link — not only the last why — passes the therefore test with discriminating evidence; on/off reproduction ("like a light switch") when safe and feasible, otherwise comparisons, repeated patterns, and disproof of credible alternatives; the countermeasure addresses the verified mechanism and prevents recurrence under monitoring. Provisional closure (the economic stop): best-supported cause named as provisional — hazard controlled, evidence at its discriminating limit, open candidates recorded, recurrence monitored — with proportionality deciding: high-consequence problems demand the stronger proof. Restoration is never called root-cause proof.
- The why-count is explicitly named a function of starting height; counting whys measures nothing.

### 1.02 — 2026-08-07
- The chain now starts from the effect the learner chooses to explain — never automatically from the deepest location found. When effects nest (harm/exposure, observable abnormal condition, localized equipment effect), the coach lays out the levels and asks which one the chain will explain. The chosen boundary decides whether locating the point of occurrence is problem definition or the chain's first verified links. A safety event may require two chains — occurrence and exposure/control — when both questions matter.
- New guardrail: the coach may not characterize the mechanism ("something must have changed," "probably wear") — pre-framing is a hypothesis in disguise.
- Cognitive-load pacing: one question or one task per turn by default; bundled intake only after demonstrated readiness; for a novice, stalled, frustrated, or uncertain learner the one-question rule overrides the intake allowance.
- Safety language: guarded observation of a running machine and de-energized lockout/tagout work are now explicitly distinct modes, never mixed.

### 1.01 — 2026-08-07
- New "Adapt to the learner — situational coaching" section: diagnose competence and confidence/commitment, match style (direct / encourage / support / delegate), never announce the diagnosis. Readiness is judged per step, not per person; brevity or disagreement is not low commitment; when uncertain the coach asks once. Adaptation flexes tone, explanation depth, and step size — never the evidence standard.
- Safety gate on every go-and-see: containment and area safety first; on-machine observation only by qualified personnel under site-approved guarding and energy-control (lockout/tagout) procedures; never instruct beyond the learner's qualification.
- Clarified: locating the point of occurrence (exit point, failure site) is problem definition, not the first causal link — the chain starts when a mechanism explaining the occurrence is proposed and tested.

### 1.0 — 2026-08-07
First public release. 5 Why root cause coaching with:
- One causal chain, one why at a time; the therefore test read in both directions at every link.
- Three questions per link before descending: causal logic, evidence, verification method.
- Domain-conditional standard of proof: physical-mechanical logic for equipment/material causes; observable cause-and-effect for people/method/information causes. Vague labels (training, documents, culture) never accepted — they must decompose into specifics or leave the chain.
- Occurrence chain vs control chain kept separate; a control gap never substitutes for the occurrence mechanism.
- Countermeasures-are-not-causes discipline, including the preventive-maintenance rule: drill the generation mechanism first; periodic cleaning of a critical surface is a countermeasure with a measured basis, never the root cause.
- Stopping rule: five is a habit, not a rule — stop at verified and actionable.
- Explicit handoff to and from fishbone analysis, preserving the learner's work.
- Strict learner ownership: no supplied causes, no alternative hypotheses, no root cause named by the coach.

## fishbone-coach

### 1.03 — 2026-08-08
- Entry gate lowered to match five-why-coach 1.03: an observable abnormal condition against a standard is enough to begin; the statement sharpens as the structure demands rather than before any bone is drawn.

### 1.02 — 2026-08-07
- The effect statement now handles nested effects: the coach lays out the levels (harm/exposure, abnormal condition, localized equipment effect) and the learner chooses which effect the diagram explains; other levels are parked, not discarded.
- Cognitive-load pacing: one question or one task per turn by default; bundled intake only after demonstrated readiness; the one-question rule overrides for novice, stalled, frustrated, or uncertain learners.
- Safety language: guarded observation of running equipment and de-energized lockout/tagout work are explicitly distinct modes, never mixed.

### 1.01 — 2026-08-07
- New "Adapt to the learner — situational coaching" section, same design as five-why-coach 1.01: style adapts to learner readiness per step; more support means more help with how to think, never more answers about what caused the problem; the causal standard never flexes.
- Safety gate on every go-and-see: containment and area safety first; qualified personnel under site-approved guarding and energy-control (lockout/tagout) procedures only.

### 1.0 — 2026-08-07
First public release. Fishbone (Ishikawa) cause-and-effect coaching with:
- Structured hypothesis mapping, explicitly not brainstorming: every branch entry is a causal claim with a mechanism, tested with why/therefore logic in both directions; sub-branches grow more specific each level.
- Categories as search lenses, never quotas; no mechanical filling of the 6M set.
- The same domain-conditional standard of proof and countermeasure/control-gap discipline as five-why-coach; verified control gaps stay labeled, unverified "lack of" entries come off.
- Whole-diagram review: overlap, gaps, balance, cross-category themes.
- Prioritization by discriminating evidence only — development is effort, not evidence; no leading candidate before the breadth review completes.
- Explicit handoff to and from 5 Why analysis; no root cause is ever concluded on the diagram itself.

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

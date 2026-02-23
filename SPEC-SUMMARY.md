# BG : Media Post-Coaching — Requirements Summary

**Assignment:** Build a Collaborative AI Workflow | **Module:** Design Prompt Workflows

---

## Lesson Objectives

| Objective | Status | How |
|---|---|---|
| Build a collaborative workflow where AI and human work together iteratively | **Met** | 8-step Skill-Powered Prompt workflow. AI proposes (story angles, structure beats, drafts, edits) and the author reacts, steers, and decides at every stage. 4 specialized skills handle the heavy lifting; human checkpoints gate every creative decision. |
| Design explicit checkpoints where you review and redirect | **Met** | 5 human gates across 7 steps. Every skill step (Media Analysis, Story Coaching, Draft & Multimedia, Editorial Coaching) includes a propose → react → refine loop. No step advances without author approval. |
| AI researches, drafts, and analyzes while you steer, review, and decide | **Met** | AI: analyzes media, proposes story angles, coaches structure using Amuse-Bouche framework, generates drafts with multimedia placement, edits for brevity. Human: selects angle, approves anchor/details/dismount/hook, reviews draft, accepts/rejects editorial suggestions. |
| Document the workflow SOP and save to registry | **Met** | 229-line Workflow Definition with refined steps, decision points, failure modes, context shopping list, and dependency map. Registered in Notion AI Building Blocks. Version-controlled on GitHub. |

---

## Deliverables

| # | Deliverable | File | Status |
|---|---|---|---|
| 1 | AI Building Block Spec | `outputs/bg-media-post-coaching-building-block-spec.md` (13.8 KB) — Execution pattern: Skill-Powered Prompt. 7 steps classified on autonomy spectrum (2 Human, 4 AI-Semi-Autonomous, 1 AI-Deterministic). 4 skill candidates fully specified with inputs, outputs, decision logic, and failure modes. Human gates mapped at every creative decision point. | **Complete** |
| 2 | Baseline Workflow Prompt + Skills | `outputs/bg-media-post-coaching-prompt.md` (6.5 KB) — 8-step coaching instructions with explicit checkpoint moments at every stage. `skills/SKILL.md` — master skill. 4 sub-skills: `media-analysis/`, `story-coaching/`, `draft-multimedia/`, `editorial-coaching/` — each with domain-specific coaching logic. | **Complete** |
| 3 | Test run output | `TEST-RUN-OUTPUT.md` — Steps 1–3 run on real media (screenshot of author's BPG Tech News briefing). 5 human checkpoints documented with what AI proposed, what the author changed, and why it mattered. Every checkpoint produced a substantive steering decision. | **Complete** |

---

## Review Criteria

| Criterion | Evidence |
|---|---|
| Execution pattern makes sense, human checkpoints placed where judgment matters | Skill-Powered Prompt — AI proposes, human decides. Checkpoints gate every creative call: story angle selection, anchor approval, essential detail review, dismount direction, hook selection, draft review, editorial acceptance. No creative decision is automated. |
| Checkpoint moments are explicit in the prompt | Each step in the baseline prompt includes explicit checkpoint language: "Does that feel right?", "What feels right? What feels off?", "Author accepts, rejects, or modifies each suggestion." Never advance without author confirmation. |
| Skills specific enough for AI to execute without ambiguity | 4 sub-skills with: media type detection logic, Amuse-Bouche framework steps, 5 hook types with selection criteria, multimedia-to-story-beat mapping rules, editorial principles with coaching rationale, word count targets, voice preservation rules. |
| Test run: used checkpoints to steer output, final result is usable | 5 of 5 checkpoints used. Author rewrote the title, rejected a generic anchor framing, added the origin story, killed a cliché, combined two dismount options, and tightened the hook language. Every gate produced a meaningful change — no rubber stamps. |

---

## Collaborative Workflow Fit

The assignment calls for workflows where **human judgment drives the quality of the final output**. Good candidates listed: meeting prep, competitive analysis, proposal drafting, research synthesis, **content creation**, strategic planning.

BG : Media Post-Coaching is **content creation** — a coaching workflow where the AI does media analysis, story structure coaching, drafting, and editorial tightening, while the author makes every creative decision. The Amuse-Bouche framework provides structure; the human checkpoints ensure the output sounds like the author, not the AI.

The test run demonstrated this concretely: the AI proposed clean, structurally sound options at every step, and the author's interventions added voice, specificity, emotional truth, and personal narrative that the AI could not have generated on its own.

---

## Bonus

| Bonus Item | Status | Evidence |
|---|---|---|
| Register building blocks in AI Operations Registry | **Done** | Skill registered in Notion AI Building Blocks database |
| Link back to workflow entry | **Done** | Workflow Definition cross-referenced in `Projects/workflow-definitions/bg-media-post-coaching.md` |
| Commit `.md` files to GitHub | **Done** | All artifacts at `github.com/bengio777/Substack-short-blog-post_skill` |

---

## File Inventory

| File | Location | Purpose |
|---|---|---|
| `outputs/bg-media-post-coaching-building-block-spec.md` | GitHub repo | Deliverable 1: AI Building Block Spec |
| `outputs/bg-media-post-coaching-prompt.md` | GitHub repo | Deliverable 2: Baseline Workflow Prompt |
| `outputs/bg-media-post-coaching-definition.md` | GitHub repo | Supporting: Workflow Definition / SOP |
| `skills/SKILL.md` | GitHub repo | Deliverable 2: Master skill |
| `skills/media-analysis/SKILL.md` | GitHub repo | Deliverable 2: Sub-skill 1 |
| `skills/story-coaching/SKILL.md` | GitHub repo | Deliverable 2: Sub-skill 2 |
| `skills/draft-multimedia/SKILL.md` | GitHub repo | Deliverable 2: Sub-skill 3 |
| `skills/editorial-coaching/SKILL.md` | GitHub repo | Deliverable 2: Sub-skill 4 |
| `TEST-RUN-OUTPUT.md` | GitHub repo | Deliverable 3: Test run output |

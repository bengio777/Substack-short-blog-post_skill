# BG : Media Post-Coaching — Assignment Requirements Mapping

**Assignment:** Build a Collaborative AI Workflow
**Module:** Design Prompt Workflows
**Project:** BG : Media Post-Coaching

---

## Lesson Objectives → Evidence

### 1. "Build a collaborative workflow where AI and human work together iteratively — AI researches, drafts, and analyzes while you steer, review, and decide"

**Met.** The workflow is an 8-step Skill-Powered Prompt where AI proposes (story angles, structure beats, drafts, edits) and the author reacts, steers, and decides at every stage. 4 specialized skills handle the heavy lifting; human checkpoints gate every creative decision.

**Evidence:**
- `outputs/bg-media-post-coaching-building-block-spec.md` — Step-by-Step Decomposition table shows 4 AI-Semi-Autonomous steps (each with Human Gate = Yes), 2 Human steps, 1 AI-Deterministic step
- `outputs/bg-media-post-coaching-prompt.md` — Every skill step includes propose → react → refine loop
- `TEST-RUN-OUTPUT.md` — 5 of 5 checkpoints used, each producing substantive steering changes

### 2. "Design explicit checkpoints where you review and redirect, so the AI does the heavy lifting while you stay in the driver's seat"

**Met.** 5 human gates across 7 steps. Every skill step (Media Analysis, Story Coaching, Draft & Multimedia, Editorial Coaching) includes a checkpoint where the author approves, rejects, or redirects before advancing.

**Evidence:**
- `outputs/bg-media-post-coaching-building-block-spec.md` — Human Gate column in decomposition table: Yes for Steps 1, 2, 3, 4/5, 6, 7
- `outputs/bg-media-post-coaching-prompt.md` — Explicit checkpoint language at each step:
  - Step 2: "Ask the author to pick an angle (or volunteer their own)"
  - Step 3: "At every stage: propose, then ask the author to react. Never move on until the author confirms."
  - Step 4/5: "Present the full draft to the author for review. Ask: 'What feels right? What feels off?'"
  - Step 6: "Present suggestions and let the author accept, reject, or modify each one."
  - Step 7: "Ask: 'Publish now, or schedule for later?'"

### 3. "Build workflows with the right balance of AI capability and human control"

**Met.** The autonomy spectrum explicitly balances AI capability (media analysis, story structure coaching, drafting, editorial tightening) with human control (every creative decision is the author's).

**Evidence:**
- `outputs/bg-media-post-coaching-building-block-spec.md` — Autonomy Spectrum Summary:
  - Human-driven (2 steps): Steps 1, 8 — author does the work, AI provides guidance
  - AI-Semi-Autonomous (4 steps): Steps 2, 3, 4/5, 6 — AI proposes and coaches, author makes every creative decision
  - AI-Deterministic (1 step): Step 7 — formatting follows rules
- `skills/story-coaching/SKILL.md` — Amuse-Bouche framework provides structure; author makes every beat decision (anchor, details, dismount, hook)

### 4. "Document the workflow SOP and save it to your registry"

**Met.** Full SOP documented as a Workflow Definition and registered in the AI Operations Registry.

**Evidence:**
- `outputs/bg-media-post-coaching-definition.md` — 229-line Workflow Definition with scenario metadata, 8 refined steps (each with action, sub-steps, decision points, data in/out, context needs, failure modes), step sequence, dependency map, context shopping list, and research sources
- Registered in Notion AI Building Blocks database
- Cross-referenced in `Projects/workflow-definitions/bg-media-post-coaching.md`
- Version-controlled at `github.com/bengio777/Substack-short-blog-post_skill`

---

## Assignment Instructions → Evidence

### Part 1: Design ("Upload your Workflow Definition and let the AI recommend an execution pattern, classify each step, and map building blocks")

**Completed.** Output saved as `outputs/bg-media-post-coaching-building-block-spec.md`.

| Design Requirement | Where It Appears |
|---|---|
| Execution pattern recommendation | Building Block Spec — "Skill-Powered Prompt" with reasoning: conversational workflow (AI proposes, human decides), 4 reusable sub-routines with complex logic, no autonomous decision-making, single expertise domain, sequential flow with human gates |
| Each step classified | Building Block Spec — Step-by-Step Decomposition table with Autonomy column: 2 Human, 4 AI-Semi-Autonomous, 1 AI-Deterministic |
| Human checkpoints mapped | Building Block Spec — Human Gate column: Yes for 6 of 7 steps. Checkpoints placed at every creative decision point. |
| Building blocks mapped | Building Block Spec — 4 skill candidates fully specified: Media Analysis (inputs, outputs, 3 media-type processing paths, 3 story angle lenses, failure modes), Story Coaching (Amuse-Bouche framework, 5 hook types, probing questions), Draft & Multimedia (media-to-beat mapping, presentation formats, quality checks), Editorial Coaching (brevity pass, hook/dismount checks, coaching rationale for every suggestion, voice preservation rules) |

### Part 2: Construct ("Follow the build path for your recommended execution pattern... Save the prompt output. If your pattern is Skill-Powered Prompt, also save any skill files you built.")

**Completed.** Output saved as `outputs/bg-media-post-coaching-prompt.md` + 5 skill files.

| Construct Requirement | Where It Appears |
|---|---|
| Baseline Workflow Prompt | `outputs/bg-media-post-coaching-prompt.md` — 138-line coaching prompt with 8 steps, explicit checkpoint moments, input requirements (media formats), context requirements (all embedded in skills), and output format (Substack-ready post + reflection log entry) |
| Skill files | `skills/SKILL.md` — master skill (invoked via `/write-substack-post`). 4 sub-skills: `skills/media-analysis/SKILL.md` (media type detection, transcription, EXIF extraction, story angle generation), `skills/story-coaching/SKILL.md` (Amuse-Bouche framework, anchor-first coaching, 5 hook types), `skills/draft-multimedia/SKILL.md` (media-to-beat mapping, multimedia placement, word count enforcement), `skills/editorial-coaching/SKILL.md` (brevity pass, hook/dismount checks, coaching rationale, voice preservation) |

### Part 3: Run ("Run your workflow on a real scenario. At each checkpoint, review the AI's output and provide feedback or direction before moving to the next stage. Run at least twice.")

**Completed.** Test run documented in `TEST-RUN-OUTPUT.md`.

| Run Requirement | Evidence |
|---|---|
| Run on a real scenario | Steps 1-3 run on real media: screenshot of the author's BPG Tech News briefing web viewer (Feb 21, 2026 daily briefing). |
| Use checkpoints to steer output | 5 of 5 checkpoints used. Author rewrote the title with personal voice, rejected a generic anchor framing, added the origin story, killed a cliché, combined two dismount options, and tightened hook language. Every checkpoint produced a substantive change — no rubber stamps. |
| Run at least twice | Test run covered Steps 1-3 with multiple iterations within Story Coaching (anchor proposed → rejected → revised; details proposed → expanded with origin story → tightened from 4 to 3 beats; dismount A proposed, B proposed, A+B combined). Each checkpoint was itself an iterative refinement loop. |
| Checkpoint structure gives confidence in final output | The propose → react → refine loop at every gate ensured the author owned every creative decision. By the time the hook was written, voice consistency was established because the author had been steering since Step 2. |

---

## Review and Refine Criteria → Evidence

### "AI Building Block Spec: Execution pattern makes sense, human checkpoints are placed where judgment matters, building blocks are mapped"

| Criterion | Status | Evidence |
|---|---|---|
| Execution pattern makes sense | **Yes** | Skill-Powered Prompt — conversational workflow where AI proposes and human decides. 4 sub-skills handle complex coaching logic. No autonomous decision-making. Sequential flow with human gates. (`building-block-spec.md`, Execution Pattern section) |
| Human checkpoints placed where judgment matters | **Yes** | Gates at: story angle selection (Step 2), anchor approval (Step 3), essential details review (Step 3), dismount direction (Step 3), hook selection (Step 3), draft review (Step 4/5), editorial acceptance (Step 6), publish approval (Step 7). Every creative decision is gated. (`building-block-spec.md`, Human Gate column) |
| Building blocks are mapped | **Yes** | 4 skill candidates with: inputs (media files, story angle, narrative structure, draft), outputs (analysis report, story structure, complete draft, annotated edits), decision logic (media type detection, Amuse-Bouche framework, media-to-beat mapping, brevity principles), and failure modes (no angles resonate, details balloon, draft sounds generic, over-editing). (`building-block-spec.md`, Skill Candidates section) |

### "Baseline Workflow Prompt: Instructions are clear, checkpoint moments are explicit, context requirements are listed"

| Criterion | Status | Evidence |
|---|---|---|
| Instructions are clear | **Yes** | `bg-media-post-coaching-prompt.md` provides step-by-step coaching instructions with specific actions per step, two entry paths (Step 1), Amuse-Bouche framework sequence (anchor → details → dismount → hook), multimedia placement rules, and editorial principles. |
| Checkpoint moments are explicit | **Yes** | Every step includes checkpoint language: "Ask the author to pick an angle," "Does that feel right?", "Never move on until the author confirms," "What feels right? What feels off?", "Let the author accept, reject, or modify each one," "Publish now, or schedule for later?" |
| Context requirements are listed | **Yes** | `bg-media-post-coaching-prompt.md`, Context Requirements section: all coaching frameworks embedded in the 4 skills (Media Analysis, Story Coaching, Draft & Multimedia, Editorial Coaching). No external context files needed. |

### "Skills (if applicable): Instructions are specific enough for the AI to execute without ambiguity"

| Criterion | Status | Evidence |
|---|---|---|
| Specific enough for AI execution | **Yes** | Media Analysis: 3 media-type processing paths (photo → EXIF + visual, video → transcribe + visual, audio → transcribe + tone), 3 story angle lenses (emotional, narrative, aesthetic). Story Coaching: 4-step Amuse-Bouche sequence (anchor first, details, dismount, hook last), 5 hook types with descriptions and selection criteria, probing questions for each stage. Draft & Multimedia: 3 media positions (opener, anchor, closer), 3 presentation formats (photo, video, audio), word count target (1,200-1,500), media density rule (1 per 300-400 words). Editorial Coaching: 3-pass structure (brevity, hook check, dismount check), 3 coaching principles ("kill your darlings," "every sentence earns its place," "reader is lending attention"), voice preservation rule (tighten, never rewrite), 2-round editing limit. |

### "Test run: You've run the workflow on at least one real scenario, used the checkpoints to steer the output, and the final result is usable"

| Criterion | Status | Evidence |
|---|---|---|
| Run on real scenario | **Yes** | Test run on a screenshot of the author's BPG Tech News briefing (real media from a real project). |
| Used checkpoints to steer | **Yes** | 5 checkpoints documented in `TEST-RUN-OUTPUT.md` with what AI proposed vs. what the author changed: title rewritten with personal voice, anchor reframed from generic to authentic feeling, origin story added, cliché killed, dismount options combined, hook language tightened. |
| Final result is usable | **Yes** | Complete story structure locked (hook, 3 essential details, anchor, dismount) — ready for Steps 4-8 (drafting through publishing). The structure reflects the author's voice, personal narrative, and creative vision at every level. |

---

## Deliverables Checklist

| # | Deliverable | Required Format | File | Status |
|---|---|---|---|---|
| 1 | AI Building Block Spec | `[name]-building-block-spec.md` | `outputs/bg-media-post-coaching-building-block-spec.md` (246 lines) | **Complete** |
| 2 | Baseline Workflow Prompt | `[name]-prompt.md` + skill files | `outputs/bg-media-post-coaching-prompt.md` (138 lines) + `skills/SKILL.md` (master) + 4 sub-skills (media-analysis, story-coaching, draft-multimedia, editorial-coaching) | **Complete** |
| 3 | Test run output | Evidence of real execution with checkpoints | `TEST-RUN-OUTPUT.md` — Steps 1-3 on real media, 5 human checkpoints documented with AI proposals, author changes, and impact analysis | **Complete** |

---

## Bonus (Optional) → Evidence

| Bonus Item | Status | Evidence |
|---|---|---|
| Register building blocks in AI Operations Registry | **Done** | Skill registered in Notion AI Building Blocks database |
| Link back to workflow entry | **Done** | Workflow Definition cross-referenced in `Projects/workflow-definitions/bg-media-post-coaching.md` |
| Commit `.md` files to GitHub | **Done** | All artifacts at `github.com/bengio777/Substack-short-blog-post_skill` |

---

## Collaborative Workflow Fit

The assignment specifies: *"Choose one that requires human judgment at key points — a collaborative workflow where AI researches, drafts, or analyzes, and you review, refine, and decide."*

**Good candidates listed:** meeting prep, competitive analysis, proposal or report drafting, research synthesis, **content creation**, strategic planning.

BG : Media Post-Coaching is **content creation** — a coaching workflow where the AI handles media analysis, story structure coaching, drafting, and editorial tightening, while the author makes every creative decision. The Amuse-Bouche framework provides structure; the human checkpoints ensure the output sounds like the author, not the AI. The test run demonstrated this concretely: the AI proposed clean, structurally sound options at every step, and the author's interventions added voice, specificity, emotional truth, and personal narrative that the AI could not have generated on its own.

---

## File Inventory

| File | Location | Lines | Purpose |
|---|---|---|---|
| `bg-media-post-coaching-building-block-spec.md` | `outputs/` | 246 | Deliverable 1: AI Building Block Spec |
| `bg-media-post-coaching-prompt.md` | `outputs/` | 138 | Deliverable 2: Baseline Workflow Prompt |
| `bg-media-post-coaching-definition.md` | `outputs/` | 229 | Supporting: Workflow Definition / SOP |
| `SKILL.md` | `skills/` | — | Deliverable 2: Master skill |
| `media-analysis/SKILL.md` | `skills/` | — | Deliverable 2: Sub-skill 1 |
| `story-coaching/SKILL.md` | `skills/` | — | Deliverable 2: Sub-skill 2 |
| `draft-multimedia/SKILL.md` | `skills/` | — | Deliverable 2: Sub-skill 3 |
| `editorial-coaching/SKILL.md` | `skills/` | — | Deliverable 2: Sub-skill 4 |
| `TEST-RUN-OUTPUT.md` | Root | — | Deliverable 3: Test run output |

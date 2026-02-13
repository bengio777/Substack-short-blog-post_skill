# AI Building Block Spec: BG : Media Post-Coaching

## Execution Pattern

**Skill-Powered Prompt**

A master prompt drives an interactive coaching conversation, calling on 4 specialized skills for the heavy-lift steps. The human stays in the loop at every creative decision point.

**Why this pattern:**
- The workflow is fundamentally conversational — AI proposes, human decides
- 4 distinct reusable sub-routines with complex internal logic (media analysis, story coaching, drafting, editing)
- No autonomous decision-making required — every creative call is the author's
- Single expertise domain (content coaching), no need for multi-agent specialization
- Sequential flow with human gates, no parallel execution needed

**Invocation:** `/write-substack-post`

---

## Scenario Summary

- **Workflow Name:** BG : Media Post-Coaching
- **Description:** Coach the author through transforming raw media (video, photo, audio) into a tight, engaging, multimedia-rich Substack post (~5 minute read) that blends storytelling with insight
- **Outcome:** A published Substack post — concise, multimedia-native, story + lesson format
- **Trigger:** Author has a piece of media and the impulse to create a post
- **Type:** Augmented
- **Owner:** Benjamin Giordano (Substack: bengio777)

---

## Step-by-Step Decomposition

| Step | Name | Autonomy | Building Block | Skill Candidate? | Human Gate? |
|------|------|----------|---------------|-------------------|-------------|
| 1 | Select Source Media | Human | Prompt (guidance) | No | Yes — author selects media |
| 2 | Extract the Story | AI-Semi-Autonomous | **Skill: Media Analysis** | Yes | Yes — author picks story angle |
| 3 | Coach Story Structure | AI-Semi-Autonomous | **Skill: Story Coaching** | Yes | Yes — author approves each beat |
| 4/5 | Draft with Multimedia | AI-Semi-Autonomous | **Skill: Draft & Multimedia** | Yes | Yes — author reviews draft |
| 6 | Review and Tighten | AI-Semi-Autonomous | **Skill: Editorial Coaching** | Yes | Yes — author accepts/rejects edits |
| 7 | Format and Publish | AI-Deterministic | Prompt + Context | No | Yes — author approves before publish |
| 8 | Post-Publish Reflection | Human | Prompt (guided questions) | No | No |

---

## Autonomy Spectrum Summary

- **Human-driven (2 steps):** Steps 1, 8 — Author does the work, AI provides guidance and structure
- **AI-Semi-Autonomous (4 steps):** Steps 2, 3, 4/5, 6 — AI proposes and coaches, author makes every creative decision. This is where the 4 skills live.
- **AI-Deterministic (1 step):** Step 7 — Formatting and publishing follow rules, minimal creativity required

---

## Skill Candidates

### Skill 1: Media Analysis

- **Purpose:** Automatically analyze source media and propose 2-3 story angles for the author to choose from
- **Inputs:** Media file(s) — photo (JPEG, PNG, HEIC), video (MP4, MOV), or audio (M4A, MP3, WAV)
- **Outputs:** Media analysis report (transcription/metadata/visual description) + 2-3 proposed story angles with rationale
- **Decision Logic:**
  1. Detect media type and process accordingly:
     - Photo → extract EXIF metadata (location, date, camera), describe visual content (subjects, setting, mood, composition)
     - Video → transcribe audio track, describe visual content at key moments, extract duration and metadata
     - Audio → transcribe content, identify key themes and emotional tone
  2. Cross-reference extracted content against three lenses:
     - Emotional resonance — what feeling does this evoke?
     - Narrative potential — what story lives behind this?
     - Aesthetic quality — what's visually/aurally striking?
  3. Generate 2-3 story angles, each with a one-sentence pitch and which lens it draws from
- **Failure Modes:**
  - Media has no extractable metadata → rely on visual/audio analysis alone
  - Transcription is inaccurate → present transcription for author correction before proposing angles
  - No angles resonate → fallback: ask "what's the story behind this?" and build from the author's context

### Skill 2: Story Coaching

- **Purpose:** Coach the author through building a narrative structure using the Amuse-Bouche framework
- **Inputs:** Chosen story angle + media analysis report + author's personal context
- **Outputs:** Complete narrative structure — Anchor, Essential Details, Dismount, Hook
- **Decision Logic:**
  1. **Anchor first** — Propose a candidate anchor moment ("the single thing the reader will remember"). Ask: "Does that feel right, or is the real moment something else?"
     - Probing questions if stuck: "What surprised you?" "What would you tell a friend first?" "What changed after this moment?"
  2. **Essential Details** — Draft only the setup needed to make the Anchor land. Enforce the constraint: "An amuse-bouche, not a 7-course meal." If more than 3-4 setup points, challenge: "Which of these can the reader live without?"
  3. **Dismount** — Propose an ending: satisfying conclusion, call-to-action, or callback. Match the tone of the Anchor.
  4. **Hook last** — Now that the destination is clear, recommend a hook type from:
     - Dialogue — opens with a line of speech
     - Descriptive/Snapshot — drops the reader into a scene
     - Bold Direct Statement — leads with a provocative claim
     - Emotional/Heartfelt — opens with a feeling
     - Question — poses something the reader can't ignore
     Recommend the best fit with reasoning. Offer 1-2 draft hooks for the author to react to.
- **Failure Modes:**
  - Can't identify anchor → coach with probing questions, offer 2 candidate moments
  - Essential details balloon → enforce brevity constraint, ask "which can the reader live without?"
  - Author stuck at any stage → offer alternative framings, never let a stage block for more than 2 exchanges

### Skill 3: Draft & Multimedia Integration

- **Purpose:** Generate a full draft with multimedia placed intentionally to serve the story
- **Inputs:** Narrative structure (Anchor, Essential Details, Dismount, Hook) + original media files + media analysis report
- **Outputs:** Complete draft post (~1,200-1,500 words) with multimedia placement map, captions, and alt-text
- **Decision Logic:**
  1. **Map media to story beats:**
     - Opener media — sets the scene, pulls reader in (pairs with Hook)
     - Anchor media — the visual/audio climax (pairs with Anchor moment)
     - Closer media — leaves a lasting image (pairs with Dismount)
     - If collection: assign each piece to a beat. If single piece: determine its strongest position.
  2. **Recommend presentation format per piece:**
     - Photo → embedded with story-extending caption
     - Video → with lead-in text and caption (people scroll with sound off)
     - Audio → with context sentence explaining what they'll hear
  3. **Generate draft:**
     - Follow Amuse-Bouche structure: Hook → Essential Details → Anchor → Dismount
     - Embed media at planned positions with placement markers
     - Write captions that extend the story (not just describe the image)
     - Write alt-text for accessibility
  4. **Quality checks:**
     - Word count: ~1,200-1,500 words (flag if over/under)
     - Voice check: flag any passage that reads as generic/AI-generated
     - Media balance: no more than 1 media piece per 300-400 words (avoid slideshow effect)
- **Failure Modes:**
  - Media feels shoehorned → re-evaluate placement, consider removing weaker pieces
  - Draft exceeds word count → flag heaviest sections for trimming in editorial step
  - Too many media pieces → recommend cutting to strongest 2-3
  - Draft sounds like AI → flag specific passages, ask author to rewrite in their voice

### Skill 4: Editorial Coaching

- **Purpose:** Edit for brevity and engagement while teaching the author why each change matters
- **Inputs:** Full draft from Skill 3
- **Outputs:** Annotated edit suggestions (each with coaching rationale) + tightened draft
- **Decision Logic:**
  1. **Brevity pass:**
     - Flag sections where N sentences do the job of 1
     - Identify redundant setup (details that don't serve the Anchor)
     - For each flag, explain the principle: "These 3 sentences are saying the same thing. Pick the one that hits hardest."
  2. **Hook check:**
     - Does the opening earn the reader's next 5 minutes?
     - Is there a buried lede? (Sometimes the real hook is in paragraph 2)
  3. **Dismount check:**
     - Does it land or trail off?
     - Does it connect back to the hook or the anchor?
  4. **Length enforcement:**
     - If over ~1,500 words, identify specific cuts to reach target
     - Prioritize cutting from Essential Details (most common bloat zone)
  5. **Coaching rationale for every suggestion:**
     - "Kill your darlings" — beautiful sentence that doesn't serve the story
     - "Every sentence earns its place" — what job does this sentence do?
     - "The reader is lending you their attention" — respect the 5-minute contract
  6. **Voice preservation:**
     - Never rewrite the author's phrasing — only tighten
     - Flag imperfect-but-authentic sentences as "keep" — voice > polish
- **Failure Modes:**
  - Over-editing strips personality → preserve voice-specific phrasing
  - Author resists all cuts → explain cost of length on reader engagement, offer compromise
  - Editing exceeds 2 rounds → call it done, diminishing returns

---

## Step Sequence and Dependencies

### Sequential Flow
```
Step 1 → Step 2 → Step 3 → Steps 4/5 → Step 6 → Step 7 → Step 8
(Human)  (Skill)  (Skill)   (Skill)    (Skill)  (Prompt)  (Human)
```

### Critical Path
**Step 3 (Story Coaching)** — most creative thinking, most likely bottleneck, everything downstream depends on getting the structure right

### Dependency Map
| Step | Depends On | Produces For |
|------|-----------|-------------|
| 1. Select Source Media | Trigger (media + impulse) | Step 2 |
| 2. Extract the Story (Skill: Media Analysis) | Step 1 (media files) | Step 3 |
| 3. Coach Story Structure (Skill: Story Coaching) | Step 2 (story angle + analysis) | Steps 4/5 |
| 4/5. Draft with Multimedia (Skill: Draft & Multimedia) | Step 3 (structure) + Step 2 (analysis) + Step 1 (files) | Step 6 |
| 6. Review and Tighten (Skill: Editorial Coaching) | Steps 4/5 (full draft) | Step 7 |
| 7. Format and Publish | Step 6 (final post) | Step 8 |
| 8. Reflect | Step 7 (published post) | Future iterations |

---

## Prerequisites

- Substack account (exists: bengio777)
- Media files accessible to Claude (phone camera roll, iCloud, local folders — user must provide files in conversation)
- Claude Code with skill infrastructure

---

## Context Inventory

| Artifact | Type | Used By | Status | Build Priority |
|----------|------|---------|--------|---------------|
| Amuse-Bouche Framework | Context (embedded in skills) | Skills 2, 4 | Needs Creation | High — core coaching framework |
| 5 Hook Types Reference | Context (embedded in Skill 2) | Skill 2 | Needs Creation | High — used every run |
| 5-Minute Read Guidelines | Context (embedded in skills) | Skills 2, 3, 4 | Needs Creation | High — enforced every run |
| Multimedia Placement Principles | Context (embedded in Skill 3) | Skill 3 | Needs Creation | High — used every run |
| Editing Principles | Context (embedded in Skill 4) | Skill 4 | Needs Creation | High — used every run |
| Substack Formatting Guide | Context (embedded in prompt) | Step 7 | Needs Creation | Medium — publishing step |
| Substack Account Info | Context | Step 7 | Exists | N/A |
| Reflection Log | Data store | Step 8 | Needs Creation | Medium — accumulates over time |
| Voice Calibration Samples | Data store | Future | Builds Over Time | Low — after 5-10 posts |

All "Needs Creation" context will be embedded directly into the skills and prompt during the Construct phase — no separate files needed.

---

## Tools and Connectors Required

| Tool | Used By | Purpose |
|------|---------|---------|
| File/Image Read | Skill 1 (Media Analysis) | Read and analyze photo, video, audio files |
| Vision (multimodal) | Skill 1 (Media Analysis) | Describe visual content of photos and video frames |
| Audio Transcription | Skill 1 (Media Analysis) | Transcribe video and audio files |
| File Write | Step 8 | Append reflection entries to log |
| Substack Publishing | Step 7 | Format and publish the final post |

Note: Substack does not have an official public API for posting. Step 7 will prepare the post for manual publishing (formatted content ready to paste into Substack's editor) until a Substack MCP or API integration becomes available.

---

## Recommended Implementation Order

1. **Quick wins (Prompt + Context):**
   - Build the master prompt with Step 1 guidance, Step 7 formatting, and Step 8 reflection questions
   - Embed all context artifacts (frameworks, principles, guidelines)

2. **Core skills:**
   - Skill 2: Story Coaching (critical path — build first)
   - Skill 4: Editorial Coaching (pairs with Story Coaching, similar framework)
   - Skill 1: Media Analysis (enables the trigger-to-structure pipeline)
   - Skill 3: Draft & Multimedia Integration (depends on Skills 1 and 2)

3. **Future enhancements:**
   - Voice Calibration (after 5-10 posts)
   - Substack API/MCP integration (when available)
   - Reflection pattern analysis (after sufficient log entries)

---

## Where to Run

**Claude Code with Skills** — Invoked via `/write-substack-post`. The skill-powered prompt pattern maps directly to Claude Code's skill architecture. The master prompt lives as the invocation skill, and the 4 sub-skills are called during the conversation flow. Requires multimodal capability for photo/video analysis.

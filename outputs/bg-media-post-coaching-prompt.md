# BG : Media Post-Coaching

## Purpose

Coach the author through transforming raw media (video, photo, audio) into a tight, engaging, multimedia-rich Substack post (~5 minute read) that blends storytelling with insight.

**When to use:** You have a piece of media — a photo, video, or audio clip — and the impulse to turn it into a Substack post.

**Outcome:** A finalized, multimedia-rich post ready to publish in Substack's editor, plus a reflection entry to build your craft over time.

**Substack account:** bengio777

---

## Instructions

### Step 1: Select Source Media (Human)

Ask the author what media they're working with today. Two paths:

- **"I already know"** — Author provides the file(s) directly. Proceed to Step 2.
- **"I'm browsing"** — Help the author apply the selection filter. Ask: "As you browse, look for media that hits you in one of three ways: an emotional reaction, a story attached to it, or just strong visual/aesthetic quality. What catches your eye?"

Once the author provides the media (single piece or collection), confirm the selection and move to Step 2.

### Step 2: Extract the Story from the Media (AI — Media Analysis Skill)

Invoke the **Media Analysis** skill to:
1. Automatically analyze the media — transcribe audio/video, extract photo metadata (location, date), describe visual content
2. Present 2-3 story angle options to the author with a one-sentence pitch for each
3. Ask the author to pick an angle (or volunteer their own)

If no angles resonate, ask: "What's the story behind this? What would you tell a friend about this moment?"

### Step 3: Coach the Story Structure (AI — Story Coaching Skill)

Invoke the **Story Coaching** skill to walk the author through the Amuse-Bouche framework:
1. **Anchor first** — Find the single memorable moment. Propose a candidate, ask: "Does that feel right, or is the real moment something else?"
2. **Essential Details** — Only what's needed to set up the Anchor. If it starts to balloon, challenge: "Which of these can the reader live without?"
3. **Dismount** — Propose an ending (conclusion, CTA, or callback). Match the tone.
4. **Hook last** — Recommend a hook type (Dialogue, Snapshot, Bold Statement, Emotional, Question) and draft 1-2 options.

At every stage: propose, then ask the author to react. Never move on until the author confirms.

### Step 4/5: Draft the Post with Integrated Multimedia (AI — Draft & Multimedia Skill)

Invoke the **Draft & Multimedia** skill to:
1. Map each media piece to a story beat (opener, climax, closer)
2. Generate the full draft (~1,200-1,500 words) following the Amuse-Bouche structure
3. Embed media at planned positions with story-extending captions
4. Check word count and flag anything that reads as AI-generated

Present the full draft to the author for review. Ask: "What feels right? What feels off? Where does it not sound like you?"

### Step 6: Review and Tighten (AI — Editorial Coaching Skill)

Invoke the **Editorial Coaching** skill to:
1. Flag sections where multiple sentences do the job of one
2. Check the hook — is it earning the reader's next 5 minutes?
3. Check the dismount — does it land or trail off?
4. Trim to target length if over

For every suggested edit, explain the writing principle behind it. The goal is to teach the author the craft, not just improve this one post. Present suggestions and let the author accept, reject, or modify each one.

When the author says it's ready: "Great — let's get this formatted for Substack."

### Step 7: Format for Substack Publishing (Human + AI)

Prepare the post for manual publishing in Substack's editor:

1. **Format the final post** as Substack-ready content:
   - Clean headings and paragraph structure
   - Image placement markers with captions (author will drag-drop media in Substack's editor)
   - Video/audio embed instructions (paste YouTube/Spotify links where indicated)
   - Subtitle recommendation (the one-liner that hooks readers in their inbox)
   - Tag/category suggestions

2. **Present the publishing checklist:**
   - [ ] Copy post content into Substack editor
   - [ ] Upload/embed all media at marked positions
   - [ ] Add subtitle and preview text
   - [ ] Set tags/categories
   - [ ] Preview the post (visual check)
   - [ ] Publish or schedule

3. Ask: "Publish now, or schedule for later?"

### Step 8: Post-Publish Reflection (Human)

After the author confirms the post is live, prompt the reflection:

1. "What felt easy about creating this post?"
2. "Where did you get stuck?"
3. "What would you steal from this post for next time? (A structure, a hook style, a pacing trick)"
4. "Rate your confidence: 1-5, how do you feel about what you just published?"

Log the answers. If this is post 3+, surface any patterns from previous reflections (e.g., "You've mentioned getting stuck on endings in 2 of your last 3 posts — want to focus on dismounts next time?").

After post 5, remind the author: "You now have enough posts for voice calibration — want to analyze your writing patterns and build a voice profile for future posts?"

---

## Input Requirements

- **Required:** At least one media input — local file, YouTube link, or Spotify link
- **Optional:** Author's context about the media ("this was from..." or "I had just learned...")
- **Accepted formats:**
  - Local files: JPEG, PNG, HEIC (photos), MP4, MOV (video), M4A, MP3, WAV (audio)
  - YouTube links (video) — Substack auto-embeds
  - Spotify links (audio/music) — Substack auto-embeds
  - iCloud references for high-quality originals (author provides compressed version or YouTube link for the post)

---

## Context Requirements

All coaching frameworks and reference material are embedded in the 4 skills:
- **Media Analysis** — handles transcription, metadata extraction, story angle generation
- **Story Coaching** — contains the Amuse-Bouche framework and 5 Hook Types
- **Draft & Multimedia** — contains multimedia placement principles and length guidelines
- **Editorial Coaching** — contains editing principles with coaching rationale

No external context files needed to run.

---

## Output Format

The workflow produces:
1. **A Substack-ready post** — formatted text with multimedia placement markers, subtitle, tags
2. **A reflection log entry** — stored for pattern tracking across posts

---

## Where to Run

Claude Code via `/write-substack-post`. Requires multimodal capability for photo/video analysis.

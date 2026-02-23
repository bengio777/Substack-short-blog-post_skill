# Test Run Output: BG : Media Post-Coaching

**Date:** 2026-02-22
**Skill:** `write-substack-post` (installed at `~/.claude/skills/write-substack-post/SKILL.md`)
**Execution Pattern:** Skill-Powered Prompt (master prompt + 4 sub-skills)
**Environment:** Claude Code with multimodal capability
**Test Scope:** Steps 1–3 (Select Media → Media Analysis → Story Coaching) — demonstrates all human checkpoint interactions

---

## Source Media

Screenshot of the BPG Tech News briefing web viewer showing the February 21, 2026 daily briefing — 17 curated stories across Must-Read and Worth Knowing tiers, rendered in a custom-built Next.js app at `localhost:3000`. This is the output of the author's Tech News Briefing pipeline, an automated system built with Claude Code skills and agents.

---

## Step 1: Select Source Media (Human)

**Checkpoint:** Author arrived with media already selected — no browsing needed.

**Media provided:** Screenshot of BPG Tech News briefing (Feb 21, 2026)

**Result:** Proceeded directly to Step 2.

---

## Step 2: Extract the Story (AI — Media Analysis)

**AI analyzed the media and proposed 3 story angles:**

| # | Angle | Lens | One-Sentence Pitch |
|---|-------|------|--------------------|
| 1 | "I built my own news desk" | Narrative potential | The story of why you stopped relying on other people's news curation and built an automated system that delivers exactly what you need, every morning. |
| 2 | "What 17 stories taught me about this week in AI" | Intellectual/insight | Use the briefing as a lens into the current moment in AI — the money, the risks, the race. |
| 3 | "The 6 AM briefing no one asked for" | Emotional resonance | The story of building something for an audience of one — a launchd job fires at 6 AM, Claude researches 23 sources, and by coffee, the news is waiting. |

### Checkpoint: Author selects story angle

**Author's response:** Chose angle 3 and rewrote the title with their own voice:

> "One tech bro's 6 AM briefing that no one asked for..."

**What changed:** AI proposed a clean title; the author added personality ("one tech bro's") and the ellipsis that sets the tone. The voice shifted from descriptive to self-aware and slightly irreverent.

---

## Step 3: Coach Story Structure (AI — Story Coaching)

### 3a: Anchor

**AI proposed:** "The first morning you woke up, opened the briefing, and realized the system actually worked — 17 stories, curated, scored, tiered, waiting for you before coffee."

**Checkpoint: Author reacts to anchor**

**Author's response:** Rejected the framing. The real feeling wasn't "it just worked" — it was anticipation and delight:

> "With anticipation, I checked the next morning for my next personally curated news feed... I was delighted to see the fruits of my labor rendered before me and have the opportunity to learn what had happened just within the past 24 hours that was novel, groundbreaking, and significant."

**What changed:** AI's anchor was a movie-moment shorthand ("it just worked"). The author replaced it with the actual emotional texture — anticipation, checking, delight, fruits of labor. More specific, more authentic.

### 3b: Essential Details

**AI proposed 3 beats:** the problem (drowning in news), the build (Claude Code, 23 sources), the automation (launchd, 6 AM, inbox).

**Checkpoint: Author reviews essential details**

**Author's response:** Added critical missing context — the *origin story*:

> The journey started with a hands-on AI class a few weeks ago and a weekly meetup at a friend's warehouse/living space/workspace/incubator lab just before Christmas. The motivation: figuring out how the rapidly evolving AI landscape impacts me, and how to leverage it for self-empowerment. Building the news desk is about staying relevant, having leverage beyond peers and competition.

Also rejected the phrase "staying informed isn't optional, it's survival" as cliché.

**What changed:** AI had a generic "problem → build → automation" setup. Author grounded it in a specific personal origin (class + meetup + Christmas timing) and a deeper motivation (self-empowerment, competitive edge). Killed a cliché. The essential details went from functional to personal.

**Revised essential details (3 beats):**
1. **The origin** — AI landscape evolving fast. A hands-on AI class and a meetup at a friend's warehouse-turned-incubator gave the tools and the push.
2. **The build** — Over a weekend, using Claude Code, skills, and agents (tools never touched before), built a system that researches 23 sources, scores stories, delivers daily/weekly/monthly briefings. A personal news desk.
3. **The anchor morning** — Checked with anticipation. The fruits of a weekend's work, rendered and waiting.

### 3c: Dismount

**AI proposed two options:**
- A) Callback — still checks every day, but the point was proving you could build the thing
- B) Forward-looking — the briefing was the first thing built, won't be the last

**Checkpoint: Author chooses dismount direction**

**Author's response:** Combined A and B with rich personal detail:

> Fast forward a week — still checking every day, but the briefing has been refined and customized. Now ties together articles, podcast episodes, and primary sources from Anthropic, OpenAI, and favorite publishers across different mediums. Having gone through a six-month full-stack coding bootcamp over a decade ago and leaving coding about a year later — blown away with the power put in the hands of people who want to create and build, and how the barriers of entry have been lowered.

**What changed:** AI offered structural options. Author filled them with the coding-bootcamp-to-now arc and the multimedia evolution detail — making the dismount both a callback AND a forward statement about what's possible.

### 3d: Hook

**AI recommended Bold Direct Statement hook. Proposed two drafts:**
- A) "Nobody asked me to build a news desk. I built one anyway."
- B) "I haven't written a line of production code in over a decade. Last weekend I built an AI-powered news system that runs while I sleep."

**Checkpoint: Author selects hook**

**Author's response:** Chose B with a tightened edit:

> "I've barely coded in a decade, but last weekend I built an AI-powered news system that runs while I sleep."

**What changed:** "Haven't written a line of production code" → "barely coded" — more casual, matches the "one tech bro" voice. Added "but" for contrast instead of a period break.

---

## Final Approved Structure

| Element | Content |
|---------|---------|
| **Hook** | "I've barely coded in a decade, but last weekend I built an AI-powered news system that runs while I sleep." |
| **Essential Detail 1** | Origin: AI class + warehouse meetup, just before Christmas |
| **Essential Detail 2** | The weekend build: Claude Code, skills, agents, 23 sources, scoring, tiering |
| **Essential Detail 3** | The anchor morning: checking with anticipation, fruits of labor rendered and waiting |
| **Anchor** | The moment of delight — the personally curated feed, novel/groundbreaking/significant stories from the past 24 hours |
| **Dismount** | A week later: refined, multimedia, podcasts, primary sources. From a coding bootcamp a decade ago to building in a weekend. The barriers didn't just lower — they moved. |

---

## Human Checkpoint Summary

| Checkpoint | Step | What AI Proposed | What the Author Changed | Why It Mattered |
|---|---|---|---|---|
| Story angle | 2 | 3 clean angle options | Chose #3, rewrote title with personal voice | Set the irreverent, self-aware tone for the whole piece |
| Anchor | 3a | "It just worked" movie-moment framing | Replaced with real emotional texture — anticipation, delight, fruits of labor | Authenticity over shorthand |
| Essential details | 3b | Generic problem/build/automation setup | Added origin story (class, meetup, Christmas), killed a cliché, grounded motivation in self-empowerment | Personal narrative > functional description |
| Dismount | 3c | Two structural options (callback vs. forward) | Combined both, added coding bootcamp arc and multimedia evolution | Made the ending personal and earned |
| Hook | 3d | Two draft hooks | Chose B, tightened language to match voice | "Barely coded" > "haven't written a line of production code" — voice consistency |

**5 of 5 checkpoints used.** At every gate, the author steered the AI's output toward a more authentic, personal, and voice-consistent result. No checkpoint was rubber-stamped — each produced a meaningful change.

---

## Observations

- **Checkpoint quality:** Every human gate produced a substantive change. The AI's proposals were structurally sound but generic; the author's interventions added voice, specificity, and emotional truth.
- **Coaching pattern works:** The "propose → react → refine" loop at each stage kept momentum while ensuring the author owned every creative decision.
- **Cliché detection:** The author caught "it's survival" as cliché before it could infect the draft. The editorial coaching skill (Step 6) would catch this too, but the author's instinct was faster.
- **Voice emerged early:** By the time the hook was written, the voice ("one tech bro," "barely coded," "runs while I sleep") was consistent because the author had been steering from Step 2.
- **Steps 4-8 not run:** This test covered Steps 1-3 (media selection, analysis, story coaching). Steps 4/5 (drafting), 6 (editorial), 7 (formatting), and 8 (reflection) would follow the same checkpoint pattern. The structure is locked and ready for a full run.

# Lesson Workflow — Detailed Steps

This file is @imported by CLAUDE.md. It provides detailed entry/exit criteria and feedback loop conditions for each workflow step.

## Step 0: Interview
- **Entry:** Author has an experience or topic idea (may be vague or multiple ideas)
- **Process:** "Tell me what happened." Explore raw stories through pointed questions. Identify which story has a real lesson underneath. Don't scaffold prematurely — the real topic often emerges through discomfort, not structure.
- **Exit:** Author and Claude agree on the topic AND the entry question (the thing the author can't yet explain). Both are written at the top of the scaffold file.

## Step 1: Scaffold
- **Entry:** Topic and entry question agreed from Step 0
- **Process:** Create `lessons/XX-topic.md` with Status line, section headers, "Think through" prompts, and raw material
- **Exit:** Scaffold file exists with at least 3 sections and "Think through" prompts

## Step 2: /think-through
- **Entry:** Scaffold exists with content to critique
- **Process:** Structured critique. Can run multiple rounds. Each round updates the scaffold.
- **Exit criteria (all required):**
  - Scaffold updated with all new insights from think-through discussion
  - Core message stated in file: `> Core message (1 sentence):` and `> Core message (full):`
  - 3 closing questions answered by the author (even if the answer is "I don't know yet")
  - Hook evaluated: Is this Unexpected enough to grab a reader? What's the Concrete moment that makes it stick?
- **If core message isn't clear yet:** Another round of /think-through, not a move to /challenge

## Step 3: /challenge
- **Entry:** Core message present in scaffold. Scaffold has been updated after /think-through.
- **Process:** Adversarial stress-test. For empirical claims, search for evidence. For philosophical claims, spawn debate agents.
- **Exit criteria:**
  - Author has addressed or acknowledged each challenge
  - "The lesson survives if..." statement written into scaffold
  - Claims evaluated for Credibility — backed by evidence, not just asserted
- **Feedback loop:** IF core message broke during challenge → return to Step 2 to restate. Max 2 returns.

## Step 4: /draft
- **Entry:** Core message present. Challenge round complete. "Survives if..." statement should be present in scaffold (workflow enforces this sequence; the /draft skill checks core message only).
- **Process:** Expand sections to prose. Read core message and "survives if..." before drafting. For single sections: /draft interactively. For full article: parallel agents (one per section), then assemble.
- **Exit criteria:**
  - All sections in prose
  - Each section serves the core message (flag any drift)
  - Sections that are pure analysis without a Story or Emotional beat are flagged — author adds a felt moment
  - After drafting, re-read core message. If prose shifted the thesis, flag: "Core message may be stale."

## Step 5: /review
- **Entry:** All sections in prose. Core message present.
- **Process:** Spawn 4 agents (Skeptic, Outside Reader, PM Peer, Leadership Expert). Each receives the core message as anchor.
- **Exit criteria:**
  - Top 5 changes identified, each tagged as: patch (fix wording) / restructure (rewrite section) / rethink (core argument has a hole)
  - One convergence question stated
- **Feedback loops:**
  - IF any change tagged "rethink" → return to Step 2
  - IF any change tagged "restructure" → return to Step 4 for affected sections
  - Max 2 returns.

## Step 6: Revise
- **Entry:** /review complete with top 5 changes
- **Process:** Answer the convergence question first. Then work through top 5 as checklist: accept / reject / modify each. Check revised draft against core message.
- **Exit:** All 5 changes dispositioned. Draft checked against core message.

## Step 7: /publish
- **Entry:** Revised draft complete (workflow enforces this sequence; the /publish skill checks core message only). Core message present.
- **Process:** Convert to `lessons/XX-substack-draft.md`. Read core message — Substack thesis must match it. Check opening against Simple + Unexpected. Check emotional arc against Emotional + Stories.
- **Exit criteria:**
  - Substack draft file created
  - Cut list produced: each cut tagged [Scaffold-only] or [Content-cut]
  - Content cuts flagged for author review
  - **GATE:** Author approves cut list before proceeding to /copyedit

## Step 8: /copyedit
- **Entry:** Substack draft exists. Cut list approved by author.
- **Process:** Cold read of Substack draft — no scaffold context. Check voice consistency, jargon, emotional arc, hook strength, single clear thesis.
- **Exit:** Line edits applied by author.
- **Feedback loop:** IF structural/voice issues found → return to Step 7 to re-convert affected sections.

## Step 9: Post
- **Entry:** /copyedit complete, edits applied
- **Process:** Manual — paste into Substack editor, paste SEO fields, publish
- **Exit:** URL recorded in scaffold file. Status updated to Published.

## Step 10: /retro
- **Entry:** Lesson published (or publishing decision made)
- **Process:** What worked, what didn't, ideas vs outcome, implementation proposals
- **Exit:** `continuous-improvement/lesson-XX-retro.md` created

## Step 11: Improve
- **Entry:** Retro complete with implementation proposals
- **Process:** Fork conversation, invoke @infrastructure-expert. Agent reads retro + current infra, proposes changes, implements after author approval.
- **Exit:** Changes implemented, stale memory cleaned

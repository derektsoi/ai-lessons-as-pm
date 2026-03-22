# Next Session Prompt — Skill Evals via /skill-creator

Copy-paste this into a new Claude Code session in the `ai-lessons-as-pm` repo.

---

## Prompt

Use /skill-creator to evaluate and iterate on all 6 skills in `.claude/skills/`. These skills were recently updated with new behaviors (core message BLOCKED status, SUCCESS framework criteria, debate agents, 4-agent review panel, cut lists, and a brand new /copyedit skill). They need proper eval.

### Context

Read these files first for context on what changed:
- `continuous-improvement/task.md` — what was implemented
- `.claude/skills/evals/evals.json` — 6 eval cases with 29 assertions (draft — refine as needed)
- `.claude/skills/evals/iteration-1/` — evals 2 and 3 already passed (challenge BLOCKED, copyedit cold read)

### What to do

For each of the 6 skills, use /skill-creator's eval loop:

1. **Review the existing test cases** in `evals/evals.json`. Refine if needed — the skill-creator may suggest better test prompts.

2. **Run each eval** — spawn agents with the skill to execute the test prompt on `lessons/05-the-infrastructure-gap.md` (for scaffold-stage skills) or `lessons/05-substack-draft.md` (for /copyedit).

3. **Grade against assertions** — use the skill-creator's grading flow. Key assertions to verify:
   - Core message BLOCKED status works (challenge, draft, review, publish)
   - SUCCESS criteria evaluated (think-through: Unexpected+Concrete, draft: Emotional+Story, publish: Simple+Unexpected, challenge: Credible)
   - Phase 2 debate agents spawn in /challenge
   - 4 agents appear in /review (including Leadership Expert)
   - Cut list with [Scaffold-only] and [Content-cut] tags in /publish
   - /copyedit produces line edits + SEO fields without referencing scaffold

4. **Use the eval viewer** to review results qualitatively.

5. **If any skill fails:** iterate using /skill-creator's improvement loop (edit skill → re-run → re-grade).

6. **After all pass:** run /skill-creator's description optimization on each skill to improve triggering accuracy.

### Priority order

Start with the highest-risk skills (most changes):
1. /challenge (BLOCKED + Credible + Phase 2 debate agents — 3 new behaviors)
2. /review (BLOCKED + 4 agents + core message anchoring + change tagging)
3. /publish (BLOCKED + SUCCESS voice check + cut list + gate)
4. /copyedit (entirely new skill)
5. /draft (BLOCKED + SUCCESS emotional check + stale core message detection)
6. /think-through (SUCCESS hook check + core message output)

### Done when

- All 6 skills pass their eval assertions
- Descriptions optimized for triggering accuracy
- Results saved to `.claude/skills/evals/iteration-N/`

# CLAUDE.md — Continuous Improvement

This file loads on-demand when Claude reads files in `continuous-improvement/` (not at session startup). It guides the process of improving the lesson-writing infrastructure (CLAUDE.md, skills, hooks, rules, memory).

## When This Happens

The author forks the conversation at the end of a lesson session. The prior context (what worked, what didn't) is available. The goal is to turn observations into infrastructure changes.

## The CI Workflow

```
1. Retro — What worked, what didn't, ideas vs outcome
   Input: conversation context from the lesson session
   Output: continuous-improvement/lesson-XX-retro.md

2. Plan — Propose specific changes with expected outcomes
   Input: retro findings
   Process:
     a. Draft changes (exact files, exact content)
     b. Cross-check proposals against each other (dependencies, overlaps, conflicts)
     c. Have infrastructure-expert agent verify against official Claude Code docs
     d. Author reviews and approves
   Output: continuous-improvement/task.md

3. Execute — Implement changes in phased sessions
   Input: task.md
   Process:
     a. Phase 1: foundation changes (CLAUDE.md, shared conventions)
     b. Phase 2+: independent changes (can parallelize as separate agents)
     c. Each session: implement → unit test → functional test → pass/fail
     d. No phase proceeds until prior phase verified
   Output: committed changes to repo

4. Verify — System-level integration tests
   Input: all changes implemented
   Process: contradiction check across all files, behavioral walkthrough
   Output: test results recorded

5. Eval — Run skill evals on modified skills
   Input: evals/evals.json
   Process: spawn agents to execute skills, grade against assertions
   Output: eval results in evals/iteration-N/
```

## Key Principles (Learned from Lesson 05 CI)

### Right mechanism for each change
- **CLAUDE.md** — universal rules, workflow sequence, conventions. Loaded every conversation. Keep under 250 lines; use `@` imports for detail.
- **Skills** — invokable tools with specific prompts. Each skill owns its own behavior. Skills auto-load when their description matches the user's request (unless `disable-model-invocation: true`). They don't require manual `/skill-name` invocation.
- **Rules** (`.claude/rules/`) — path-scoped guidance. Use `paths:` frontmatter to scope. Only load when touching matching files.
- **Agents** (`.claude/agents/`) — reusable experts. Loaded at session start; Claude delegates automatically based on the description field. You can also invoke explicitly with `@agent-name`.
- **Memory** — cross-conversation context. Not rules. Remove stale entries after implementing the changes they requested.

### Skills flag, they don't gate
Skills are prompt instructions. They cannot enforce behavior. When a skill needs a prerequisite (e.g., core message present), it outputs a status flag (`BLOCKED`). Real enforcement is the CLAUDE.md workflow + author discipline.

### Verify against official docs before implementing
Claude Code evolves. Before proposing changes to CLAUDE.md, skills, hooks, or rules, verify against official documentation. Use WebSearch to check https://docs.anthropic.com/en/docs/claude-code. Do not rely on cached knowledge.

### What auto-loads and what doesn't

**At session start (always loaded):**
- Root `CLAUDE.md` and `.claude/CLAUDE.md`
- `.claude/rules/*.md` without `paths:` frontmatter
- Memory `MEMORY.md` (first 200 lines)
- `.claude/agents/*.md` (agent metadata — Claude delegates based on description)
- `.claude/skills/*/SKILL.md` metadata (name + description only, not the full body)

**On-demand (loaded when relevant):**
- Subdirectory CLAUDE.md files (when Claude reads files in those dirs)
- Path-scoped `.claude/rules/*.md` (when touching files matching `paths:` frontmatter)
- Skill bodies (when triggered by description match or `/skill-name` invocation)

**Not auto-loaded (requires explicit mechanism):**
- Arbitrary `.md` files you create in `.claude/` (e.g., `.claude/lesson-workflow.md`). These are NOT agents, rules, or skills — they're just files. To load them at startup, use `@` import syntax in a CLAUDE.md file: `@.claude/lesson-workflow.md` (path relative to the CLAUDE.md containing the import). Regular markdown links do NOT cause auto-loading.

### Scope hierarchy for CLAUDE.md files
CLAUDE.md files above the working directory load in full at session start. Subdirectory CLAUDE.md files load on-demand when Claude reads files in those subdirectories. When multiple exist, more specific locations take precedence.

### Test at two levels
- **Unit tests** (per change): grep-based checks that verify text exists in files. Fast, deterministic.
- **Functional tests** (per skill): spawn an agent that executes the skill and grades output against assertions. Slower, but tests real behavior.
- **E2E tests** (system level): contradiction checks, workflow walkthroughs. Run after all changes.

Paper walkthroughs (agent reads docs and reproduces the sequence) prove docs are consistent. They do NOT prove Claude follows the workflow in practice. Real behavioral tests happen during actual lesson work.

### Parallel execution model
Independent changes can run as separate agents simultaneously. Requirements:
- Explicit file ownership (no two agents edit the same file)
- Each agent runs its own unit tests before reporting done
- All parallel agents must pass before the next phase starts

## Retro Template

```markdown
# Lesson XX Retrospective — Process Review

> Date: YYYY-MM-DD
> Lesson: "Title"

## What Worked
[Specific techniques/moments that produced breakthroughs]

## What Didn't Work
[Where process stalled, repeated, or produced waste]

## Ideas vs. Final Outcome
| Original Idea | What Happened |
|---------------|---------------|

## Changes Needed
[Specific changes with expected outcomes and verification criteria]

## Execution Order
[Phased sessions with dependencies and file ownership]
```

## Task Template

Each change in task.md must have:
- **File:** exact path to edit
- **What:** specific content to add/change
- **Expected outcome:** observable behavior after the change
- **Unit verification:** grep-based tests with pass criteria
- **Functional verification:** skill execution test with parseable pass criteria

## Common Mistakes to Avoid

- **Don't propose changes without expected outcomes.** Every change must state what success looks like and how to verify it.
- **Don't test with paper walkthroughs and call it behavioral validation.** An agent reading docs and reproducing the sequence proves consistency, not compliance.
- **Don't create new files when editing existing ones works.** Prefer consolidation over proliferation.
- **Don't add process overhead disproportionate to value.** A PM writing weekly lessons doesn't need a 57-point test suite every time. Scale verification to the risk of the change.
- **Don't assume `.claude/` files auto-load.** Verify with official docs.
- **Don't skip the official docs verification step.** The platform changes. What worked last month may not work now.

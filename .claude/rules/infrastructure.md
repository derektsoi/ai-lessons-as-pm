---
paths:
  - ".claude/**"
  - "continuous-improvement/**"
---

# Infrastructure Rules

These rules load only when editing Claude Code infrastructure files or continuous improvement documents.

## Skill file requirements
- Every skill must have: `name`, `description`, `disable-model-invocation: false`, `argument-hint`
- If the skill reads the lesson file, it must locate the `> Core message (1 sentence):` line and output `Core message: [present/missing]` and `Status: [READY/BLOCKED]`
- If core message is missing, skill outputs BLOCKED status and does not proceed to main analysis

## Consistency checks
- After editing any skill, verify it doesn't contradict CLAUDE.md workflow sequence
- After editing CLAUDE.md, verify referenced skills actually exist as files
- Core message convention must be consistent across all files that reference it

## Memory management
- After implementing improvements, check if any memory entries are now redundant
- Remove stale index entries from MEMORY.md (keep archived files for history)
- Memory files that say "add X to CLAUDE.md" should be removed once X has been added

# Conventions

Standards and schema definitions for all prompts in this repository.
Prompts that deviate from these conventions should document why in their metadata header.

---

## Prompt Metadata Schema

Every prompt file must open with the following header block as a comment:

    # prompt_id:       {category}-{descriptor}
    # version:         {Major}.{Minor}.{Patch}
    # status:          draft | stable | deprecated
    # author:          {handle}
    # created:         YYYY-MM-DD
    # last_modified:   YYYY-MM-DD
    # changelog:
    #   {version} ({date}) - {description}

---

## Versioning Rules

Follows semantic versioning (Major.Minor.Patch):

| Bump  | When |
|-------|------|
| Patch | Typo fixes, clarifications - no behavioral change |
| Minor | Additive changes; existing outputs remain valid |
| Major | Output schema changes; existing generated files may require migration |

File naming: {descriptor}-v{Major}.{Minor}.{Patch}.md

Previous versions are retained as files - do not overwrite.

---

## Folder Structure

    prompt-engineering/
    +-- README.md
    +-- roadmap.md
    +-- conventions/
    |   +-- conventions.md
    +-- templates/
    |   +-- prompt-template.md
    +-- prompts/
    |   +-- {category}/
    |       +-- README.md
    |       +-- {descriptor}-v{Major}.{Minor}.{Patch}.md
    +-- tests/
        +-- {category}/
            +-- acceptance-criteria.md

---

## Prompt Categories

| Category | Description |
|----------|-------------|
| competency-matrices | Prompts that generate structured learning and skill-tracking matrices |

Add new rows as categories are created.

---

## Input / Output Contract Fields

All prompts must document the following in their metadata header:

- REQUIRED INPUTS - what the caller must provide
- OPTIONAL INPUTS - parameters with defaults
- EXPECTED OUTPUTS - artifacts produced, format, approximate size
- KNOWN FAILURE MODES - conditions that degrade output quality

---

## Acceptance Criteria

Every prompt must have a corresponding acceptance checklist in tests/{category}/acceptance-criteria.md.
Checklists are verified manually after each run until test volume justifies automation.

---

## Rating Scales

### Dreyfus Competency Scale (default for learning prompts)

| Level | Label | Description |
|-------|-------|-------------|
| 0 | Unencountered | Not yet exposed |
| 1 | Novice | Rule-based; requires guidance |
| 2 | Advanced Beginner | Handles simple tasks independently |
| 3 | Competent | Independent on most tasks; deliberate planning |
| 4 | Proficient | Holistic pattern recognition; handles complexity |
| 5 | Expert | Intuitive mastery; analytic only in novel situations |

---

## Status Definitions

| Status | Meaning |
|--------|---------|
| draft | In development; output quality not guaranteed |
| stable | Verified against acceptance criteria; safe to use |
| deprecated | Superseded by a newer version; retained for reference |

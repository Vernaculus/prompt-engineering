# competency-matrices

Prompts for generating structured, versioned competency matrices to support AI-assisted learning across any subject or body of knowledge.

Matrices are produced as `.md` files with YAML front matter for machine readability and a Markdown body for human readability — designed to live in a note-taking app or version-controlled repo and to serve as a reusable AI session briefing artifact.

---

## Prompts

| File | Version | Description | Status |
|------|---------|-------------|--------|
| [general-v1.0.0.md](./general-v1.0.0.md) | 1.0.0 | Reusable matrix generator for any subject or body of knowledge | stable |
| [az104-v1.0.0.md](./az104-v1.0.0.md) | 1.0.0 | Matrix generator scoped to AZ-104: Microsoft Azure Administrator | stable |

---

## Output Format

Each prompt produces a single `.md` file containing:

- **YAML front matter** — skill hierarchy with Dreyfus 0–5 competency ratings, metadata, and version
- **Exam / Syllabus Domain Map** — official objective mapping and weights
- **Competency Overview** — human-readable summary table of all skills
- **Learning Progression Notes** — prerequisite relationships and sequencing guidance
- **Compact Session Header** — paste-ready AI briefing block for use at the start of study sessions
- **Session Log** — running record of sessions, skills reviewed, and level updates

---

## Competency Rating Scale

All matrices use the Dreyfus model:

| Level | Label | Description |
|-------|-------|-------------|
| 0 | Unencountered | Not yet exposed |
| 1 | Novice | Rule-based; requires guidance |
| 2 | Advanced Beginner | Handles simple tasks independently |
| 3 | Competent | Independent on most tasks; deliberate planning |
| 4 | Proficient | Holistic pattern recognition; handles complexity |
| 5 | Expert | Intuitive mastery; analytic only in novel situations |

---

## Versioning

Prompts follow semantic versioning (`Major.Minor.Patch`):

- **Patch** — clarifications, typo fixes, no behavioral change
- **Minor** — additive changes; existing outputs remain valid
- **Major** — output schema changes; existing `.md` files may require migration

Changelog entries are embedded in each prompt's metadata header.

---

## Usage

1. Copy the full contents of the relevant prompt file
2. Paste into your AI assistant of choice (GPT-4 class model recommended; 32k+ context preferred)
3. Follow the question blocks (general prompt) or receive direct output (az104 prompt)
4. Save the generated `.md` file to your notes or repo
5. Update skill levels and session log after each study session
6. Paste the **Compact Session Header** section at the start of future AI sessions to maintain continuity

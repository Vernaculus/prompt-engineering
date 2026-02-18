# Roadmap

A running record of what has been done and what comes next.
Milestones are tied to meaningful thresholds, not arbitrary dates.

---

## Done

### 2026-02-18 — Foundation
- Repo created: `prompt-engineering`
- License: MIT
- Established folder structure: `prompts/`, `templates/`, `conventions/`, `tests/`
- Authored `CONVENTIONS.md` — metadata schema, versioning rules, rating scales, status definitions
- Authored `prompt-template.md` — reusable scaffold for new prompts
- Published first prompt category: `prompts/competency-matrices/`
  - `general-v1.0.0.md` — reusable matrix generator for any subject
  - `az104-v1.0.0.md` — scoped matrix generator for AZ-104 certification prep
- Both prompts versioned at `1.0.0`, status: `stable`

---

## Up Next

### When you add a second prompt category
- Add a row to the categories table in `conventions.md`
- Create `prompts/{category}/README.md` using `competency-matrices/README.md` as the model
- Create `tests/{category}/acceptance-criteria.md`
- Confirm `prompt-template.md` still covers the new category's needs; bump to `1.1.0` if additions are needed

### When you have 3–5 stable prompts
- Add a repo-level `README.md` with: purpose, folder map, quick-start usage, link to `CONVENTIONS.md`
- Review whether any prompts share reusable components (e.g., shared role definitions, output schemas) that warrant extraction into a `components/` or `partials/` folder
- Consider tagging `v1.0.0` in git as a baseline release

### When you have 10+ prompts across multiple categories
- Add a prompt index (simple table in repo `README.md`) listing all stable prompts with one-line descriptions
- Evaluate whether manual acceptance criteria checklists are creating enough friction to justify a lightweight automated eval script
- Assess whether any prompts have diverged from `conventions.md` and need alignment

### When you share with or onboard another person
- Add `contributing.md` — keep it short: link to `conventions.md`, describe the PR expectation, define what "stable" means before merging
- Add GitHub branch protection on `main`
- Add issue templates: `new-prompt.md`, `prompt-bug.md`

### When a prompt reaches its third major version
- Formally assess whether the prompt has stabilized enough to extract its output schema into a standalone spec file in `conventions/schemas/`
- This is the signal that the prompt has matured from a tool into infrastructure

---

## Deliberately Deferred

These are worth knowing about but not worth doing yet:

- **CI/CD pipeline** — adds overhead before prompt volume justifies it
- **Automated eval/testing** — manual checklists are sufficient under ~15 prompts
- **Changelog at repo root** — redundant while changelogs live in prompt headers
- **Monorepo tooling** (Nx, Turborepo, etc.) — not applicable at this scale

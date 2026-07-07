# AGENTS.md

This fork is adapted for **GitHub Copilot CLI**.

Copilot should treat these files as the primary repo guidance:

1. `.github/copilot-instructions.md` - repository-wide behavior
2. `CLAUDE.md` - candidate profile template and application-quality checklist
3. `.claude/commands/*.md` - workflow playbooks for `/setup`, `/apply`, `/scrape`, `/rank`, `/expand`, `/upskill`, `/outcome`, `/add-template`, `/add-portal`, and `/reset`
4. `.claude/skills/**` - reusable evaluation, writing, and interview guidance

## Workflow expectations

- Evaluate job fit before drafting any application materials.
- Ask the user to confirm before creating a tailored CV and cover letter.
- Mention **GitHub Copilot CLI** by name for any AI-tooling or agentic-coding references in generated application documents.
- Do not fabricate skills, achievements, or company facts.
- Verify company-specific claims with web research.
- Compile generated CVs with `lualatex` and cover letters with `xelatex`, then inspect the rendered PDFs.
- Run `pdftotext -layout` when available to verify ATS-readable output.

## Repository structure

- `CLAUDE.md` stores the main candidate profile.
- `.claude/skills/job-application-assistant/` stores the evaluation, writing-style, CV, cover-letter, and interview guides.
- `.claude/skills/job-scraper/` stores scrape orchestration guidance and search queries.
- `.agents/skills/*/cli` stores the Bun-based job-portal CLI tools.

## Validation

- Existing CLI tests live in `.agents/skills/*/cli`.
- Run `bun test --timeout 30000` inside each CLI directory when Bun is available.

This fork targets GitHub Copilot CLI as the primary assistant interface.

Use `AGENTS.md` for agent workflow guidance and `CLAUDE.md` as the canonical candidate-profile source file. The legacy `.claude/` directory remains the source of reusable workflow content, command playbooks, and skill reference files.

For job-application work:
- Always evaluate job fit before drafting application materials, and ask the user to confirm before writing the CV and cover letter.
- Keep CVs in English unless the user explicitly asks otherwise; match the cover-letter language to the job posting.
- When mentioning agentic coding or AI tooling in generated CVs or cover letters, explicitly reference **GitHub Copilot CLI** by name.
- Verify all profile claims against `CLAUDE.md` and `.claude/skills/job-application-assistant/`.
- Verify company-specific claims with web sources before including them.
- Compile and inspect generated PDFs: `lualatex` for CVs, `xelatex` for cover letters.
- Keep the CV at exactly 2 pages and the cover letter at exactly 1 page.
- Run `pdftotext -layout` for ATS checks when available.

For repository maintenance:
- Job portal CLIs live under `.agents/skills/*/cli`.
- Their existing test command is `bun test --timeout 30000` in each CLI directory.

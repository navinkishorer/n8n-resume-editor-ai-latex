# n8n Resume Editor (LaTeX) . DeepSeek (AI)

A production style n8n workflow that edits LaTeX resumes safely using DeepSeek.
It updates only marked sections in a `.tex` template to match a job description while preserving formatting, macros, and structure.

![Workflow](n8n-resume-editor-ai-latex/docs/screenshots/Workflow-n8n.png)

## What it does
Given:
- a target role (predefined)
- a job description
- a role specific skill checklist
- a LaTeX resume template with markers

The workflow:
1. Loads the correct resume template for the role
2. Extracts marked blocks (LOCATION, SUMMARY, SKILLS, EXPERIENCE, PROJECTS)
3. Calls DeepSeek (OpenAI compatible endpoint)
4. Validates the model output for safety
5. Replaces only the marked blocks
6. Writes a new `.tex` file to output/

## Why this is useful
- Preserves your LaTeX formatting and custom macros
- Prevents the model from changing `\usepackage` or adding new commands
- Produces recruiter ready tailored resumes in seconds

## Tech
- n8n workflow automation
- DeepSeek API (chat completions)
- LaTeX templates with marker based patching
- Validation + guardrails (forbidden tokens, brace balance)

---

## Quickstart

### 1. Import workflow into n8n
Import:
`workflow/resume-editor-deepseek-5blocks.json`

### 2. Create local folders
Run:
```bash
bash scripts/setup_dirs.sh

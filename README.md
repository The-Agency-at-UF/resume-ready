# Resume Ready

A Claude skill that helps students turn their work on Agency projects into concise, business-focused resume bullets.

![Resume Ready](image.png)

## Table of Contents

- [What is Resume Ready?](#what-is-resume-ready)
- [Tech Stack](#tech-stack)
- [Prerequisites](#prerequisites)
- [How to get started](#how-to-get-started)
- [Example output](#example-output)
- [How to contribute](#how-to-contribute)
- [How to review changes](#how-to-review-changes)
- [Contact](#contact)

## What is Resume Ready?

**The problem:** Students build websites, applications, and digital experiences for Agency clients, but translating that work into a resume accomplishment can be difficult. Project documents often describe features and plans without clearly stating individual contributions, measurable scope, or business value.

**The solution:** Resume Ready reads project briefs, meeting notes, technical documents, and reports to generate resume bullets that connect confirmed deliverables to organizational or community value.

**Who it's for:** Students in The Agency's Development Department at the UF College of Journalism and Communications who want to describe their project contributions on resumes, portfolios, and showcase presentations.

### What it produces

- One bullet per project by default, targeting **20–35 words**.
- A strong action verb followed by a quantified deliverable and its business value.
- **X** placeholders for missing numbers, such as page counts, percentages, or hours.
- A **Verify** line identifying missing metrics or project status details needed to finalize each bullet.

The skill preserves verified numbers and never invents results, deployment status, revenue, adoption, donations, or cost savings. Unverified benefits are described as intended outcomes, and planned features are not treated as completed work.

You can request an **executive showcase**, **developer resume**, or **metrics-first** version. Ask for **only bullets** to omit Verify lines while retaining accurate wording for unverified outcomes.

## Tech Stack

This repository contains a Claude skill written in Markdown, with YAML frontmatter defining its name and description.

- [SKILL.md](resume-ready-skill/SKILL.md): Main instructions, extraction workflow, bullet rules, and examples.
- [context/](resume-ready-skill/context/): Source documents read before drafting bullets, including documents in subfolders. Add reusable organization background and project evidence here.
- [metric-ideas.md](resume-ready-skill/references/metric-ideas.md): Suggested metrics for websites, AI automation, internal tools, archives, and marketing sites, including projects without users yet.

There is no application build or local server to run.

## Prerequisites

- Access to Claude and a way to provide readable project materials in your conversation.
- Project briefs, meeting notes, technical documents, reports, or other materials documenting your work.
- Details about your personal contribution and the project's current status.
- For contributors: Git or GitHub Desktop and a text editor such as VS Code.

## How to get started

1. Download or clone this repository. Add any reusable source documents to `resume-ready-skill/context/`, then compress the `resume-ready-skill` folder into `resume-ready-skill.zip`. Include `SKILL.md`, `references`, and `context`; do not zip the entire repository. Rebuild and re-upload the ZIP after changing bundled documents.
2. Sign in to Claude and open [Customize > Skills](https://claude.ai/customize/skills).
3. Click **+ Add**, select **Upload Skill**, and choose `resume-ready-skill.zip`.
4. Confirm that **resume-ready** appears in your skills list and is toggled on.
5. Start a new conversation and attach any additional company documents and project description. The skill reads bundled `context/` documents before drafting and uses them alongside your attachments; if the folder is empty, it uses the available attachments and facts you provide.
7. Ask Claude to use **Resume Ready** to write a resume bullet.
8. Review the bullet against your source documents. Replace **X** placeholders with verified numbers and resolve any **Verify** items before adding it to a resume.

### Example prompt

```text
Use Resume Ready to create one developer resume bullet for Adora Lin's work
on the Gator Unidos client project using the attached project details and
company documents. Her contribution was [describe her specific work], and
the project is [completed / in progress / proposed]. Use X for missing
metrics and list any details I need to verify.
```

When documents disagree, the skill prioritizes the most recent explicit project status and flags unresolved discrepancies.

## Example output

Developed 3 pages and 4 features for a non profit supporting UF Latino students professional development resulting in 2000 dollars in additional donations. 

# How to contribute
1. Clone the repo & pull the latest `main` to avoid merge conflicts:
```bash
   git checkout main
   git pull
```
2. Create a new branch named `[your-initials]/[feature-name]`:
```bash
   git checkout -b hs/metric-suggestions
```
3. Confirm you're on the right branch with `git branch` or check via GitHub Desktop
4. Publish your branch in GitHub Desktop, then make your edits in VSCode
5. Commit using [Conventional Commits](https://gist.github.com/Zekfad/f51cb06ac76e2457f11c80ed705c95a3) format:
   - Example: `docs: clarify skill usage`
   - Example: `feat: add metric suggestions`
6. Push your branch and open a pull request describing the changes and how you checked them. Use the [pull request template](pull_request_template.md).
7. Request review

# How to review code
1. In GitHub Desktop, switch to the contributor's branch to pull it locally
2. Run the project locally
3. Test the changes:
   - Does the new feature work as described in the PR?
   - Are there any console errors or warnings?
   - Does the existing functionality still work?
4. On the GitHub PR page, click **Files changed** and leave inline comments on specific lines
5. Submit your review as **Approve**, **Request changes**, or **Comment**

## Contact

**Project Lead:** Hiral Shukla via Slack or [hiralshukla@ufl.edu](mailto:hiralshukla@ufl.edu)

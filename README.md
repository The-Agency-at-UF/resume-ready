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

- One bullet per project by default, targeting **15–25 words**.
- A strong action verb followed by a quantified deliverable and its business value.
- **X** placeholders for missing numbers, such as page counts, percentages, or hours.
- A **Verify** line identifying missing metrics or project status details needed to finalize each bullet.
- A **Sources** list of the documents used for each bullet.

The skill preserves verified numbers and never invents results, deployment status, revenue, adoption, donations, or cost savings. Unverified benefits are described as intended outcomes, and planned features are not treated as completed work.

You can request an **executive showcase**, **developer resume**, or **metrics-first** version. Ask for **only bullets** to omit Verify lines. The **Sources** list still appears.

## Tech Stack

This repository contains a Claude skill written in Markdown, with YAML frontmatter defining its name and description.

- [SKILL.md](resume-ready-skill/SKILL.md): Main instructions, extraction workflow, bullet rules, and examples.
- [Drive folder configuration](resume-ready-skill/context/README.md): Stores the shared folder link for the skill. Project evidence stays in Google Drive.
- [metric-ideas.md](resume-ready-skill/references/metric-ideas.md): Suggested metrics for websites, AI automation, internal tools, archives, and marketing sites, including projects without users yet.

There is no application build or local server to run.

## Prerequisites

- Access to Claude with the Google Drive connector enabled and a connected Google account that can read the shared folder. On Team and Enterprise plans, a Claude organization owner may need to enable the connector first. [Claude Google Workspace connector instructions](https://support.claude.com/en/articles/10166901-use-google-workspace-connectors)
- Project briefs, meeting notes, technical documents, reports, or other materials documenting your work.
- Details about your personal contribution and the project's current status.
- For contributors: Git or GitHub Desktop and a text editor such as VS Code.

## How to get started

1. Download or clone this repository. Make any edits. Compress the `resume-ready-skill` folder into `resume-ready-skill.zip`.
2. Sign in to Claude and connect Google Drive in Claude under **Customize > Connectors** and enable it in the chat. Use your UFL Google account.
3. Resume Ready uses the shared folder in [the folder configuration](resume-ready-skill/context/README.md). To change the folder for an installation, update the `Drive folder URL` field before packaging. If you updated the default folder URL, rebuild the ZIP from the repository root with PowerShell. The packaged skill contains its instructions and writing guides.

   ```powershell
   Compress-Archive -LiteralPath ./resume-ready-skill -DestinationPath ./resume-ready-skill.zip -Force
   ```

4. Open [Customize > Plugin](https://claude.ai/customize/skills), then**+ Add > Upload Plugin**, and select `resume-ready-skill.zip`. Ensure the uploaded skill is enabled.
5. Start a new chat. Ask Claude to use Resume Ready via using `/resume-ready-skill` command. Follow the command with your prompt including stating the name of the person, the project, and contribution and ask for a resume bullet to be written. Attach supporting files or paste relevant excerpts if you have additional project details.
6. Read over the documents listed under **Sources** and confirm they support the bullet. If folder browsing fails, attach readable copies or paste relevant excerpts. Review any **X** placeholders and **Verify** items before using the bullet.

### Example prompt

```text
Use Resume Ready to create one developer resume bullet for Adora Lin's work
on the Gator Unidos client project using our shared Google Drive folder.
Her contribution was [describe her specific work], and
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

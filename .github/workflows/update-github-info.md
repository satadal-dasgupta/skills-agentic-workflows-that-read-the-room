---
name: update-github-info
description: Draft concise GitHub Info updates for Mona from official GitHub sources and open a reviewable pull request.
model: gpt-5.4
on:
  workflow_dispatch:
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.com
    - github.blog
    - awesome-copilot.github.com
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any updates.

Follow these steps:

- Read `notes/mona-notes.md`.
- Read external public guidance with web-fetch, especially:
  - https://github.blog/latest/
  - https://github.blog/changelog/
  - https://awesome-copilot.github.com/workflows/
- Read repository guidance or reference files with GitHub repository API tools instead of terminal, CLI, or sandboxed commands.
- Update `site/content/github-info.md` with short, practical, developer-focused GitHub updates.
- Mention the source of any update from the GitHub Blog, GitHub Changelog, or Awesome Copilot workflows.
- Keep the language clear and useful for developers learning GitHub faster.
- Open a pull request for Mona to review using `safe-outputs` with `create-pull-request`.
- Do not write directly to `main`; propose changes through the pull request flow.
- Before finalizing the draft, check that the workflow configuration syntax is valid and that the frontmatter keys are correctly formed.
- Do not compile the workflow. Only edit the markdown workflow file and then prepare the proposed website change.

Use the GitHub Blog, GitHub Changelog, and Awesome Copilot workflows as source material for updates to `site/content/github-info.md`.

The pull request should be created through the safe output mechanism so Mona can review the draft before it goes live.

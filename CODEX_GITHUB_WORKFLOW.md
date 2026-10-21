# ChatGPT GitHub Integration Test Record

This file records an end-to-end test of ChatGPT's Codex integration with
GitHub for this repository.

## Verified actions

- Authenticated to GitHub as the repository owner.
- Created GitHub issue #1.
- Created the `codex/verify-github-workflow` branch.
- Added and committed a repository file.
- Pushed the branch and opened pull request #2.
- Linked the pull request to issue #1 with `Closes #1`.
- Confirmed the pull request was mergeable and merged it.
- Confirmed that merging the pull request closed issue #1 automatically.

No credentials or secrets are stored in this repository.

# ChatGPT GitHub Integration Test

This repository is a small, disposable test project for validating ChatGPT's
Codex integration with GitHub.

## What this repository tests

- authenticating to GitHub from a local Codex project;
- creating and managing GitHub issues;
- creating branches, files, and commits;
- pushing changes and opening pull requests;
- linking pull requests to issues with GitHub closing keywords; and
- checking merge readiness and merging pull requests.

The repository contains no production application, research data, or sensitive
information.

## Completed workflow

The first end-to-end test created
[issue #1](https://github.com/martingerdin/test-codex-access/issues/1), opened
[pull request #2](https://github.com/martingerdin/test-codex-access/pull/2), and
verified that merging the pull request automatically closed the linked issue.

See [`CODEX_GITHUB_WORKFLOW.md`](CODEX_GITHUB_WORKFLOW.md) for the test record.

## Safety

Use this repository only for GitHub integration testing. Do not commit access
tokens, credentials, personal data, or other sensitive material.

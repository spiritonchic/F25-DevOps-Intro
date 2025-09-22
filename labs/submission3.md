# Lab 3 — CI/CD with GitHub Actions

Goal: Build foundational CI/CD workflows in GitHub Actions: quickstart, triggers, logs, and system information.

------------------------------------------------------------
# Task 1 — First GitHub Actions Workflow (4 pts)

## 1.1 Following GitHub Actions Quickstart

I followed the GitHub Actions Quickstart Guide and created a minimal workflow file

Key steps performed:
- Created .github/workflows/github-actions-demo.yml.
- Added on: [push] to trigger on push.
- Used actions/checkout@v5 to clone the repo.
- Added run steps to print runner and environment info.

## 1.2 Testing Workflow Trigger

Pushed a commit to the repository to trigger the workflow automatically.

Run link:
[Successful workflow run](https://github.com/spiritonchic/F25-DevOps-Intro/actions/runs/17920989838)

What I observed:
- In the Actions tab, a new run appeared automatically after push.
- Each run command prints its output in real time.

Concepts Learned:

Workflows — YAML files under .github/workflows/ describing automation.

Triggers — Events like push start workflows.

Jobs — Group of steps run on a specified runner.

Steps — Individual commands or actions executed sequentially inside a job.

Runners — Machines (GitHub-hosted or self-hosted) that execute jobs.

Cause of Run Trigger:

- The run was automatically triggered by a push event when I committed changes.

Workflow Execution Process:

1. Event (push) detected by GitHub Actions.
2. A new runner (Ubuntu VM) is allocated.
3. Jobs defined in the workflow are scheduled.
4. Steps execute one by one:
    - Initial echo commands run.
    - actions/checkout@v5 clones the repo into $GITHUB_WORKSPACE.
    - Remaining commands run inside that workspace.
5. Logs are stored and visible under each step.
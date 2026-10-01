# CMPE-272 Project

**Course:** FA26 CMPE-272 Sec 49 - Enterprise SW Platforms (SJSU)
**Author:** 傅炜浩

Demo project for HW #5: Jenkins + GitHub integration.

- `Jenkinsfile` — declarative pipeline (build + test stages, GitHub push trigger)
- `app.py` — tiny sample app
- `tests/` — pytest test suite
- `.github/` — (reserved)

## Jenkins integration

1. Jenkins runs on Windows (local machine).
2. A Jenkins pipeline job `cmpe272-project-build` pulls this repo.
3. Build trigger: **GitHub webhook** — every push to `main` triggers a build automatically
   (webhook forwarded to the local Jenkins via smee.io).

## GitHub Project

Work is tracked in the **CMPE-272 Project Tracker** project
(Sprint iteration field, Priority field, Kanban board, done-automation).

## Webhook test
Push-triggered build verification (Jenkins + GitHub webhook).

## Auto-build verification
Second push test: verifying Jenkins auto-triggers on GitHub push.

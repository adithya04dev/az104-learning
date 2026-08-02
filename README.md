# AZ-104 Learning Workspace

A stateful Microsoft Azure Administrator learning workspace designed to build practical Azure administration skill and prepare for Exam AZ-104.

## Start here

Open [`lessons/index.html`](lessons/index.html) in a browser. Complete each theory page and then its matching lab:

1. Identity lifecycle
2. Effective Azure access
3. Governance guardrails

Use [`reference/identity-governance-cheat-sheet.html`](reference/identity-governance-cheat-sheet.html) for review after completing the lessons.

## Workspace map

- [`MISSION.md`](MISSION.md) — why this learning project exists and what success means
- [`STUDY_PLAN.md`](STUDY_PLAN.md) — mastery-based roadmap for all AZ-104 domains
- [`RESOURCES.md`](RESOURCES.md) — curated official Microsoft sources
- [`NOTES.md`](NOTES.md) — teaching preferences and open setup questions
- [`learning-records/`](learning-records/) — demonstrated prior knowledge and future mastery records
- [`lessons/`](lessons/) — self-contained interactive theory and lab pages
- [`reference/`](reference/) — printable rapid-reference material

## Current status

The learner has completed a conceptual first pass of identity and governance. The current lesson pack consolidates that knowledge through scenarios, quizzes, and permission-aware labs. Hands-on mastery should only be recorded after the evidence gates are completed.

## Continue from another workspace

```bash
git clone https://github.com/adithya04dev/az104-learning.git
cd az104-learning
open lessons/index.html
```

If `open` is unavailable, open `lessons/index.html` directly in a browser.

Before teaching or adding material, read `MISSION.md`, `NOTES.md`, the most recent learning record, and the relevant official sources in `RESOURCES.md`.

## Safety

Labs must be run only in a personal Azure lab tenant or an explicitly approved work sandbox. Verify the tenant, subscription, scope, permissions, expected cost, and cleanup steps before making changes. Never commit credentials, tokens, tenant exports, or `.env` files.

## Source alignment

The current roadmap and identity/governance pack align with the Microsoft AZ-104 skills measured from April 17, 2026. Recheck the [live Microsoft study guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104) before scheduling the exam.

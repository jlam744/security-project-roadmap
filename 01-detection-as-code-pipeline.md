# Project 01: Detection-as-Code pipeline

> **Target repo:** `sentinel-detections` | **Difficulty:** Advanced | **Time:** 2 weeks | **Cost:** Free (GitHub Actions + Sentinel trial or lab workspace)

## Goal

Manage Sentinel analytics rules the way software teams manage code: rules live in GitHub, every change is validated automatically, and merged rules deploy to Sentinel without anyone clicking through the portal.

## Why hiring managers care

"Detection-as-Code" is how mature detection teams work. It shows you think like an engineer (version control, testing, CI/CD), not only like an analyst.

## Skills you'll show

- Microsoft Sentinel analytics rules (ARM/Bicep or YAML format)
- GitHub Actions CI/CD
- Validation and linting of rule metadata
- Git workflow: branches, pull requests, reviews

## Prerequisites

- A Sentinel workspace you control (personal Azure subscription)
- At least 5 rules already in `sentinel-detections`

## Milestones

- [ ] Choose a rule format (Sentinel YAML like the Azure-Sentinel repo, or ARM templates) and convert 5 existing rules to it
- [ ] Write a Python validator that checks every rule has: name, severity, ATT&CK tactic and technique, query, frequency and lookback
- [ ] Add a GitHub Actions workflow that runs the validator on every pull request and fails if a rule is invalid
- [ ] Connect deployment: either Sentinel's built-in Repositories feature or a workflow step using Azure CLI
- [ ] Prove it end to end: open a PR that changes a rule threshold, watch CI pass, merge, confirm the change in Sentinel
- [ ] Write the README with an architecture diagram of the pipeline

## Deliverables

- `rules/` in the deployable format
- `scripts/validate_rules.py` with tests
- `.github/workflows/validate.yml` (and `deploy.yml` if you deploy from Actions)
- README section "How rules get to production" with a diagram and screenshots of a passing PR check

## Stretch goals

- Auto-generate the rules table in the README from rule metadata
- Run each query against sample data in CI to catch syntax errors
- Add a CODEOWNERS file so rule changes need review

## Interview talking points

- Why version control matters for detections (audit trail, rollback, peer review)
- What you validate in CI and what you can't
- How you'd handle an urgent rule change during an incident

## Resources

- [Azure-Sentinel GitHub repo](https://github.com/Azure/Azure-Sentinel) (rule format examples)
- Microsoft Learn: "Deploy custom content from your repository" (Sentinel Repositories)
- GitHub Actions documentation

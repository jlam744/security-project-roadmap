# Project 02: ATT&CK coverage map generator

> **Target repo:** `sentinel-detections` | **Difficulty:** Intermediate | **Time:** 3-4 days | **Cost:** Free

## Goal

Write a Python script that reads the ATT&CK IDs from every rule in `sentinel-detections` and generates a MITRE ATT&CK Navigator layer, so anyone can see at a glance which techniques you cover and where the gaps are.

## Why hiring managers care

Coverage mapping is how detection teams decide what to build next. It shows you think about detection as a program, not one rule at a time.

## Skills you'll show

- MITRE ATT&CK framework
- Python (file parsing, JSON generation)
- Gap analysis and prioritization

## Prerequisites

- Rules in `sentinel-detections` with ATT&CK IDs in a consistent place (the TEMPLATE.md table)

## Milestones

- [ ] Write `scripts/coverage.py` that walks `rules/` and `hunting/` and extracts each ATT&CK technique ID
- [ ] Generate a Navigator layer JSON file, scoring rules higher than hunting queries
- [ ] Load it in ATT&CK Navigator and export a screenshot
- [ ] Add a "Coverage" section to the README with the screenshot and the count of techniques covered
- [ ] Write a short gap analysis: 5 techniques you don't cover yet and why each is worth building next

## Deliverables

- `scripts/coverage.py` with a test
- `coverage/layer.json`
- README "Coverage" section with screenshot and gap analysis

## Stretch goals

- Run the script in GitHub Actions so the layer updates on every merge
- Color techniques by data source so you can see which log sources carry the most coverage

## Interview talking points

- How you prioritize which techniques to detect first
- Why 100% ATT&CK coverage is not the goal
- The difference between having a rule for a technique and actually detecting it

## Resources

- [MITRE ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator/)
- ATT&CK Navigator layer format documentation (in the Navigator GitHub repo)

# Project 11: CloudGoat from the defender's side

> **Target repo:** `aws-ir-lab` (case files in `incident-casebook`) | **Difficulty:** Intermediate | **Time:** 1 scenario per week | **Cost:** Low (tear down after each scenario)

## Goal

Most CloudGoat write-ups are from the attacker's view. Write them from the defender's view: run each scenario with CloudTrail recording, then investigate your own attack as if you were the IR team, and write the detections that would have caught it.

## Why hiring managers care

It shows you understand AWS attack paths and can find them in logs, which is the core of a cloud IR role. Defender-side write-ups also stand out because they're rare.

## Skills you'll show

- AWS IAM privilege escalation paths
- CloudTrail investigation
- Writing cloud detections in KQL or CloudTrail Lake SQL

## Prerequisites

- CloudGoat installed, AWS lab account, CloudTrail on in all regions
- Somewhere to query CloudTrail: Sentinel's AWS connector, CloudTrail Lake, or Athena

## Milestones

Repeat for each scenario:

- [ ] Note the start time, run the scenario, note the end time
- [ ] Without looking at your attack notes, reconstruct the attack from CloudTrail alone
- [ ] Build a timeline: every API call that mattered, by which identity, from which IP
- [ ] Write at least one detection for the key step
- [ ] Write the fix: the misconfiguration that made it possible
- [ ] Destroy the scenario

## Deliverables

- One case file per scenario in `incident-casebook`
- Detections in `aws-ir-lab/detections/`
- A table in the `aws-ir-lab` README: scenario, key technique, detection, fix

## Stretch goals

- Compare what GuardDuty caught on its own with what only your custom detection caught

## Interview talking points

- An IAM privilege escalation path you found in logs and how you spotted it
- What CloudTrail does not record (data events off by default) and why that matters
- Prevention vs detection for each scenario

## Resources

- [CloudGoat](https://github.com/RhinoSecurityLabs/cloudgoat)
- Rhino Security Labs IAM privilege escalation research

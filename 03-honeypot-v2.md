# Project 03: Honeypot v2, from map to response

> **Target repo:** `SentinelGeo_lab` (upgrade your existing project) | **Difficulty:** Intermediate | **Time:** 1 week | **Cost:** Low (Azure VM running a few days)

## Goal

Your honeypot already shows where RDP attacks come from. Version 2 turns it into a full detect-and-respond loop: an analytics rule that alerts on brute force, an incident in Sentinel, and an automated response.

## Why hiring managers care

Many candidates have built the honeypot map. Few take it further. Adding detection logic and response shows you understand what happens after the data lands.

## Skills you'll show

- KQL analytics rules and workbooks
- Sentinel incidents and automation rules
- Logic Apps (playbooks)
- Writing up results with real numbers

## Prerequisites

- The original lab rebuilt (VM, Log Analytics workspace, Sentinel)
- Consider replacing the custom PowerShell log export with the Azure Monitor Agent and querying `SecurityEvent` directly, and explain why in the README

## Milestones

- [ ] Rebuild the lab and collect at least 48 hours of attack data
- [ ] Write an analytics rule: more than N failed logons (Event 4625) from one IP in 10 minutes
- [ ] Write a second rule for the dangerous case: a successful logon (4624) from an IP that previously failed many times
- [ ] Build a Sentinel workbook: top source countries, top usernames tried, attempts over time
- [ ] Create a playbook that adds the attacker IP to a watchlist and comments on the incident
- [ ] Write a results section: total attempts, unique IPs, top 10 usernames attackers tried, and what that says about real attacks
- [ ] Tear down the VM

## Deliverables

- Updated README with "v2" section, architecture diagram and results
- `detections/` with both KQL rules documented using the sentinel-detections template
- Workbook JSON export
- Screenshots of an incident and the playbook run

## Stretch goals

- Add an SSH honeypot (Linux VM) and compare attacker behavior across RDP and SSH
- Enrich IPs with your `soc-automation` IOC tool

## Interview talking points

- What attackers try first (usernames like administrator, admin, test) and what that tells defenders
- Why the successful-after-failures rule matters more than the brute-force rule
- How you'd tune the threshold to avoid alert fatigue

## Resources

- Microsoft Learn: Sentinel analytics rules, workbooks, and playbooks
- Windows Security Event IDs 4624 and 4625 documentation

# Project 04: Kerberoasting detection lab

> **Target repo:** `sentinel-detections` (plus a case file in `incident-casebook`) | **Difficulty:** Intermediate | **Time:** 1 week | **Cost:** Free (local VMs)

## Goal

Build a small Active Directory lab, run a Kerberoasting attack against it, find the evidence in the logs, and write a detection that catches it.

## Why hiring managers care

Active Directory attacks are still behind many real breaches. Doing the attack yourself and then detecting it shows you understand both sides, which is what purple teaming means.

## Skills you'll show

- Active Directory (builds on your AD bulk user project)
- Kerberos authentication and Windows event logs
- Writing detections from attack evidence
- Purple team method: attack, observe, detect, tune

## Prerequisites

- VirtualBox or Hyper-V with a Windows Server domain controller and one Windows client
- A service account with an SPN and a weak password (lab only)
- Logs forwarded to Sentinel, or reviewed locally in Event Viewer

## Milestones

- [ ] Build the domain and create a service account with an SPN
- [ ] Turn on auditing for Kerberos Service Ticket Operations
- [ ] From the client, request service tickets with a Kerberoasting tool (for example Rubeus or Impacket's GetUserSPNs)
- [ ] Find the Event ID 4769 entries and note what's different about them (ticket encryption type, request volume, the account requesting)
- [ ] Write a KQL detection based on what you observed
- [ ] Document false positives you'd expect in a real environment
- [ ] Write the full case file: attack, evidence, detection, mitigation

## Deliverables

- Detection rule in `sentinel-detections/rules/credential-access/T1558.003-kerberoasting.md`
- Case file in `incident-casebook`
- Lab setup notes (no passwords committed)

## Stretch goals

- Detect AS-REP Roasting (T1558.004) the same way
- Set up a honeypot service account with an SPN that should never be requested, and alert on any request for it

## Interview talking points

- Why RC4 ticket encryption is a strong signal
- Why the real fix is strong service account passwords or gMSAs, not only detection
- How a honey SPN gives a near-zero false positive alert

## Resources

- [MITRE ATT&CK T1558.003](https://attack.mitre.org/techniques/T1558/003/)
- Microsoft documentation for Event ID 4769

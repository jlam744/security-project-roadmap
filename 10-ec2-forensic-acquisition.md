# Project 10: EC2 forensic acquisition tool

> **Target repo:** `aws-ir-lab` | **Difficulty:** Advanced | **Time:** 1 week | **Cost:** Low (snapshots and a small forensic instance; delete after)

## Goal

Write a Python tool that collects evidence from a suspected compromised EC2 instance without changing it: snapshot its volumes, capture its metadata and network setup, copy the snapshots to a separate forensic account or locked-down area, and record a chain of custody.

## Why hiring managers care

Evidence handling is what separates incident response from cleanup. Cloud forensics is a specialized skill few junior candidates can show.

## Skills you'll show

- Python and boto3 (EC2, EBS, S3)
- Forensic principles: preserve before you act, chain of custody, integrity hashes
- Cross-account snapshot sharing and encryption with KMS

## Prerequisites

- AWS lab account (a second "forensics" account is ideal, but a separate tagged area works)
- A test EC2 instance to treat as compromised

## Milestones

- [ ] Given an instance ID, record its metadata: AMI, IAM role, security groups, network interfaces, tags, launch time
- [ ] Snapshot every attached EBS volume and tag each with case ID, collector, and time
- [ ] Copy or share snapshots to the forensic account (handle KMS-encrypted volumes)
- [ ] Write a chain-of-custody JSON file with every action, timestamp and resource ID, and hash it
- [ ] In the forensic account, create a volume from the snapshot and attach it read-only to an analysis instance
- [ ] Document how to examine the mounted volume (for example look at logs and user histories)

## Deliverables

- `forensics/acquire.py` with a `--dry-run` mode and tests
- Chain-of-custody example output (with fake IDs)
- README: workflow diagram, required IAM permissions, and analysis steps

## Stretch goals

- Capture memory with a tool such as LiME or AVML before snapshotting, and explain the tradeoffs
- Combine with Project 09 so containment triggers acquisition automatically

## Interview talking points

- Why you collect before you contain or terminate
- How you prove evidence wasn't changed
- What volatile evidence you lose by only taking disk snapshots

## Resources

- AWS Security Incident Response Guide (whitepaper), forensics sections
- AWS docs: sharing EBS snapshots and KMS keys across accounts

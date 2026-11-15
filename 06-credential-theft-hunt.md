# Project 06: Credential theft hunt on public data

> **Target repo:** `incident-casebook` (hunting queries in `sentinel-detections/hunting`) | **Difficulty:** Intermediate | **Time:** 4-5 days | **Cost:** Free

## Goal

Run a hypothesis-driven threat hunt for credential dumping (for example LSASS memory access) using recorded attack datasets, and write it up as a formal hunt report.

## Why hiring managers care

Threat hunting is a step beyond alert triage: you start from a hypothesis, not an alert. A clean hunt report shows structured thinking.

## Skills you'll show

- Hypothesis-driven threat hunting
- Windows and Sysmon telemetry (process access, process creation)
- Loading raw JSON datasets into a queryable tool (Azure Data Explorer free cluster or Sentinel custom logs)

## Prerequisites

- A credential access dataset from OTRF Security-Datasets
- A free Azure Data Explorer cluster or a Log Analytics workspace to ingest it

## Milestones

- [ ] Write the hypothesis first: "An attacker on host X accessed LSASS memory to steal credentials"
- [ ] Load one or two OTRF credential access datasets into ADX or Log Analytics
- [ ] Hunt: which processes accessed lsass.exe, with what access rights, from what parent process?
- [ ] Separate the malicious activity from normal system behavior and explain how
- [ ] Turn your best query into a hunting query and a detection
- [ ] Write the hunt report: hypothesis, data, method, findings, detection, recommendations

## Deliverables

- Hunt report in `incident-casebook/cases/` (adapt the template: "Hypothesis" replaces "Scenario")
- Hunting query in `sentinel-detections/hunting/credential-access/`
- Short "how I loaded the data" guide so others can reproduce it

## Stretch goals

- Repeat for a second technique (for example DCSync)
- Compare what Sysmon shows against Windows Security events alone

## Interview talking points

- The difference between hunting and responding to alerts
- How you avoid confirmation bias during a hunt
- What you'd do when a hunt finds nothing (it's still a result)

## Resources

- [OTRF Security-Datasets](https://github.com/OTRF/Security-Datasets)
- [OTRF ThreatHunter-Playbook](https://github.com/OTRF/ThreatHunter-Playbook)
- [MITRE ATT&CK T1003.001](https://attack.mitre.org/techniques/T1003/001/)

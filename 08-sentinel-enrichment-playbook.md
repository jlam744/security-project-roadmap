# Project 08: Sentinel enrichment playbook

> **Target repo:** `soc-automation` | **Difficulty:** Intermediate | **Time:** 1 week | **Cost:** Low (Logic Apps consumption pricing)

## Goal

Build a Sentinel playbook (Logic App) that runs when an incident is created, pulls out IP entities, looks them up in AbuseIPDB, and writes the results back to the incident as a comment, so the analyst sees context before they start.

## Why hiring managers care

SOAR experience is often listed for security engineer roles. A working playbook with before and after screenshots shows you can measurably cut triage time.

## Skills you'll show

- Logic Apps and Sentinel automation rules
- Managed identity and secure handling of API keys (Key Vault)
- Incident entity mapping

## Prerequisites

- Sentinel workspace with at least one analytics rule that maps IP entities (your honeypot rules work)
- Free AbuseIPDB API key

## Milestones

- [ ] Create a Logic App with the Microsoft Sentinel incident trigger
- [ ] Store the API key in Azure Key Vault and give the Logic App a managed identity to read it
- [ ] Loop over IP entities and call the AbuseIPDB API
- [ ] Add a comment to the incident with a formatted table of results
- [ ] Raise the incident severity if any IP has a high abuse score
- [ ] Attach the playbook to incidents with an automation rule
- [ ] Export the Logic App as an ARM template for the repo (remove secrets and IDs)

## Deliverables

- `playbooks/enrich-ip-abuseipdb/azuredeploy.json`
- README with architecture, deploy steps, and screenshots of an incident before and after enrichment

## Stretch goals

- Add a "Deploy to Azure" button to the README
- Second playbook: block the IP in a network security group after analyst approval

## Interview talking points

- Why you used Key Vault and managed identity instead of a key in the workflow
- When automation should act on its own vs wait for a human
- How you'd measure the time saved

## Resources

- Microsoft Learn: automate threat response with playbooks in Microsoft Sentinel
- [Azure-Sentinel repo, Playbooks folder](https://github.com/Azure/Azure-Sentinel)

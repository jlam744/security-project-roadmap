# Security Engineering Project Ideas

Thirteen project briefs to build on my own, each tied to a skill security engineering hiring managers look for. Every brief lists the goal, milestones, deliverables and interview talking points. Check off milestones as I go.

## Projects

| # | Project | Area | Difficulty | Time | Cost | Lands in repo |
| --- | --- | --- | --- | --- | --- | --- |
| 01 | [Detection-as-Code pipeline](01-detection-as-code-pipeline.md) | Detection engineering | Advanced | 2 weeks | Free | `sentinel-detections` |
| 02 | [ATT&CK coverage map generator](02-attack-coverage-map.md) | Detection engineering | Intermediate | 3-4 days | Free | `sentinel-detections` |
| 03 | [Honeypot v2: from map to response](03-honeypot-v2.md) | Detection + automation | Intermediate | 1 week | Low (Azure) | `SentinelGeo_lab` |
| 04 | [Kerberoasting detection lab](04-kerberoasting-detection-lab.md) | Identity threats | Intermediate | 1 week | Free (local VMs) | `sentinel-detections` |
| 05 | [KC7 investigation series](05-kc7-investigation-series.md) | Investigation | Beginner to Advanced | 1 case per week | Free | `incident-casebook` |
| 06 | [Credential theft hunt on public data](06-credential-theft-hunt.md) | Threat hunting | Intermediate | 4-5 days | Free | `incident-casebook` |
| 07 | [Phishing email analyzer](07-phishing-email-analyzer.md) | Automation | Intermediate | 1 week | Free | `soc-automation` |
| 08 | [Sentinel enrichment playbook](08-sentinel-enrichment-playbook.md) | SOAR | Intermediate | 1 week | Low (Azure) | `soc-automation` |
| 09 | [AWS GuardDuty auto-containment](09-aws-guardduty-auto-containment.md) | Cloud IR | Advanced | 2 weeks | Low (AWS) | `aws-ir-lab` |
| 10 | [EC2 forensic acquisition tool](10-ec2-forensic-acquisition.md) | Cloud forensics | Advanced | 1 week | Low (AWS) | `aws-ir-lab` |
| 11 | [CloudGoat from the defender's side](11-cloudgoat-defender-writeups.md) | Cloud IR | Intermediate | 1 scenario per week | Low (AWS) | `aws-ir-lab` |
| 12 | [DLP detection tester](12-dlp-detection-tester.md) | Data protection | Intermediate | 4-5 days | Free | `dlp-purview-playbooks` |
| 13 | [Atrex AI Pentesting](13-atrex-ai-pentesting.md) | AI security / pentesting | Intermediate to Advanced | 5 sessions | Free (local VMs) | `Atrex-AI-Pentesting` |

Full week-by-week plan: [SCHEDULE.md](SCHEDULE.md)

## Suggested order

1. **Start here (quick wins):** 05, 02, 12
2. **Core engineering:** 04, 07, 03
3. **Cloud IR depth:** 09, 11, 10
4. **AI security:** 13
5. **Show-off pieces:** 01, 08, 06

## Rules for every project

- Lab or public data only. Nothing from any employer environment.
- No secrets in commits. Use `.env` files and keep them in `.gitignore`.
- Tear down cloud resources after each session and keep a billing alarm on.
- Every project ends with a README a stranger could follow, plus screenshots or sample output.

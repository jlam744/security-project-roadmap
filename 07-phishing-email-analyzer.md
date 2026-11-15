# Project 07: Phishing email analyzer

> **Target repo:** `soc-automation` | **Difficulty:** Intermediate | **Time:** 1 week | **Cost:** Free

## Goal

Build a Python command-line tool that takes a suspicious `.eml` file and produces a triage report: sender and reply-to mismatch, SPF/DKIM/DMARC results, the path the email took, every URL and attachment hash, and an overall risk score.

## Why hiring managers care

Phishing triage is one of the most common SOC tasks. Automating it shows you can turn analyst pain into a tool.

## Skills you'll show

- Python standard library `email` parsing
- Email authentication (SPF, DKIM, DMARC) and header analysis
- IOC extraction and hashing
- Building on your own tools (reuse `ioc_enrich.py`)

## Prerequisites

- Sample phishing emails from a public phishing sample collection, or emails you write yourself as test cases
- Never use real emails that contain other people's personal data

## Milestones

- [ ] Parse an `.eml` and print From, Reply-To, Return-Path, Subject, Date
- [ ] Extract and interpret the Authentication-Results header (SPF, DKIM, DMARC pass or fail)
- [ ] Rebuild the delivery path from the Received headers
- [ ] Extract every URL (plain text and HTML), defang them for safe sharing
- [ ] Hash every attachment (SHA-256) without opening it
- [ ] Score risk with clear, documented rules (for example Reply-To domain differs from From domain)
- [ ] Output a Markdown report and a JSON file
- [ ] Write tests with at least 3 sample emails (one clean, two malicious)

## Deliverables

- `phish_analyzer/` package with tests
- Sample reports in `samples/`
- README with usage, a sample report, and the scoring rules table

## Stretch goals

- Look up extracted URLs with urlscan.io and IPs with your IOC tool
- Detect lookalike domains (for example paypa1.com) with a simple similarity check

## Interview talking points

- What headers attackers can fake and which they can't
- Why DMARC alignment matters more than SPF passing
- How you'd plug this into a phishing report mailbox

## Resources

- Python `email` module documentation
- RFC 7489 (DMARC) overview

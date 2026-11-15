# Project 12: DLP detection tester

> **Target repo:** `dlp-purview-playbooks` | **Difficulty:** Intermediate | **Time:** 4-5 days | **Cost:** Free

## Goal

Build a Python tool that tests sensitive data detection patterns (credit card numbers, US Social Security numbers, and others) against a synthetic test set, and measures how many it catches and how many false alarms it raises. It's a small model of how DLP policies are tuned.

## Why hiring managers care

It turns your DLP experience into something concrete: you understand why DLP alerts are noisy and how pattern plus validation plus context reduces false positives.

## Skills you'll show

- Regular expressions and validation logic (for example the Luhn checksum for card numbers)
- Measuring detection quality: true positives, false positives, precision, recall
- Synthetic test data generation (Python Faker library). Never use real personal data

## Prerequisites

- Python 3, Faker
- Understanding of how DLP sensitive info types combine a pattern, validation and nearby keywords

## Milestones

- [ ] Generate a test set: documents with valid fake card numbers, invalid look-alikes (random 16-digit numbers, order numbers), fake SSNs, and harmless text
- [ ] Label every document with what it truly contains
- [ ] Detection level 1: regex only. Measure precision and recall
- [ ] Level 2: regex plus validation (Luhn for cards, invalid SSN ranges). Measure again
- [ ] Level 3: plus keyword context (for example "card", "exp", "SSN" within 50 characters). Measure again
- [ ] Present the results in a table and explain the tradeoff at each level

## Deliverables

- `dlp-tester/` with the generator, detectors and tests
- Results table and chart in the README
- A short write-up connecting results to real DLP policy tuning (no employer specifics)

## Stretch goals

- Add confidence levels (low, medium, high) like Purview sensitive info types
- Add a simple "instance count" threshold and show how it changes alert volume

## Interview talking points

- Why regex alone creates alert fatigue
- How you'd explain a precision vs recall tradeoff to a compliance team
- How this maps to what you saw tuning DLP policies in a real rollout

## Resources

- Microsoft Learn: sensitive information type entity definitions (to see how a vendor structures pattern, checksum and keywords)
- Python `re` module and Faker documentation

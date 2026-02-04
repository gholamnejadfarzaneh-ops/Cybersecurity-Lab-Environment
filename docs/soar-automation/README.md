# Security Domain: Automated Threat Intelligence

## Project Overview: SOAR Playbook for URL Triage
In a high-volume SOC environment, manual triage of suspicious URLs is a bottleneck. This project implements a Python-based **SOAR (Security Orchestration, Automation, and Response)** playbook that automates the enrichment phase of incident response.

## Technical Implementation
- **Tooling:** Python 3, Requests library.
- **Integrations:** VirusTotal API (v3).
- **Workflow:** 1. The script receives a suspicious URL.
  2. It performs an automated lookup via the VirusTotal API.
  3. It parses the JSON response to calculate a "Threat Score" based on engine detections.

## Security Impact
- **MTTR Reduction:** Significantly reduces the **Mean Time to Respond (MTTR)** by automating the initial data gathering.
- **Consistency:** Ensures every URL is checked against the same global threat intelligence database, removing human error.

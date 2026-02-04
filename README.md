# 🛡️ Cybersecurity Lab: Portfolio & Research

Welcome to my live security lab documentation. This repository tracks the technical implementation of my hardened server environment.

## 📂 Documentation Modules
* **[Automated Threat Intelligence (SOAR)](docs/soar-automation/README.md)**:SOAR Playbook for URL Triage
* **[Infrastructure & Hardening](docs/infrastructure-hardening/README.md)**: Details on T480 setup, Cloudflare Tunnels, and Linux security.
* **[Accountability & AAA Framework](docs/accountability-git/README.md)**: Documentation on Git digital signatures, non-repudiation, and audit trails.
* **[SOAR Automation](./soar-automation.html)**: Python logic for network threat detection.
* # Cybersecurity-Lab-Environment
# Project: Hardened Security Lab & Portfolio Node

## Overview
This project demonstrates the implementation of a secure web architecture hosted on a physical Linux node (Lenovo ThinkPad T480). The primary focus is **Infrastructure Security** and **Access Control**, utilizing Zero-Trust principles.

## Security Architecture


### 1. Edge Security & Zero Trust
- **Cloudflare Tunnels (Argo):** The server is not exposed via traditional port forwarding. All inbound traffic is routed through an encrypted outbound-only tunnel, effectively eliminating the local network's attack surface.
- **DDoS Protection:** Leveraging Cloudflare's edge network to mitigate volumetric attacks.

### 2. Host Hardening (Linux/Ubuntu)
- **Least Privilege:** Nginx and Git operations are performed by a non-root user to prevent privilege escalation.
- **Availability:** Configured `systemd-logind` to ensure high availability (HA) by maintaining server uptime during lid-closed (headless) operations.

### 3. Application Security (AppSec)
- **Directory Listing:** Disabled Nginx `autoindex` to prevent sensitive file exposure (CWE-16).
- **Automation:** Implemented a Python-based frequency analysis script to detect and alert on anomalous network traffic patterns (DoS detection).

## Technical Roadmap (In-Progress)
- [x] Linux Host Hardening & Zero Trust Implementation
- [ ] Active Directory (AD) Lab: Windows Server 2022 Implementation
- [ ] Identity & Access Management (IAM): GPO Hardening & Audit
- [ ] Centralized Logging: Prometheus & Grafana Integration
## System Administration Best Practices
Privilege Management: > Access to the /var/www/html directory was reconfigured from root:root to user:user. This mitigates the risk of Privilege Escalation vulnerabilities. By avoiding the use of the su (Switch User) command and utilizing sudo only when necessary, the lab adheres to the Principle of Least Privilege (PoLP).
#sudo chown -R user:user /var/www/html
Why? Normally, /var/www/html belongs to root. If you run Git as root, every file you create will also belong to root. This makes it very difficult to edit files later with your normal account. By taking ownership now, you make your workflow smooth and follow Best Practices for local development servers.


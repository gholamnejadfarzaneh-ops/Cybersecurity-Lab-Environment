# Security Domain: Infrastructure Hardening

## Overview
This module details the defensive configurations applied to the physical host (ThinkPad T480) and the web server (Nginx). The goal is to minimize the attack surface of the lab environment.

## Hardening Measures
### 1. Privilege De-escalation
- **Non-Root Ownership:** The web root directory (`/var/www/html`) was transitioned from `root` ownership to a standard user account. 
- **Impact:** This limits the potential for **Privilege Escalation** if the web server is compromised.

### 2. Host Configuration
- **Lid-Closed Operation:** Modified `systemd-logind` to prevent system suspension when the laptop lid is closed. 
- **Impact:** Ensures **Availability (High Availability)** for a "headless" server setup.

### 3. Edge Defense
- **Zero-Trust Tunnels:** Utilizing Cloudflare Tunnels to expose the portfolio. 
- **Impact:** No open inbound ports (e.g., Port 80/443) on the local router, effectively hiding the server from public IP scanners.

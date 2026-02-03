# Security Domain: Accountability & AAA Framework

## Overview
This module documents the implementation of the **AAA Framework** (Authentication, Authorization, and Accounting) within the development lifecycle of this lab. By enforcing these standards, I ensure that all infrastructure changes are tracked and authenticated.

## Technical Controls
### 1. Authentication & Authorization
- **Personal Access Tokens (PAT):** Access to the GitHub remote repository is secured via scoped tokens rather than traditional passwords. 
- **Scope Limitation:** The token is restricted to `repo` level access, adhering to the **Principle of Least Privilege (PoLP)**.

### 2. Accounting & Non-Repudiation
To ensure accountability, the local Git environment is configured with a unique digital signature. This ensures that every commit in the system audit log is tied to a verified identity.

```bash
# Configuration of the digital signature
git config --global user.email "...@gmail.com"
git config --global user.name "Farzaneh Gholamnejad"
## Troubleshooting: Authentication Failure Handling

During the Git integration phase, a `401 Unauthorized` error was encountered. This served as a practical exercise in **Authentication Failure Handling**.

### The "Handshake" Reset Protocol
If the connection between the local node and the remote repository becomes desynchronized or invalid, the following reset protocol is utilized to re-establish a secure link:

```bash
# 1. Terminate the existing remote link (the "handshake")
git remote remove origin

# 2. Re-establish the link using a Personal Access Token (PAT) for identity verification
git remote add origin https://<YOUR_TOKEN_HERE>@[github.com/gholamnejadfarzaneh-ops/Cybersecurity-Lab-Environment.git](https://github.com/gholamnejadfarzaneh-ops/Cybersecurity-Lab-Environment.git)

# 3. Synchronize the local 'main' branch with the remote repository
git push -u origin main

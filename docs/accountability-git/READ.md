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
git config --global user.email "gholamnedfazrzaneh@gmail.com"
git config --global user.name "Farzaneh Gholamnejad"

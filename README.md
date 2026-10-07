# Project-Sentinel-Security-as-Code-That-Finds-and-Fixes-Cloud-Misconfigurations-Automatically

## Scenario

> *This project is my implementation of a cloud security lab scenario created by The DevSec Blueprint. The organization and incident described below are fictional, but they're modeled on real-world cloud breach patterns.*

### The Situation

Aether Financial Services is a fast-growing digital bank that processes millions of transactions. Its engineering teams deploy thousands of cloud resources across multiple regions every day, far faster than manual security audits can keep up with.

### The Incident

That gap led to a breach involving two failures, neither of which was detected in time:

1. **Public data exposure:** a misconfigured storage bucket stayed publicly accessible for **three weeks**.
2. **Privilege abuse:** an over-privileged IAM role was used to **exfiltrate database snapshots**.

No alerts fired, and the security team found out only after the damage was done.

### The Problem

The underlying failure was the absence of any automated way to **detect** risky changes as they happen, **remediate** them without waiting for a human, and **record** every action for audit. At Aether's scale, a security model that relies on manual review will always be too slow.

### The Objective

The board has made it clear that the cloud environment must be able to defend itself.

I took on the role of Lead Cloud Security Engineer and built a Security as Code platform that automatically detects and remediates high-risk misconfigurations as they occur. Its design goals are:

| Goal | What It Means |
|------|---------------|
| **Self-healing** | High-risk misconfigurations are remediated automatically, without waiting for manual review |
| **Auditable** | Every detection and remediation action is logged and traceable |
| **Scalable** | Controls are deployed as code and apply consistently across every region and every new resource |
| **Secrets Management** | Secrets are not written in plaintext |

**Success criterion:** reduce the exposure window from **weeks to minutes**.

## Implementation


1. Create a monitored resource, an Azure storage account.
![Create a Storage Account](https://github.com/ZaneleLM/Assets/blob/main/Screenshot%202026-10-07%20091303.png)

2. Enable audit logging to capture all activity
![Enable audit logging](https://github.com/ZaneleLM/Assets/blob/main/Screenshot%202026-10-07%20092010.png)
![Enable audit logging](https://github.com/ZaneleLM/Assets/blob/main/Screenshot%202026-10-07%20092435.png)
![Enable audit logging](https://github.com/ZaneleLM/Assets/blob/main/Screenshot%202026-10-07%20092454.png)

3. Enable the Storage account to send logs to log analytics
![loganalytics](https://github.com/ZaneleLM/Assets/blob/main/Screenshot%202026-10-07%20100438.png)

4. 


   

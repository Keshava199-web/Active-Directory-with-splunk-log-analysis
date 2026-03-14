# Active-Directory & log analysis with Splunk

## Overview
This project demonstrates how **Splunk SIEM** can be used to monitor authentication activity across **Active Directory (Windows)** and **SSH services (Linux)** environments.

The goal of this project is to detect suspicious login behavior such as:

* *Brute-force login attempts*
* *Repeated failed authentication attempts*
* *Suspicious successful logins*
* *SSH reconnaissance activity*

Logs from different systems are collected and analyzed in **Splunk** using SPL queries, dashboards, and alerts to simulate a **Security Operations Center (SOC) monitoring workflow.**

## Lab Architecture
The following diagram shows the logical architecture of the lab environment used in this project.
### Requirement in the lab:

| Component               | Description                                   |
| ----------------------- | --------------------------------------------- |
| Windows Server          | Generates Windows authentication logs         |
| Active Directory Server | Manages domain authentication                 |
| Victim Machine          | Target system inside the network              |
| Attacker Machine        | Used to simulate attack activity              |
| Router                  | Connects internal network to external network |
| Layer 2 Switch          | Connects all systems in the internal network  |
| Splunk Server           | Collects and analyzes logs                    |
| Splunk Forwarder        | Forwards the logs from endpoint to Splunk Server | 

## Project Arch :
```
Windows Active Directory Logs
            │
            ▼
Linux SSH Authentication Logs
            │
            ▼
        Splunk SIEM
            │
            ▼
    Detection Queries (SPL)
            │
            ▼
     Dashboards & Alerts

```
Authentication logs from both Windows and Linux environments are centralized in Splunk SIEM, enabling unified log monitoring and security analysis.

### Network Flow

1. Windows Server and Active Directory Server generate authentication events.
2. Systems communicate through a Layer 2 switch.
3. The router connects internal network traffic to external access.
4. A victim machine acts as the monitored endpoint.
5. An attacker machine simulates suspicious login activity.
6. Logs are ingested into Splunk SIEM.
7. Splunk analyzes the logs using SPL detection queries.
8. Dashboards and alerts are used to visualize suspicious activity.

### Data Source
 **SSH Authentication Logs**
* *SSH authentication logs from Linux systems were ingested into Splunk in JSON format.*

Events included in the dataset:

* *Successful SSH Login*

* *Failed SSH Login*

* *Multiple Failed Authentication Attempts*

* *Connection Without Authentication*

* *Analyzing these logs helps detect brute-force attacks, scanning activity, and unusual login patterns.*











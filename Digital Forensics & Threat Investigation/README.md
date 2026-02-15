
# 🔍 Threat Intelligence & DFIR Lab
## Overview
This repository contains comprehensive forensic investigations and incident response reports. These projects simulate the role of a Tier 2/3 SOC Analyst and Forensic Examiner, focusing on evidence acquisition, artifact analysis, and threat attribution. I have mapped all findings to the MITRE ATT&CK framework to provide actionable intelligence for remediation.

## 🛠️ Technical Stack
**Forensic Tools:** FTK Imager, DeepBlueCLI, ExifTool, Browser History Viewer

**Analysis Platforms:** Wireshark, Splunk, CyberChef, SQLite DB Browser

**Log Analysis**: Apache Access Logs, Linux auth.log/wtmp, Zeek/Bro logs

**Environment:** Kali Linux, Windows Event Logs (.evtx), AD1 Logical Images

## 🕵️ Highlighted Investigations
### 1. RDP Compromise & Meterpreter Persistence
**Objective:** Investigated a Windows workstation compromise originating from an internet-facing RDP service.

**Analysis:** Used DeepBlueCLI to parse Security.evtx and System.evtx logs.

**Findings:** Identified the deployment of a Meterpreter payload and the creation of backdoor persistence mechanisms.

### 2. Chrome Extension Cryptominer (AD1 Image Analysis)
**Objective**: Analyzed an AD1 logical evidence image to investigate unauthorized browser activity.

**Analysis:** Mounted evidence via FTK Imager and used Browser History Viewer to correlate extension installation with CPU spikes.

**Findings:** Uncovered a malicious extension named "DFP Cryptocurrency Miner" running a CryptoLoot framework at 20 hashes/sec.

### 3. Apache Web Shell & phpBB Credential Theft
**Objective:** Reverse-engineered a credential theft incident leveraging server logs and SQLite database artifacts.

**Analysis:** Used grep/awk for log parsing and SQLite DB Browser to trace the escalation from a standard user to Admin.

**Findings:** Mapped the full lifecycle of a PHP web shell (fr34k.php) deployed via a vulnerable WordPress plugin.

### 4. Spearphishing Triage (CoCanDa Crisis)
**Objective:** Replicated a SOC phishing triage workflow to analyze a multi-stage cyber campaign.

**Analysis:** Analyzed email headers for spoofing, decoded Base64 payloads in CyberChef, and extracted metadata using ExifTool.

**Findings:** Attributed the attack to a specific C2 domain by correlating email routing anomalies and SPF/DKIM failures.

## 📡 Network Forensics & Exploit Analysis
**CVE-2022-25237 (BonitaSoft RCE):** Investigated a PCAP to confirm an Authorization Bypass leading to RCE. Identified Credential Stuffing attempts (T1110.004) and persistent SSH key injection.

**Zeek MD5 Enrichment:** Built a workflow to extract MD5 hashes from Zeek files.log and automate VirusTotal lookups via Python for rapid malware identification.

**SSH Brute Force:** Analyzed auth.log and wtmp to map an automated brute-force attack against the MITRE TTP for Valid Accounts.

## 🧠 Skills Demonstrated
**Evidence Integrity:** Understanding of Chain of Custody and working with forensic images (AD1, E01).

**Log Correlation:** Ability to pivot between Web Logs (Apache), System Logs (Windows/Linux), and Network Traffic (PCAP).

**Threat Attribution:** Using OSINT and CVE research to identify threat actor motivations and techniques.

**Incident Reporting:** Writing high-impact reports that translate technical "bits and bytes" into executive-level summaries.

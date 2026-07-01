# Investigation of a Remote Access Cyber Attack with Evidence Manipulation and False Flag Activity

## Project Overview

This project demonstrates a complete **Digital Forensics and Incident Response (DFIR)** investigation in a controlled Windows 11 virtual environment.

The objective was to simulate a real-world cyber attack, collect forensic evidence, and reconstruct the attack timeline using memory and disk forensic techniques.

The investigation covers:

- Initial compromise
- Remote access attack
- Privilege escalation
- Persistence
- Data theft
- False flag attack
- Anti-forensics
- Memory analysis
- Disk forensic analysis
- Evidence correlation

> **Note:** This project was performed entirely in an isolated virtual lab for educational and research purposes.


# Attack Scenario

The simulated attack followed a complete attack lifecycle.

The attacker:

- Created a malicious administrator account
- Disabled Windows security features
- Established remote access
- Executed a Meterpreter reverse shell
- Installed persistence
- Accessed confidential company files
- Simulated AI-assisted exam cheating
- Planted fake evidence to frame another user
- Deleted evidence and manipulated timestamps
- Attempted to hide all traces of the attack

The investigation successfully reconstructed every stage using forensic techniques.


# Objectives

- Simulate a realistic cyber attack
- Perform memory acquisition
- Create a forensic disk image
- Analyze RAM using Volatility
- Analyze disk artifacts using Magnet AXIOM
- Identify attacker activities
- Detect persistence mechanisms
- Reconstruct the attack timeline
- Demonstrate false flag investigation techniques


# Lab Environment

## Host Machine

- Kali Linux
- NAT Network

## Target Machine

- Windows 11 Virtual Machine
- NAT Network

# Tools Used

## Offensive Tools

- Metasploit Framework
- msfvenom
- Meterpreter
- Python HTTP Server
- AnyDesk

## Evidence Acquisition

- FTK Imager

## Memory Forensics

- Volatility 3

## Disk Forensics

- Magnet AXIOM

## Password Analysis

- PwDump
- John the Ripper
- Hashcat
- Mimikatz


# Attack Workflow

```
Initial Access
        │
        ▼
Reverse Shell
        │
        ▼
Privilege Escalation
        │
        ▼
Persistence
        │
        ▼
Remote Access
        │
        ▼
Data Theft
        │
        ▼
False Flag Attack
        │
        ▼
Anti-Forensics
        │
        ▼
Memory Acquisition
        │
        ▼
Disk Imaging
        │
        ▼
Forensic Investigation
```


# Attack Techniques Demonstrated

- Reverse TCP Meterpreter Payload
- Remote Administration
- Privilege Escalation
- Registry Persistence
- Credential Access
- Data Exfiltration
- Browser Artifact Generation
- False Flag Evidence Planting
- Timestamp Manipulation
- Anti-Forensics

# Memory Forensics

Memory analysis was performed using **Volatility 3**.

The investigation included:

- Operating system identification
- Running process analysis
- Hidden process detection
- Process tree reconstruction
- Network connection analysis
- DLL analysis
- Registry persistence detection
- Privilege analysis
- Shellcode detection
- Command history reconstruction

Evidence recovered included:

- Meterpreter payload
- Registry persistence
- Command and Control (C2) connections
- Malicious processes
- Injected DLLs
- Command history
- Privilege escalation evidence


# Disk Forensics

Disk images were acquired using **FTK Imager** and analyzed with **Magnet AXIOM**.

Recovered artifacts included:

- Browser History
- Search Queries
- Download History
- User Activity
- File Access
- Recent Files
- Prefetch Files
- Registry Artifacts
- Jump Lists
- LNK Files
- User Profiles


# Key Findings

The investigation successfully identified:

- Reverse shell payload execution
- AnyDesk remote access
- Registry persistence
- Meterpreter command-and-control communication
- Data theft activity
- Browser search history
- AI-assisted exam activity
- Evidence planting
- Anti-forensic activity
- Timestamp manipulation
# Ethics Statement

This project was conducted entirely in a controlled virtual environment for academic and learning purposes only. No real systems were targeted or harmed.


# Full Investigation Report

See project.pdf in this repository for the complete documented investigation including screenshots, commands, and analysis results.

# Pickle Rick — TryHackMe

**Platform:** TryHackMe  
**Difficulty:** Easy  
**OS:** Linux  
**Status:** Completed  
**Date:** November 6, 2026

[TryHackMe Room](https://tryhackme.com/room/picklerick)

## Overview

Linux penetration testing lab focused on reconnaissance, web enumeration, command execution and privilege management.

The machine was approached as a black-box assessment, starting with an unknown target and identifying its exposed services before investigating potential security weaknesses.

## Tools

- Nmap
- Gobuster
- curl
- Firefox
- Linux command-line utilities

## Topics Covered

**Network Reconnaissance**
- TCP port scanning
- Service and version detection
- Identification of exposed services

**Web Enumeration**
- HTTP response analysis
- Web content and directory discovery
- HTML source inspection
- Authentication mechanisms

**Linux Security**
- User and group enumeration
- File and directory permissions
- System enumeration
- Privilege escalation concepts
- Security misconfigurations

## Key Takeaways

- Service enumeration helps identify potential attack surfaces, but an exposed service is not necessarily vulnerable.
- Web applications can expose information beyond what is visible in the browser.
- Linux permissions determine which resources a process can access and modify.
- Incorrect privilege configurations can significantly increase the impact of an initial compromise.
- Understanding the underlying misconfiguration is as important as validating its impact.

## Result

**Room completed successfully.**

Detailed exploitation steps, credentials and challenge answers are intentionally excluded in accordance with TryHackMe's disclosure policy.
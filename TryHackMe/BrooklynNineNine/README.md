# Brooklyn Nine Nine — TryHackMe

**Platform:** TryHackMe  
**Difficulty:** Easy  
**OS:** Linux  
**Status:** Completed  
**Date:** November 8, 2026

[TryHackMe Room](https://tryhackme.com/room/brooklynninenine)

## Overview

Linux penetration testing lab covering network reconnaissance, service enumeration, credential security, file analysis and local privilege management.

I approached the machine as a black-box target, investigated the exposed services and worked through the findings to complete both user- and root-level objectives.

## Tools

- Nmap
- FTP client
- Firefox
- Steghide and StegSeek
- SSH
- Nano and Linux command-line utilities
- Kali Linux (Distrobox)

## Topics Covered

**Network and Service Enumeration**
- TCP port scanning and version detection
- FTP authentication and file access
- Understanding active and passive FTP connections
- HTTP source inspection

**File and Credential Security**
- JPEG metadata and steganography concepts
- Offline wordlist-based password testing
- Credential exposure and authentication risks

**Linux Security**
- User and group identification
- File permissions and absolute paths
- Sudo rules and least privilege
- Privileged applications and command execution

## Key Takeaways

- Service banners and exposed files can provide valuable context, but they do not automatically imply a vulnerability.
- FTP uses separate control and data connections, which can behave differently across a VPN.
- Hidden or encrypted data is only as well protected as its passphrase and the security of the embedding method.
- An overly permissive sudo rule can make an otherwise ordinary program a serious security risk.
- Troubleshooting the testing environment is part of the process: understanding an error matters more than blindly switching tools.

## Result

**Room completed successfully — user and root objectives achieved.**

Detailed exploitation steps, credentials and challenge answers are intentionally excluded in accordance with TryHackMe's disclosure policy.

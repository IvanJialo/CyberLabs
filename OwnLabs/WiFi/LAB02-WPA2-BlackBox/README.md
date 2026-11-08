# LAB02 — WPA2 Black-Box Security Audit

**Category:** Wireless Security  
**Environment:** Authorized WPA2-Personal hotspot  
**Status:** Completed  
**Type:** Black-box password security assessment

## Objective

Assess the resistance of a WPA2-Personal network to offline password recovery without prior knowledge of the network password.

Unlike LAB01, where the password structure was known, this assessment was performed under black-box conditions.

The goal was to capture valid authentication material and evaluate whether the password could be recovered using common wordlists and candidate-generation techniques within a limited testing window.

## Environment & Tools

- Linux
- Aircrack-ng suite
- airodump-ng
- aireplay-ng
- hcxpcapngtool
- Hashcat
- GPU for offline password recovery

## Methodology

### 1. Network Reconnaissance

Identified the authorized test access point, operating channel and associated client.

Verified the target network and prepared the wireless interface for monitor-mode traffic capture.

### 2. Handshake Capture

Monitored authentication traffic using airodump-ng.

A targeted deauthentication test was performed against an authorized client to trigger reconnection and capture a WPA2 EAPOL handshake.

The resulting capture was checked before proceeding with offline analysis.

### 3. Capture Processing

Converted the captured authentication data into Hashcat's `22000` format using hcxpcapngtool.

This allowed password candidates to be tested offline without sending authentication attempts to the access point.

### 4. Password Recovery Attempts

Several approaches were tested using Hashcat:

- Dictionary attack using RockYou.
- Rule-based candidate generation using best66.
- Hybrid attempts combining dictionary entries with additional candidate patterns.

The available testing window was approximately 40 minutes.

None of the tested approaches recovered the network password.

## Results

**Handshake capture:** Successful  
**Offline password recovery:** Unsuccessful  
**Testing window:** Approximately 40 minutes

The capture provided valid authentication material for offline testing, but the tested candidate sets did not contain a matching password.

This does not prove that the password is impossible to recover. It only establishes that recovery was unsuccessful under the tested conditions, candidate-generation strategies and time constraints.

## Security Considerations

- WPA2-Personal passwords can be tested offline once suitable authentication material has been captured.
- The effectiveness of an offline attack depends on the candidate space, password predictability and available computing resources.
- Dictionary and rule-based attacks are limited by the words and transformations they generate.
- Deauthentication-based capture techniques depend on the network and client configuration. Protected Management Frames can restrict these attacks when properly enforced.
- A failed recovery attempt should not automatically be interpreted as proof of strong password security.

## Conclusion

This lab provided practical experience with black-box wireless reconnaissance, targeted deauthentication, WPA2 handshake capture and offline password auditing.

Compared with LAB01, the main difference was the lack of prior knowledge about the password structure.

The password was not recovered within the available testing window, illustrating the limitations of dictionary-based and hybrid recovery strategies.

## Disclosure

The assessment was performed against an authorized test network.

Original captures, hashes, wireless identifiers, client information and password-related data are excluded from this public report.
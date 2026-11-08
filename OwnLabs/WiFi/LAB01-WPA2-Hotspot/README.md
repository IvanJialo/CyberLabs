# LAB01 — WPA2 Hotspot Security Audit

**Category:** Wireless Security  
**Environment:** Personal WPA2 hotspot  
**Status:** Completed  
**Type:** Controlled security assessment

## Objective

Evaluate the security of a WPA2-Personal network by capturing an authentication handshake and testing the resistance of a known-format password against an offline dictionary/mask-based attack.

The experiment was performed using my own hotspot and an authorized client device.

## Environment & Tools

- Linux
- Aircrack-ng suite
- airodump-ng
- hcxpcapngtool
- Hashcat
- GPU for offline password recovery

## Methodology

### 1. Network Reconnaissance

Identified the test access point, its operating channel and the associated client.

Verified that the network was using WPA2-Personal before proceeding with the capture.

### 2. Handshake Capture

Configured the wireless adapter in monitor mode and captured the WPA2 authentication exchange using airodump-ng.

The capture was obtained during a client connection. No deauthentication attack was required.

### 3. Capture Processing

Converted the capture into Hashcat's `22000` format using hcxpcapngtool.

This allowed the captured authentication data to be used for offline password verification.

### 4. Password Recovery

Performed an offline password recovery test using Hashcat.

The attack used a mask based on the known structure of the laboratory password, reducing the number of candidates that needed to be tested.

The test password was successfully recovered.

## Results

**Password recovery: Successful**

The experiment confirmed that a valid WPA2 authentication capture can be used to verify password candidates offline.

The recovery was possible because the test password followed a predictable structure. This result does not imply that WPA2 encryption itself was broken.

## Security Considerations

- Capturing a WPA2 handshake does not directly reveal the plaintext password.
- Offline recovery depends heavily on password strength, predictability and available computing resources.
- A long, randomly generated password significantly increases the difficulty of this type of attack.
- WPA3-Personal provides additional protection against passive offline dictionary attacks when properly implemented.

## Conclusion

This lab provided practical experience with wireless reconnaissance, monitor mode, WPA2 authentication captures and GPU-based password recovery.

It also demonstrated the importance of password predictability and the difference between capturing authentication material and actually recovering a network password.

## Disclosure

All tests were performed against a personally controlled network with authorization.

Original packet captures, hashes, network identifiers and the recovered password are intentionally excluded from this public report.
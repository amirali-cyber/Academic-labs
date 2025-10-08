#  Wireshark: TCP Three-Way Handshake & SYN-Flood (Lab)

**Date:** 2025-10  
**Source:** University lab  
**Objective:** Capture the TCP three-way handshake between Kali and Metasploitable, then observe the effect of a simulated SYN flood in a controlled lab environment.

---

## Short summary
This lab demonstrates two complementary exercises in a safe VM lab:
1. Capture and inspect the **TCP three-way handshake** (SYN → SYN/ACK → ACK) between a Kali machine and a Metasploitable target.  
2. Observe how a simulated **SYN-flood** (lab-only) increases SYN traffic and affects normal handshake behaviour.

All activity was performed in isolated virtual machines (Kali and Metasploitable) using the lab environment. No public or production systems were targeted.

---

## Steps performed
1. Booted Kali and Metasploitable VMs and confirmed network interfaces. (See `metasploitable-ifconfig-redacted.png`.)  
2. Started Wireshark on Kali and began a capture on the relevant interface.  
3. Opened a web browser on Kali and navigated to the Metasploitable IP to generate a normal TCP handshake.  
4. Applied a Wireshark display filter to show the initial SYN packets:
tcp.flags.ack == 0 && tcp.flags.syn == 1 && tcp.seq == 0

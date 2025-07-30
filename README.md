
# 🛡️ Deception Lab — Cybersecurity Honeypot Deployments

This project showcases the installation, configuration, and testing of multiple open-source deception technologies (honeypots) designed to detect, log, and analyze unauthorized or malicious activity across a network.

It includes detailed, hands-on labs for:

- 🐍 [Dionaea](./Dionaea/setup.md) — malware collection honeypot
- 🕵️ [Cowrie](./Cowrie/setup.md) — SSH/telnet honeypot
- 🧪 [OpenCanary](./OpenCanary/setup.md) — multi-protocol honeypot
- 🪤 [CanaryTokens](./CanaryTokens/usage.md) — honeytokens (file-based traps)

---

##  Purpose

The goal of this lab is to simulate real-world cyberattacks in a controlled environment and use deception tools to:

- Capture attacker behavior and payloads
- Log brute-force attempts, file access, and protocol scans
- Generate threat intelligence artifacts (IP addresses, commands, malware)

---

##  Technologies Used

- Ubuntu Server 20.04 (for Dionaea and OpenCanary)
- Kali Linux (as attacker environment)
- Docker (for Cowrie)
- Canarytokens.org
- Tools: `nmap`, `ftp`, `curl`, `ssh`, `hydra`, `smbmap`

---

##  Structure

Each honeypot includes:

- `setup.md` — Installation guide
- `configuration.md` — Customization and setup
- `testing.md` — Simulated attack procedures and log review

>  Start with [navigation.md](./navigation.md) for a quick index of all sections.

Thank you for your interest in cybersecurity !
---

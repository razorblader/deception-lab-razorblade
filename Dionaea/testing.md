#  Dionaea — Testing

This section walks through several attack simulations against Dionaea using Kali Linux tools to verify its functionality. We'll test emulated services like FTP, HTTP, SMB, MySQL, and SIP, and review how Dionaea logs the interactions.

---

##  Port Scanning with Nmap

Use `nmap` to detect open ports on the honeypot:

```bash
nmap -sV <DIONAEA-IP>
```

Expected result: nmap should detect several fake services exposed by Dionaea (FTP, HTTP, SMB, etc.).

# Real-Time Log Monitoring
Dionaea logs are located in:
```bash
/opt/dionaea/var/log/dionaea/dionaea.log
```
To monitor logs live, you can use:
```bash
sudo tail -f /opt/dionaea/var/log/dionaea/dionaea.log
```
# FTP Upload Simulation
From Kali, upload a test file (e.g., fakemalware.exe) to the FTP service:
```bash
ftp <DIONAEA-IP>
# Login anonymously, then:
put fakemalware.exe
```
Search for file capture confirmation:
```bash
sudo grep download.complete /opt/dionaea/var/log/dionaea/dionaea.log
```
Check the saved file under:
```bash
ls /opt/dionaea/var/lib/dionaea/ftp/root/
```
# HTTP File Hosting Test
Move a test file to the HTTP root:
```bash
sudo cp fakefile.exe /opt/dionaea/var/lib/dionaea/http/root/
```
From Kali, request the file:
```bash
curl http://<DIONAEA-IP>/fakefile.exe
```
the, check logs for HTTP access records.
# SMB Enumeration
List shared resources with smbclient:

```bash
smbclient -L <DIONAEA-IP> -N
```
Use smbmap to probe:
```bash
smbmap -H <DIONAEA-IP>
```
Dionaea will simulate valid SMB responses and log each interaction.

# MySQL Brute-Force Simulation
From Kali, simulate a password attack using hydra:
```bash
hydra -l root -P /usr/share/wordlists/rockyou.txt mysql://<DIONAEA-IP>
```
The login attempts will be logged in real time.

You can try to enable other services and try tests with any tool you want! 
Thank you for interest in cybersecurity :D

Continue to [Cowrie lab](../Cowrie/setup.md)









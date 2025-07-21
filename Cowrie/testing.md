#  Cowrie — Testing

This section walks through how to simulate attacks against Cowrie's fake SSH service and observe how it captures attacker behavior.

---

## Simulated SSH Access

From your attacker machine (e.g., Kali Linux), attempt to connect to Cowrie:
Let’s delete any other previous ssh known_hosts connections to the honeypot first to avoid erros:
```bash
rm .ssh/known_hosts
```
```bash
ssh root@<COWRIE-IP> -p 2222
```
Let’s delete any other previous ssh known_hosts connections to the honeypot

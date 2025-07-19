#  Cowrie — Setup

Cowrie is a medium-interaction honeypot that emulates SSH and Telnet services to capture attacker behavior. This section covers installing Cowrie via Docker for quick deployment.

---

## Requirements

- Host OS: Kali Linux (or any modern Linux distro)
- Docker installed and running
- Internet access

---

##  Install Cowrie via Docker

Run the following command to download and start the Cowrie container:

```bash
docker run -p 2222:2222/tcp cowrie/cowrie
```
This exposes Cowrie’s fake SSH service on port 2222 of your host.
# Verify the Container is Running
Check the container status:
```bash
docker ps
```
You should see the cowrie/cowrie container listed and active.
Now you are ready to test it, but if you want to custom some features go to: [Configuration](./configuration.md)

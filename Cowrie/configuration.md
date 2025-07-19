# Cowrie — Configuration

This section explains how to locate and edit Cowrie's configuration files when running it via Docker, so you can customize banners, hostname, and logging behavior.

---

##  Locate the Configuration File

Cowrie's configuration file is typically named `cowrie.cfg.dist`.

Use the following command to search for it inside your Docker container:

```bash
sudo find / -name "cowrie.cfg.dist" 2>/dev/null
```
The path may look something like this (Docker overlay path):
```bash
/var/lib/docker/overlay2/<container_id>/diff/cowrie/cowrie-git/etc/cowrie.cfg.dist
```
# Edit the Configuration
Open the file using a text editor (vim or nano, nano if you are a not a weirdo): 
```bash
sudo nano /var/lib/docker/overlay2/<container_id>/diff/cowrie/cowrie-git/etc/cowrie.cfg.dist
```
# Example Customization
To change the hostname that appears to attackers when they connect:
```bash
# Original
hostname = svr04

# Custom
hostname = not_a_trap_lol
```
Save and exit the file.
Restart Cowrie.
```bash
docker restart <container_id>
```
Logs and fake terminal behavior should now reflect the updated configuration.
Continue to: [Testing](./testing.md)

#  Dionaea — Configuration

This section describes how to configure Dionaea after installation, including enabling/disabling services and setting it up to run as a background service using `systemd`.

---

##  Important Configuration Directories

Located in `/opt/dionaea/etc/dionaea/`:

- `services-available/`: contains all available protocol emulation configs
- `services-enabled/`: symbolic links to active services
- `ihandlers-available/`: available malware handling plugins
- `ihandlers-enabled/`: active malware handlers (also via symlinks)

---

##  Disable Unwanted Services

Remove unnecessary service links (optional but recommended for testing):

```bash
cd /opt/dionaea/etc/dionaea/services-enabled

sudo rm blackhole.yaml epmap.yaml ftp.yaml memcache.yaml mirror.yaml mongo.yaml \
mqtt.yaml mssql.yaml pptp.yaml sip.yaml tftp.yaml upnp.yaml printer.yaml
```
# Create a systemd Service
To run Dionaea in the background and enable it on startup, create a systemd unit file:
```bash
sudo nano /etc/systemd/system/dionaea.service
```
Paste the following configuration:
```bash
[Unit]
Description=Run Dionaea Honeypot
After=network.target

[Service]
ExecStart=/opt/dionaea/bin/dionaea

[Install]
WantedBy=multi-user.target
```

# Enable and Start the Service 
Reload services and start Dionaea:

```bash
sudo systemctl daemon-reexec
sudo systemctl enable dionaea
sudo systemctl start dionaea
```
To verify that it’s running:
```bash
sudo systemctl status dionaea
```
Now needed configuration is done Dionaea is ready for [Testing](./Dionaea/testing.md)


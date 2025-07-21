# OpenCanary - configuration
This section explains how to generate a configuration file, edit it and run OpenCanary

---
# Generate default config file
To generate a config file, please run:
```bash:
opencanaryd --copyconfig
```
Once created, to modify some features and allow the services to run please go to:
```bash
sudo nano /etc/opencanaryd/opencanary.conf
```
Inside the file, adjust the features you want, or allow them to run or not, by defining its state to "true" or "false".
Save the file and now to run the honeypot, please type:
```bash
/root/opencanary-env/bin/opencanaryd –start
```
Now configuration is done and ready to go, now you can continue to: [Testing](./testing.md)

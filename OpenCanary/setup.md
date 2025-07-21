# OpenCanary - setup
this guide explains how to install and build the OpenCanary honeypot on a clean Ubuntu Server 20.04 system.

--- 
#  Requirements

- Ubuntu Server 20.04
- 8 GB of available storage
- Virtual machine recommended
- Internet access for downloading dependencies

  
  ---
# System Preparation.

Update packages and confirm Python 3 is installed:

```bash
sudo apt update
sudo apt -y upgrade
python3 --version
```
Now, create a virtual ennvironment.
```bash
virtualenv env
. env/bin/activate
```
Once inside the virtual env, run:
```bash
sudo apt-get install python3-dev python3-pip python3-virtualenv python3-venv python3-scapy libssl-dev libpcap-dev

virtualenv env/

. env/bin/activate

pip install opencanary
```
If you want to also use the “Windows File Share” or SNMP modules, please run:
```bash
sudo apt install samba # if you plan to use the Windows File Share module
pip install scapy pcapy-ng # if you plan to use the SNMP module
```
With this setup is done and all needed resources are redy to go!
Now please continue to: [Configuration](./configuration.md)

# 🐍 Dionaea — Setup

This guide explains how to install and build the Dionaea honeypot on a clean Ubuntu Server 20.04 system.

---

## 📋 Requirements

- Ubuntu Server 20.04
- 8 GB of available storage
- Virtual machine recommended
- Internet access for downloading dependencies

---

## ⚙️ System Preparation

Update packages and confirm Python 3 is installed:

```bash
sudo apt update
sudo apt -y upgrade
python3 --version
```
📥 Clone Dionaea Source
```bash
cd ~
git clone https://github.com/DinoTools/dionaea.git
cd dionaea
```
📦 Install libemu (Manual Install)
Ubuntu 20.04 doesn't include this package by default. You must download and install manually:
```bash
cd ~/Downloads

wget http://archive.ubuntu.com/ubuntu/pool/universe/libe/libemu/libemu2_0.2.0+git20120122-1.2build1_amd64.deb \
     http://archive.ubuntu.com/ubuntu/pool/universe/libe/libemu/libemu-dev_0.2.0+git20120122-1.2build1_amd64.deb

sudo apt install ./libemu2_*.deb ./libemu-dev_*.deb
```
📚 Install Dependencies
```bash
sudo apt-get install \
  build-essential \
  cmake \
  check \
  cython3 \
  libcurl4-openssl-dev \
  libemu-dev \
  libev-dev \
  libglib2.0-dev \
  libloudmouth1-dev \
  libnetfilter-queue-dev \
  libnl-3-dev \
  libpcap-dev \
  libssl-dev \
  libtool \
  libudns-dev \
  python3 \
  python3-dev \
  python3-bson \
  python3-yaml \
  python3-boto3 \
  fonts-liberation
```
🔨 Build and Install Dionaea
```bash
sudo mkdir build
cd build
sudo cmake -DCMAKE_INSTALL_PREFIX:PATH=/opt/dionaea ..
sudo make
sudo make install
```
✅ Dionaea will be installed to: /opt/dionaea
🧪 Verify Installation
Test whether Dionaea runs:
```bash
/opt/dionaea/bin/dionaea -vv
```


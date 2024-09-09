# Packet-Tracer-Dependencies
>"dpkg: error processing package packettracer (--install):  dependency problems - leaving unconfigured"

---
### When you run:

```bash
sudo dpkg -i CiscoPacketTracer82*.deb
```
---
### You might get this error:
---

 (Reading database ... 661127 files and directories currently installed.)
 Preparing to unpack CiscoPacketTracer822_amd64_signed.deb ...
Unpacking packettracer (8.2.2) over (8.2.2) ...
Warning: program compiled against libxml 212 using older 209
gtk-update-icon-cache: Cache file created successfully.
dpkg: dependency problems prevent configuration of packettracer:
 packettracer depends on dialog; however:
  Package dialog is not installed.
 packettracer depends on libgl1-mesa-glx; however:
  Package libgl1-mesa-glx is not installed.
 packettracer depends on libxcb-xinerama0-dev; however:
  Package libxcb-xinerama0-dev is not installed.

dpkg: error processing package packettracer (--install):
 dependency problems - leaving unconfigured
Processing triggers for gnome-icon-theme (3.12.0-5) ...
Processing triggers for shared-mime-info (2.4-5) ...
Warning: program compiled against libxml 212 using older 209
Errors were encountered while processing:
 packettracer

---

> FYI: Kali is a rolling distribution based in Debian & tracks the latest updates. 
The actual Kali have a "mesa 23.3.5-1" and therefore there's no binary package "libgl1-mesa-glx".
Because "mesa" last use of binary package "libgl1-mesa-glx" was in "mesa 23.2.1-1".

___

# To solve Error, try to use apt to fix install.

---

```bash
sudo apt --fix-broken install
```

```bash
sudo apt-get install
```

---

## If the Error persists, download packages manually (at your own risk)

  Go to https://pkgs.org/ find & download the necessary packages,

  In this case:
    http://ftp.de.debian.org/debian/pool/main/m/mesa/libgl1-mesa-glx_22.3.6-1+deb12u1_amd64.deb
    http://ftp.de.debian.org/debian/pool/main/libx/libxcb/libxcb-xinerama0-dev_1.15-1_amd64.deb

---

### Install packages manually 

```bash
sudo dpkg -i libgl1-mesa-glx_22.3.6-1+deb12u1_amd64.deb
```

```bash
sudo dpkg -i libxcb-xinerama0-dev_1.15-1_amd64.deb 
```

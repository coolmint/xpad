# Updated Xpad Linux Kernel Driver
Driver for the Xbox/ Xbox 360/ Xbox 360 Wireless/ Xbox One Controllers

## Changes compared to Linux Staging
* fixed blinking LED on Xbox 360 Wireless Controllers (based on [SteamOS Version](https://github.com/ValveSoftware/steamos_kernel/commit/d92cfaac03183c01382bde7e817d22e4ea9078d5))
* fixed kernel panics due to URB request races ([patch by Sarah Bessmer](https://www.marc.info/?l=linux-input&m=140023068527280&w=2))
* merged Xbox One controller force feedback (again from SteamOS)

# Installation
```
sudo git clone https://github.com/paroj/xpad.git /usr/src/xpad-0.4
sudo dkms install -m xpad -v 0.4
```
# Updating
```
cd /usr/src/xpad-0.4
sudo git fetch
sudo git checkout origin/master
sudo dkms remove -m xpad -v 0.4 --all
sudo dkms install -m xpad -v 0.4
```

# Sending Upstream

1. `git format-patch --cover-letter staging..master`
2. `git send-email --to xxx *.patch`

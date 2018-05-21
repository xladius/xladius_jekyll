---
layout: post
title:  "Using Yubikey as openPGP smart cards"
date:   2018-05-21 10:53:41 +0800
categories: update
---

```bash
echo 'KERNEL=="hidraw*", SUBSYSTEM=="hidraw", MODE="0664", GROUP="users", ATTRS{idVendor}=="2581", ATTRS{idProduct}=="f1d0"' | sudo tee /etc/udev/rules.d/10-security-key.rules
```

In order for your YubiKey to be a U2F device and behave as a GPG card, you need to put the card into a mode called 'super combo mode'.

On Arch Linux, I installed yubikey-personalization and set the 'super combo mode' (86) like this:

```bash
pacman -S yubikey-personalization
ykpersonalize -m 86
```




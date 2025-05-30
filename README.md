# Instantnoodle Device + Hardware + Kernel Tree

This repository contains the complete **device tree, hardware, and kernel sources** for the OnePlus 8 (`instantnoodle`) – suitable for custom AOSP or LineageOS ROM development.

## 📂 Included Sources

```
device/oneplus/instantnoodle
device/oneplus/sm8250-common
kernel/oneplus/sm8250
hardware/oplus
```

## 📥 How to Clone

Clone this repository into your AOSP working directory:

```bash
git clone https://github.com/dmmartin/instantnoodle-device-hardware-kernel.git
```

This will provide:
- Device-specific files for OnePlus 8
- Common SM8250 device tree
- Kernel source for SM8250
- Required `hardware/oplus` components

---

## 📦 Vendor Blobs (Proprietary)

Since this repo does **not** contain proprietary vendor blobs, please download them separately:

🔗 [Vendor Blobs - Mega Link](https://mega.nz/file/hZxzhRKQ#LOdLHH1dp64XoD7GztBYnpC4vNygiHbWTIHAoyjy5C8)

After downloading, extract the contents into your working folder under `vendor/oneplus/`.

---

## 💡 Notes

- This tree was tested on AOSP-based ROMs like LineageOS and crDroid.
- The goal is to provide a clean, buildable starting point for custom ROM development on OnePlus 8.
- Contributions welcome if you'd like to improve or update this setup!

---

## 🧠 Maintainer

**Denis Martin**  
🔧 ROM builder, Fedora lover, and smartass sudo whisperer 😄  

> 💬 _"Don't give me beer... I don't need it like some scavengers do."_  
> 💡 All proprietary blobs belong to **OnePlus**.  
> 📦 This device tree and related code are adapted from **LineageOS**,  
> not from *some Indian guy asking for beer donations* in exchange for his crDroid OnePlus ROM `.zip`.

---

## 👥 Credits


[![LineageOS](https://raw.githubusercontent.com/LineageOS/branding/master/logo/lineage-logo.png)](https://lineageos.org)


This project is based on sources provided by:


**LineageOS**  
Website: [https://lineageos.org](https://lineageos.org)  
Branding: [https://github.com/LineageOS/branding](https://github.com/LineageOS/branding)

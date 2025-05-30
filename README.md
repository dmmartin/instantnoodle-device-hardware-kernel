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

Clone this repository into a temporary folder if you're using `repo sync`, or merge carefully:

```bash
git clone https://github.com/dmmartin/instantnoodle-device-hardware-kernel.git ~/temp-noodle
```

Then manually copy the required folders into your AOSP source tree:

```bash
cp -r ~/temp-noodle/device/* aosp/device/
cp -r ~/temp-noodle/kernel/* aosp/kernel/
cp -r ~/temp-noodle/hardware/* aosp/hardware/
```

---

### ⚠️ Avoiding Conflict with `repo sync`

If you directly clone into `aosp/`:

```bash
git clone https://github.com/dmmartin/instantnoodle-device-hardware-kernel.git aosp/
```

…it will create:

```
aosp/device/
aosp/kernel/
aosp/hardware/
```

This may **conflict with `repo sync`** if the same folders are defined in your manifest.

#### ✅ Recommended:
- Use `local_manifests` for safe integration
- Or manually copy the tree into your source folder as shown above

---

## 📦 Vendor Blobs (Proprietary)

Since this repo does **not** contain proprietary vendor blobs, please download them separately:

🔗 [Vendor Blobs - Mega Link](https://mega.nz/file/hZxzhRKQ#LOdLHH1dp64XoD7GztBYnpC4vNygiHbWTIHAoyjy5C8)

After downloading, extract the contents into your working folder under:

```
vendor/oneplus/
├── sm8250-common/
├── instantnoodle/  ← (if required by your ROM tree setup)
```

⚠️ **Note**: This repository does not include `vendor/oneplus/instantnoodle` — only `sm8250-common`.  
You may need to regenerate or adapt the `instantnoodle` vendor tree using `extract-files.py` or pull from a known ROM base.

---

## 🔧 Setup Instructions

After copying the device tree into `device/oneplus/instantnoodle`, run the following:

```bash
cd device/oneplus/instantnoodle
./setup-makefiles.py
```

This script regenerates key files like `Android.mk`, `Android.bp`, and `BoardConfigVendor.mk`, ensuring they match your current `proprietary-files.txt` list and vendor blob setup.

⚠️ This is **essential**, because after copying the tree, it may contain **broken or stale references** to `vendor/oneplus/instantnoodle` blobs.  
Running this script will:
- Re-link or clean up proprietary file references
- Prevent build errors from missing or mismatched vendor blobs
- Make your tree ready for `brunch` or `lunch` builds

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

This project is based on sources and guidance provided by:

[![LineageOS](https://raw.githubusercontent.com/LineageOS/branding/master/logo/lineage-logo.png)](https://lineageos.org)

**LineageOS**  
Website: [https://lineageos.org](https://lineageos.org)  
Branding: [https://github.com/LineageOS/branding](https://github.com/LineageOS/branding)

🤖 **ChatGPT (by OpenAI)** – For guidance, writing help, and motivational tech banter along the way.

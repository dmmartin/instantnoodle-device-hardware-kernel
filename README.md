# OnePlus 8 Device Tree Pack

This repository contains the **device tree, hardware, and kernel sources** for the OnePlus 8 (`instantnoodle`) – suitable for LineageOS ROM android 15 building

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
git clone https://github.com/dmmartin/oneplus8-device-tree-pack.git ~/temp-noodle
```

Then manually copy the required folders into your source tree:

```bash
cp -r ~/temp-noodle/device/* lineage/device/
cp -r ~/temp-noodle/kernel/* lineage/kernel/
cp -r ~/temp-noodle/hardware/* lineage/hardware/
```

---

### ⚠️ Avoiding Conflict with `repo sync`

If you directly clone into `lineage/`:

```bash
git clone https://github.com/dmmartin/oneplus8-device-tree-pack.git lineage/
```

…it will create:

```
lineage/device/
lineage/kernel/
lineage/hardware/
```

This may **conflict with `repo sync`** if the same folders are defined in your manifest.

#### ✅ Recommended:
- Use `local_manifests` for safe integration
- Or manually copy the tree into your source folder as shown above



## 📦 Vendor Blobs (Proprietary)

This repository does **not** include proprietary blobs due to licensing restrictions, but you can download a **complete vendor tree** separately:

🔗 [Vendor Blobs - Mega Link](https://mega.nz/file/hZxzhRKQ#LOdLHH1dp64XoD7GztBYnpC4vNygiHbWTIHAoyjy5C8)

After downloading and extracting, the vendor directory structure should look like:

```
vendor/oneplus/instantnoodle
vendor/oneplus/sm8250-common
```
```
vendor/
└── oneplus
    ├── instantnoodle
    │   ├── Android.bp
    │   ├── Android.mk
    │   ├── BoardConfigVendor.mk
    │   ├── instantnoodle-vendor.mk
    │   ├── proprietary/
    │   └── radio/
    └── sm8250-common
        ├── Android.bp
        ├── Android.mk
        ├── BoardConfigVendor.mk
        ├── proprietary/
        └── sm8250-common-vendor.mk
```
✅ Copy this into the corresponding directory, this will ***complete*** your instantnoodle source tree.
---

### 🔧 `setup-makefiles.py`

After placing the vendor blobs in `vendor/oneplus/`, run:

```bash
cd device/oneplus/instantnoodle
./setup-makefiles.py
```

Even though the extracted vendor tree already includes the necessary `*.mk` and `Android.bp` files, this script ensures:

- Any broken/missing proprietary references are regenerated
- New `.mk` or `.bp` files get created if absent
- Your device tree is synced with the proprietary blob lists

---

## 💡 Notes

- This tree was tested on AOSP-based ROMs like LineageOS and crDroid.
- The goal is to provide a clean, buildable starting point for custom ROM development on OnePlus 8.
- Contributions welcome if you'd like to improve or update this setup!

---

## 🧠 I am not the OFFICIAL Maintainer of Instantnoodle

**dmm**  
🔧 ROM builder wannabe...  

> 💡 All proprietary blobs belong to **OnePlus**.  
> 📦 This device tree and related code are adapted from **LineageOS**,  

---

## 👥 Credits

This project is based on sources and guidance provided by:

[![LineageOS](https://raw.githubusercontent.com/LineageOS/branding/master/logo/lineage-logo.png)](https://lineageos.org)

**LineageOS**  
Website: [https://lineageos.org](https://lineageos.org)  
Branding: [https://github.com/LineageOS/branding](https://github.com/LineageOS/branding)

🤖 **ChatGPT (by OpenAI)** – For guidance, writing help, and motivational tech banter along the way.

---

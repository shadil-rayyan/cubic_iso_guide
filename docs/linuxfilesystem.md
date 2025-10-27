

# 🌐 Linux Filesystem Overview for Custom ISO Creation

When creating a **custom Ubuntu ISO** using Cubic, it’s essential to understand the **Linux filesystem hierarchy**. Each folder has a specific role, and knowing where to place or edit files ensures your custom ISO works reliably and efficiently.

---

## 🏰 Root (`/`)

* **Description:** The root directory is the **top-level directory** of the Linux filesystem.
* **Role in Cubic:**

  * All other directories branch from here.
  * When you enter Cubic’s chroot, you are inside `/`, seeing the ISO as the complete system.
* **Tip:** Never add files directly in `/` unless necessary. Always use the appropriate subdirectory.

---

## 📂 `/bin` – Essential Binaries

* **Contains:** Core system programs used by all users (e.g., `ls`, `cp`, `bash`).
* **Role in Cubic:** Usually left untouched; only modify if adding fundamental system commands.

---

## 🛠 `/etc` – Configuration Files

* **Contains:** System-wide **configuration files and settings**.
* **Important Files for Custom ISO:**

  * `/etc/lsb-release` → Defines OS name and version.
  * `/etc/os-release` → System identification for applications and boot process.
* **Role in Cubic:**

  * Edit these files to **rebrand your ISO** and set default system configurations.

---

## 🏠 `/home` – User Data

* **Contains:** Personal files and settings for each user.
* **Role in Cubic:**

  * Preconfigure `/etc/skel/` so that **new users automatically inherit settings, themes, and extensions**.
* **Tip:** Don’t store ISO-wide files here; use `/usr` or `/opt` instead.

---

## 📦 `/usr` – User Programs & Resources

* **Contains:** Applications, libraries, and shared resources.
* **Key Subdirectories:**

  * `/usr/bin` → Programs and executables
  * `/usr/lib` → Libraries required by programs
  * `/usr/share` → Shared resources (icons, wallpapers, applications, GNOME extensions)
* **Role in Cubic:**

  * Add custom apps, extensions, and themes here for **system-wide availability**.
* **Tip:** Use `/usr/share/applications` for `.desktop` files to make apps appear in menus.

---

## 🗄 `/var` – Variable Data

* **Contains:** Logs, caches, temporary files, and spool directories.
* **Role in Cubic:**

  * Clean `/var/cache/apt/archives` and `/var/log` before building ISO to **reduce image size**.

---

## 🏛 `/opt` – Optional Software

* **Contains:** Third-party or optional applications.
* **Role in Cubic:**

  * Ideal for **bundling custom applications** outside the package manager.

---

## 🖼 `/boot` – Boot Files

* **Contains:** Kernel, initial RAM disk, and bootloader configuration.
* **Role in Cubic:**

  * Customize **GRUB splash images** and boot parameters.
  * Ensure kernels match installed packages.

---

## 🧩 `/lib` and `/lib64` – Libraries

* **Contains:** Shared libraries required by system programs.
* **Role in Cubic:**

  * Usually left unchanged unless a specific program needs a custom library.

---

## 🔧 `/sbin` – System Binaries

* **Contains:** Administrative commands (e.g., `fsck`, `ifconfig`)
* **Role in Cubic:** Typically unchanged; important for live system utilities.

---

## 🏷 `/tmp` – Temporary Files

* **Contains:** Temporary runtime files.
* **Role in Cubic:**

  * Clean before building ISO to **keep image small**.

---

## 🔌 `/dev` – Device Files

* **Contains:** Device nodes (hard drives, USBs, etc.)
* **Role in Cubic:**

  * Automatically populated in live sessions. Usually not modified.

---

## 📊 `/proc` and `/sys` – Virtual Filesystems

* **Contains:** System and kernel information (dynamic, not real files).
* **Role in Cubic:**

  * Provides runtime data. Not edited for customization.

---

## 🧩 Summary – Memory Aid

Think of Linux as a **kingdom**:

| Folder  | Role in the Kingdom      | Cubic Use                                 |
| ------- | ------------------------ | ----------------------------------------- |
| `/`     | The gate to the kingdom  | Base environment in chroot                |
| `/bin`  | Essential tools          | Usually untouched                         |
| `/sbin` | Admin tools              | Usually untouched                         |
| `/etc`  | Council chambers (rules) | Rebrand OS, configure defaults            |
| `/home` | Villagers’ homes         | Set default user configs via `/etc/skel/` |
| `/usr`  | Marketplace              | Add apps, themes, GNOME extensions        |
| `/opt`  | Optional shops           | Bundle extra apps                         |
| `/var`  | Storage vault            | Clean caches/logs to reduce ISO size      |
| `/boot` | Royal gates              | Customize boot images and kernel          |
| `/lib`  | Library archive          | Usually untouched                         |
| `/tmp`  | Temporary stalls         | Clean before building ISO                 |



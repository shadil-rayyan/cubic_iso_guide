

# 🧰 Custom Ubuntu ISO Creation with Cubic

**Author:** [Shadil A.M](https://www.linkedin.com/in/shadil-am)
**Focus:** Building a custom Ubuntu-based distribution using **Cubic** (Custom Ubuntu ISO Creator)

---

## 🚀 What Is Cubic?

**Cubic (Custom Ubuntu ISO Creator)** is a graphical tool for creating **custom Ubuntu Live ISOs**.
It provides a chroot environment where you can:

* Modify packages and system files
* Pre-install applications
* Customize themes, wallpapers, and user defaults
* Tweak boot options and preseed configuration
* Build a ready-to-install ISO for distribution or deployment

In short — it’s the easiest way to **remaster Ubuntu visually** without terminal complexity.

---

## 🧩 What You Can Do with Cubic

| Capability                  | Description                                      |
| --------------------------- | ------------------------------------------------ |
| **Add/Remove Packages**     | Install apps via `apt`, remove unwanted packages |
| **Change UI**               | Customize desktop themes, icons, wallpaper       |
| **Pre-configure Settings**  | Add `.bashrc`, `skel` files, defaults for users  |
| **Add Scripts or Services** | Autostart apps, run setup scripts                |
| **Embed Drivers**           | Include Wi-Fi/GPU/firmware drivers in ISO        |
| **Offline Installation**    | Build fully self-contained ISO with dependencies |

---

## ⚙️ How to Install Cubic

```bash
sudo add-apt-repository ppa:cubic-wizard/release
sudo apt update
sudo apt install cubic
```

Launch via **Applications → Cubic**, or:

```bash
cubic
```

---

## 🧠 How the Process Works

1. **Start Cubic**

   * Choose a project directory (e.g., `~/cubic/mydistro`)
   * Select a base Ubuntu ISO (e.g., `ubuntu-24.04-desktop.iso`)

2. **Enter Chroot Environment**

   * Cubic opens a terminal inside the extracted ISO filesystem
   * You can install packages, edit configs, add scripts, etc.

3. **Customize and Exit**

   * Modify `/etc/issue`, `/usr/share/backgrounds/`, `skel/`, etc.
   * Exit the terminal when done

4. **ISO Settings**

   * Update boot menu text, kernel options, and compression format

5. **Build ISO**

   * Cubic packages your customizations into a **new bootable ISO**

---

## 🧩 Comparison: Cubic vs Other Remaster Tools

| Feature                        | **Cubic (Ubuntu)**  | **Penguin’s Eggs (Debian/Arch)** | **Customizer (Old)** | **ArchISO (Arch)** |
| ------------------------------ | ------------------- | -------------------------------- | -------------------- | ------------------ |
| **GUI Support**                | ✅ Full GUI          | ✅ CLI + partial GUI              | ⚠️ Deprecated        | ❌ CLI only         |
| **Base OS**                    | Ubuntu / Debian     | Debian / Arch / Devuan           | Ubuntu               | Arch Linux         |
| **Chroot Editing**             | ✅ Built-in          | ✅ Shell based                    | ✅ Yes                | ✅ Yes              |
| **Bootloader Editing**         | ✅ Easy GUI          | ⚠️ Manual                        | ⚠️ Partial           | ✅ Manual           |
| **ISO Compression (SquashFS)** | ✅ Yes               | ✅ Yes                            | ✅ Yes                | ✅ Yes              |
| **Offline Mode**               | ✅ Yes               | ✅ Yes                            | ⚠️ Partial           | ⚠️ Advanced        |
| **Beginner Friendly**          | ⭐⭐⭐⭐⭐               | ⭐⭐                               | ⭐                    | ⭐                  |
| **Ideal Use**                  | Custom Ubuntu spins | Multi-distro remaster            | Legacy               | Power users        |

---



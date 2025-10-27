
### 🗂 Using `custom-root` Directly in Cubic Projects

When you create a **Cubic project**, all modifications to the ISO are stored in the **`custom-root` folder**. This folder represents the **entire filesystem of your custom ISO**, and you can interact with it directly without entering the virtual chroot environment.

Many users, especially for tasks like **adding wallpapers, copying GNOME extensions, or editing configuration files**, find it more convenient to work directly in the file system instead of using the Cubic terminal or chroot environment.

---

#### 1️⃣ Why Work Directly in `custom-root`

* **Visibility & Comfort:** You can browse folders using your file manager or IDE, which is often faster and easier than navigating the virtual chroot terminal.

* **Direct Copy & Paste:** Adding files like wallpapers or extensions is as simple as dragging and dropping into the appropriate folders:

  * Wallpapers → `custom-root/usr/share/backgrounds/`
  * Extensions → `custom-root/usr/share/gnome-shell/extensions/`
  * Applications → `custom-root/usr/share/applications/`

* **Avoid Chroot Complexity:** Some users prefer this approach because it eliminates the need to learn chroot commands or deal with environment-specific limitations.

---

#### 2️⃣ Permissions and Ownership

By default, `custom-root` files may be **owned by root** or have **restricted permissions**, preventing you from modifying them directly. To fix this:

1. **Change ownership to your user**:

```bash
sudo chown -R $(whoami):$(whoami) /path/to/custom-root
```

2. **Grant full permissions (read, write, execute) recursively**:

```bash
sudo chmod -R 777 /path/to/custom-root
```

**Explanation of Commands:**

| Command                        | Purpose                                                                                            |
| ------------------------------ | -------------------------------------------------------------------------------------------------- |
| `chown -R $(whoami):$(whoami)` | Makes your user the owner of all files and folders recursively (`-R`).                             |
| `chmod -R 777`                 | Grants **read, write, execute** permissions to all users on all files and directories recursively. |


---

#### 3️⃣ Workflow Using `custom-root`

1. Open `custom-root` in your file manager or IDE.
2. Copy or edit files directly:

   * Wallpapers → `/usr/share/backgrounds/`
   * Extensions → `/usr/share/gnome-shell/extensions/`
   * Application `.desktop` files → `/usr/share/applications/`
3. If files are locked:

   * Open a terminal.
   * Run the `chown` and `chmod` commands above.
4. After modifications, you can **re-enter Cubic** and continue building the ISO.
5. Cubic will include all changes made directly in `custom-root` during the ISO build process.

---

#### 4️⃣ Advantages of Direct Editing

* **Faster for bulk operations** like copying multiple extensions or wallpapers.
* **Full visibility** into the filesystem structure.
* **No need to repeatedly enter/exit chroot**, saving time.
* **Works seamlessly** with all other Cubic customization steps (GRUB edits, ISO compression, branding, etc.).

---

#### 5️⃣ Important Notes

* Always **backup your `custom-root` folder** before making massive changes.
* Avoid accidentally modifying system-critical files like `/boot` unless necessary.
* After finishing your edits, **verify all permissions** are correct and that no files are missing or misconfigured.

---



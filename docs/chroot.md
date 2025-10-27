
### 🧩 What Is `chroot` and Why Cubic Uses It

**`chroot`** stands for **“change root”**. It is a Linux/Unix operation that **changes the apparent root directory (`/`) for a process and its children**. In other words, the process sees a different directory tree as its root, isolated from the rest of the system.

#### Key Points:

1. **Purpose of `chroot`**

   * Creates an **isolated environment** for safely modifying a filesystem.
   * Any changes inside the `chroot` **do not affect the host OS**.

2. **Why Cubic Uses `chroot`**

   * When customizing an Ubuntu ISO, Cubic extracts the ISO filesystem and opens a **chroot shell** inside it.
   * This allows you to:

     * Install or remove packages
     * Modify system configuration
     * Add applications or extensions
     * Test scripts
   * All changes are **confined to the custom ISO** and do not affect your running system.

3. **Advantages of Using `chroot`**

   * Safe experimentation without risking the host OS.
   * Full root privileges inside the ISO environment.
   * Can replicate the environment the user will see when booting the ISO.

4. **Common Usage in Cubic**

   * Enter the chroot via the Cubic GUI terminal.
   * Run commands as if you were on a live Ubuntu system.
   * Exit the chroot once customization is done, then build the final ISO.

#### Example:

```bash
# Inside Cubic terminal (chroot)
apt update
apt install firefox gnome-tweaks
```

This installs packages **inside the ISO**, not on your host system.



Here’s a **professional, detailed, and clear explanation** of adding desktop icons in your Cubic custom ISO documentation:

---

### 🖥 Adding Desktop Icons for New Users

When creating a **custom Ubuntu-based ISO** with Cubic, you can include **preconfigured desktop icons** so that new users immediately see them after account creation.

---

#### 1️⃣ Location for Desktop Icons

* Place your `.desktop` files in the **`/etc/skel/Desktop/`** directory of your `custom-root`:

```text
custom-root/etc/skel/Desktop/
```

* **Purpose:**

  * The `/etc/skel` directory acts as a **template for new user accounts**.
  * Any file or folder here is **automatically copied** into a new user’s home directory (`~/Desktop`) when the account is created.

---

#### 2️⃣ File Format

* Desktop icons are standard `.desktop` files.
* Example structure of a `.desktop` file:

```ini
[Desktop Entry]
Name=My App
Comment=Launch My App
Exec=/usr/bin/myapp
Icon=/usr/share/icons/hicolor/48x48/apps/myapp.png
Terminal=false
Type=Application
Categories=Utility;
```

**Tips:**

* Ensure the `Exec` path points to the correct executable inside your ISO.
* `Icon` should point to an image installed in the system (e.g., `/usr/share/icons/`).
* Use proper capitalization and `.desktop` file extension.

---

#### 3️⃣ Displaying the Icons

* Modern GNOME desktops require the **Desktop extension** to show icons on the desktop.
* Make sure your ISO includes **“Desktop Icons NG (DING)”** or a similar extension.
* Without it, users **will not see any icons**, even if the `.desktop` files are correctly placed.

---

#### 4️⃣ Workflow Summary

1. Copy or create `.desktop` files in:

```text
custom-root/etc/skel/Desktop/
```

2. Verify that the executable and icon paths are correct.
3. Include **Desktop Icons NG (DING)** extension in your ISO so icons are visible.
4. Test the live environment or a new user in your installed system to ensure the icons appear on the desktop.

---

✅ **Outcome:**

* Every new user created from the ISO will automatically have your preconfigured desktop icons.
* Combined with your extensions and wallpapers, this ensures a **ready-to-use desktop environment** from first login.

---

If you want, I can now **integrate this with your Cubic workflow documentation**—wallpapers, GNOME extensions, ISO compression, GRUB splash, direct `custom-root` edits, and desktop icons—into **one fully polished, professional Markdown guide** for your MkDocs site.

Do you want me to do that?

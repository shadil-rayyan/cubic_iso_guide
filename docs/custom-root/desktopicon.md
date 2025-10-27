

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


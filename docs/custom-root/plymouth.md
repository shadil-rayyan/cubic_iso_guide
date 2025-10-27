

### 🔥 Customizing Plymouth Boot & Login Images

**Plymouth** is the **graphical boot system** used in Ubuntu-based distributions. It displays **splash screens** during boot and can also affect the **login screen background** in some configurations. Customizing Plymouth is essential when creating a branded ISO with Cubic.

---

#### 1️⃣ Location of Plymouth Files

* Plymouth files are stored in:

```text
/usr/share/plymouth/
```

* Inside, you will find:

1. **Themes**: `themes/` directory contains theme definitions, including logos, spinners, and watermarks.
2. **Boot images**: Images used during startup are stored inside specific theme folders.

Example structure:

```text
/usr/share/plymouth/themes/<theme-name>/
├── <theme-name>.plymouth      # Theme configuration file
├── spinner/                   # Animation frames
├── watermark/                 # Image file (often includes Ubuntu logo)
└── other resources            # Fonts, scripts, etc.
```

---

#### 2️⃣ Replacing the Logo / Boot Image

* Locate the **watermark or logo image** inside the theme folder.
* Replace it with your **custom image** using the **same filename** to avoid editing the theme configuration:

```bash
sudo cp my-logo.png /usr/share/plymouth/themes/<theme-name>/watermark/ubuntu-logo.png
```

* If you want, you can also edit the theme’s `.plymouth` file to point to a new image filename.

---

#### 3️⃣ Effect on Boot and Login Screens

* **Boot Splash Screen:**

  * Appears when the system starts, before the login screen.
  * Controlled entirely by Plymouth theme.

* **Login Screen (GDM/LightDM):**

  * May use the same theme or image as Plymouth.
  * By customizing the Plymouth theme, the login screen background often reflects your branding.

---

#### 4️⃣ Workflow for Cubic

1. Enter the `custom-root` folder of your Cubic project.
2. Navigate to:

```text
custom-root/usr/share/plymouth/themes/
```

3. Identify the theme used by default (`ubuntu-logo`, `breeze`, etc.).
4. Replace the **watermark/logo image** in the theme folder.
5. (Optional) Edit the theme’s `.plymouth` file to reference a different filename.
6. Continue with other Cubic customizations (wallpapers, extensions, GRUB).

---



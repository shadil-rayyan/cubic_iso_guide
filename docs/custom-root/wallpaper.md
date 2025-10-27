
### 🌄 Customizing Default Wallpapers in Ubuntu-Based ISOs

When building a custom Ubuntu-based ISO using **Cubic**, you may want to **replace default system wallpapers**. These wallpapers are often included for branding purposes, so understanding their location, XML configuration, and licensing is critical.

---

#### 1️⃣ Wallpaper Locations

* **Default wallpapers** are stored in:

```text
/usr/share/backgrounds/
```

* You may see several images here, often representing:

  * Ubuntu official wallpapers (e.g., “ubuntu-24.04.jpg”)
  * Freely licensed wallpapers (e.g., “Noble.jpg” or “Focal-Landscape.jpg”)

**Tip:** Only replace wallpapers that are **freely redistributable** to avoid licensing issues.

---

#### 2️⃣ XML Mapping Files

* Wallpapers are often referenced in **XML files** located nearby, usually in:

```text
/usr/share/gnome-background-properties/
```

* Example files:

  * `ubuntu-wallpapers.xml` → maps the default Ubuntu wallpapers
  * `noble-wallpapers.xml` → maps freely licensed wallpapers

**Purpose of XML:**

* Each XML file defines **metadata** for the wallpapers, including:

  * File path
  * Name (human-readable)
  * Type (Light, Dark, or Grey mode)
  * Default selection

---

#### 3️⃣ Editing Wallpapers Safely

There are two ways to replace wallpapers while keeping system behavior intact:

##### **Option A: Keep the XML Filename and Replace the Image**

1. Identify the image you want to replace (e.g., `ubuntu-wallpaper.jpg`)
2. Prepare your custom image with **the same filename**.
3. Replace the original file in `/usr/share/backgrounds/`:

```bash
sudo cp my-wallpaper.jpg /usr/share/backgrounds/ubuntu-wallpaper.jpg
```

**Effect:**

* XML mapping does **not need to be edited**.
* The system will display your custom image while keeping Light/Dark/Grey modes intact.

##### **Option B: Edit the XML File**

1. Open the XML file (e.g., `ubuntu-wallpapers.xml`) in a text editor:

```bash
sudo nano /usr/share/gnome-background-properties/ubuntu-wallpapers.xml
```

2. Find the `<wallpaper>` entries and modify:

   * `<name>` → human-readable label (optional)
   * `<filename>` → path to your custom image

Example:

```xml
<wallpaper>
    <name>My Custom Wallpaper</name>
    <filename>/usr/share/backgrounds/my-wallpaper.jpg</filename>
    <options>zoom</options>
    <pcolor>#000000</pcolor>
    <scolor>#FFFFFF</scolor>
    <shade_type>solid</shade_type>
</wallpaper>
```

**Effect:**

* You can rename wallpapers, add multiple modes, and assign custom metadata.
* Allows full control over Light, Dark, and Grey modes.

---

#### 4️⃣ Supporting Multiple Modes (Light/Dark/Grey)

* Modern Ubuntu and GNOME desktops support **three modes**:

  1. **Light Mode** → default wallpaper for bright themes
  2. **Dark Mode** → used when the system switches to a dark theme
  3. **Grey/Neutral Mode** → sometimes used for login screens or lock screens



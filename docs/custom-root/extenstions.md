

### 🧩 Installing and Customizing GNOME Extensions in Cubic

When creating a **custom Ubuntu-based ISO**, you may want to include **GNOME extensions** that you normally use on your own system. However, there are several challenges:

1. **Copying Extensions to the Custom ISO**

   * On your normal Ubuntu system, you installed all the extensions you wanted.

   * System-wide extensions are usually in:

     ```text
     /usr/share/gnome-shell/extensions/
     ```

   * User-local extensions are in:

     ```text
     ~/.local/share/gnome-shell/extensions/
     ```

   * To include these in your **Cubic custom ISO**, copy the desired folders into:

     ```text
     custom-root/usr/share/gnome-shell/extensions/
     ```

   * **Important:** Remove any preinstalled extensions that conflict with yours to avoid runtime errors.

---

2. **Extensions Do Not Load Automatically in Live ISO**

   * Simply copying the extension folder is **not enough**.

   * The GNOME shell looks at **override schemas** in:

     ```text
     /usr/share/glib-2.0/schemas/
     ```

   * To enable your extension during live boot:

     1. Open or create an **override schema file**.
     2. Add entries for your extension identifiers.
     3. Compile schemas with:

        ```bash
        sudo glib-compile-schemas /usr/share/glib-2.0/schemas/
        ```

   * This ensures the extension is **recognized and loaded** by GNOME in the live session.

---

3. **Extension Manager**

   * Include **GNOME Extension Manager** in your ISO to allow users to enable, disable, or configure extensions easily.

---

4. **Custom Preference Settings**

   * Some extensions store default preferences in **GSettings schemas**.

   * To preserve your own preference settings:

     * Locate the schema file inside the extension folder (e.g., `org.gnome.shell.extensions.<name>.gschema.xml`).
     * Edit it to include your desired default values.
     * Compile the schemas inside the ISO using `glib-compile-schemas`.

   * **Note:** There is no fully automated way to copy your personal preferences from your system(well i dont know); editing the schema or extension code is the workaround.

---


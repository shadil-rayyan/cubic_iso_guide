## ⚖️ Legal Guidelines for Creating Ubuntu-Derived Distributions


### 1️⃣ Base System Usage

* You may use **Ubuntu servers and mirrors** to obtain packages.
* Binary compatibility with Ubuntu is acceptable.
* If your distribution grows, consider hosting your **own repository** or partial mirrors.
* Always check the **mirror’s usage policy** before heavy redistribution.

**Reference:** Matt Zimmerman – Ubuntu Devel Mailing Lists (2006–2007)

---

### 2️⃣ Trademarks and Branding

* **Do not use the Ubuntu name or logos** in your branding, ISO, or splash screens.
* Avoid naming your derivative “Ubuntu Something” or “Lubuntu Remix”.
* You may state: `"MyDistro, based on Ubuntu"` to give credit.

**Actions:**

* Replace logos in **packages** (e.g., Ubiquity installer) with your own.
* Replace GRUB splash and Plymouth themes for a **custom boot experience**.
* Avoid Ubuntu-branded wallpapers in live CD ISO.

---

### 3️⃣ System Identification Files

Ubuntu uses several files to identify the system. For legal compliance:

| File | Recommendation |
| ---- | -------------- |
| `/etc/lsb-release` | Change `DISTRIB_DESCRIPTION` to your distro name; leave `DISTRIB_ID=Ubuntu` if necessary for compatibility. |
| `/etc/os-release` | Update `PRETTY_NAME` and `NAME` to reflect your distribution. |

*This prevents automated tools from falsely attributing your derivative as official Ubuntu.*

---

### 4️⃣ Default User Names

* Ubuntu Live CD default user is `"ubuntu"`.  
* Change it to a neutral name or your distro name (e.g., `"coder"`, `"user"`).  
* In modern Ubuntu releases, the live user name can be derived from `.disk/info`.

---

### 5️⃣ Package Names and Licenses

* Package version strings like `1.4.4-0ubuntu1` **do not require renaming**.  
* Respect the licenses of all included software; most Ubuntu packages are under GPL, MIT, Apache, or similar permissive licenses.  
* If your derivative includes **proprietary packages**, ensure you comply with their licensing terms.

---

### 6️⃣ Logos Embedded in Packages

* Many applications (installers, menus, etc.) include Ubuntu branding.
* Options:

  1. **Replace logos** with your own images.
  2. Obtain **explicit permission** from Canonical (rarely granted for unofficial derivatives).

*Example:* Replace Ubiquity installer logo in `usr/share/pixmaps/` or relevant Plymouth themes.

---

### 7️⃣ Plymouth & GRUB Splash Images

* Plymouth theme controls boot animation; GRUB controls boot menu splash.
* For legal compliance:

  * Remove Ubuntu-specific branding (`--quiet splash` in GRUB) for live boot.
  * Replace Plymouth themes with **your own graphics**.
  * Ensure branding is consistent with your derivative across live CD and installed system.

---

### 8️⃣ Contribution & Feedback

* Ubuntu encourages derivatives to **contribute bug fixes, translations, and patches** back to upstream.  
* Examples:

  * Reporting critical bugs upstream.
  * Submitting patches for libraries, themes, or installer improvements.
  * Translating software into additional languages.

*This ensures the ecosystem remains healthy and derivative distros are seen as cooperative.*

---

### 9️⃣ Existing Ubuntu Derivatives

Some derivatives provide useful reference points:

* **Kubuntu** – official flavor with KDE
* **Xubuntu** – official flavor with XFCE
* **Edubuntu** – education-focused flavor
* **Linux Mint** – standalone derivative based on Ubuntu LTS

Study their **branding choices, licensing compliance, and package management** for guidance.



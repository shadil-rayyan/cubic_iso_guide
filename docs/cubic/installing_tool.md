

### 🧩 Installation Notes & Best Practices
[](../image/virtual_enviroment.png)
You can easily install **Cubic** using the default package manager of your base OS — for example, `apt` on Ubuntu or `dnf` on Fedora — by installing the `cubic` package or using the official PPA.

When customizing your ISO:

* 🧹 **Clean up after modifications** — run `apt clean`, `autoremove`, and delete temporary files before building. This ensures your final ISO remains small and optimized.
* ⚠️ **Do not fully remove Snap** — some Ubuntu installers and desktop dependencies rely on Snap. Removing it entirely can break the installer environment.

# ☕ WSL_Internet-Cafe-Streaming-Server-Debian-AMD64

Turn your WSL into a lightweight streaming-ready Linux server in minutes (depending on your host & internet connection speed).

---

## ❌ Don't have WSL yet?

[Installation and Configuration WSL](https://github.com/neew1152/Installation-and-Configuration-WSL)

---

## 🎓 What is this?

This project helps you turn your **WSL** into a mini Linux-based streaming or browsing server. You can run web apps like **Firefox** and **Discord** inside a simple Linux interface, while still using Windows host.

---

## 🧠 Minimum System Requirements for 720p (YouTube/Netflix Passed)

You don't need a supercomputer. Here's what your WSL should have:

| Component | Minimum Requirement |
|-----------|---------------------|
| CPU       | 2–4 Cores           |
| RAM       | 1 GB                |
| Swap      | 1 GB                |
| Storage   | 6 GB                |

---

## 🛠️ One-Time Installation

Follow these steps **exactly** — just copy and paste each command into **Windows CMD** or **WSL Terminal**, as told. You only need to do this **once**.

---

### 🪟 Step 1: Reset and Install Debian on Windows

> Open **Command Prompt (CMD)** as Administrator (or user, if you want) and run:

```cmd
wsl --shutdown && wsl --unregister Debian && wsl --install Debian
```

This installs a fresh version of **Debian Linux** on your Windows system using WSL.

> **⚠️ VERY IMPORTANT WARNING!**
> The second command will completely **DELETE** any existing "Debian" Linux installation you have on WSL. If you've never used WSL or Debian before, you have nothing to worry about! If you have, make sure you back up anything you need.

---

### 🐧 Step 2: Set Up Debian (Inside WSL Terminal)

> After Debian installs, a WSL Terminal will open. Run this full command:

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install flatpak htop pipewire icewm x11-utils x11-xserver-utils xinit xrdp xorgxrdp -y && echo icewm-session > ~/.xsession && chmod +x ~/.xsession && sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo && sudo reboot
```

Explanation of the command:
*   `sudo apt update && sudo apt upgrade -y`: Updates the package lists and upgrades all installed packages.
*   `sudo apt install flatpak htop pipewire icewm x11-utils x11-xserver-utils xinit xrdp xorgxrdp -y`: Installs core packages:
    *   `flatpak`: Universal software deployment system.
    *   `htop`: Interactive process viewer.
    *   `pipewire`: Modern audio/video server (important for streaming audio).
    *   `icewm`: Lightweight window manager for a graphical environment.
    *   `x11-utils, x11-xserver-utils, xinit`: X Window System utilities for graphical applications.
    *   `xrdp, xorgxrdp`: Remote Desktop Protocol server and X.Org support for RDP connections.
*   `echo icewm-session > ~/.xsession`: Configures IceWM as the default session for XRDP.
*   `chmod +x ~/.xsession`: Makes the .xsession file executable.
*   `sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo`: Adds the Flathub repository, where many applications are available.
*   `sudo reboot`: Restarts the WSL Debian distribution to apply changes.

---

### 💻 Step 3: Open the Linux GUI (Graphical Interface)

> After rebooting, open **Command Prompt (CMD)** again and run:

```cmd
mstsc.exe && wsl -d Debian
```

This opens **Remote Desktop Connection** and launches Debian in the background.

---

### 🌐 Step 4: Find Your WSL IP & Install Apps

> Inside the Debian terminal (which pops up), run:

```bash
hostname -I && sudo flatpak install flathub org.mozilla.firefox com.discordapp.Discord
```

* Copy the IP address from `hostname -I`
* Paste it into the **Remote Desktop Connection** window
* Press **Enter** — you're in! 🎉

Now you can run Firefox or Discord from your Linux desktop!

---

## 📴 How to Shut Down the WSL

> From **Command Prompt (CMD)**:

```cmd
wsl --shutdown
```

This safely turns off the Linux system.

---

## 🔁 How to Reconnect Next Time

> To open your Linux desktop again:

```cmd
mstsc.exe && wsl -d Debian
```

* Debian starts in the background
* Remote Desktop opens — use the same IP from before

---

## 📌 Notes

* You **don't need to reinstall** after rebooting — just follow the reconnect steps.
* If your IP address changes, just run `hostname -I` inside Debian again and use that.

---

Enjoy your lightweight Linux streaming setup, right inside Windows! ✨

---
---

เหมือนที่เพลง Photograph ของ Ed Sheeran กล่าวไว้ :

> "And if you hurt me
> Well, that's okay, baby, only words bleed
> Inside these pages, you just hold me."

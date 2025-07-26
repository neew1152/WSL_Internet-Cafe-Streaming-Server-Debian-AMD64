# ☕ WSL_Internet-Cafe-Streaming-Server-Debian-AMD64

Turn your WSL into a lightweight streaming-ready Linux server in minutes (depending on your host & internet connection speed).

---

## ❌ Don't have WSL yet?

[Installation and Configuration WSL](https://github.com/neew1152/Installation-and-Configuration-WSL)

---

## 🎓 What is this?

This project helps you turn your **WSL** into a Linux-based server for streaming and browsing. You can run web apps like **Firefox** and **Discord** inside a simple Linux interface, while still using a Windows host.

---

## 🧠 Minimum System Requirements for 720p (YouTube/Netflix Passed)

You don't need a supercomputer. Here's what your WSL should have:

| Component | Minimum Requirement |
|-----------|---------------------|
| CPU       | 2–4 Cores           |
| RAM       | 288 MB              |
| Swap      | 1792 MB             |
| Storage   | 6144 MB             |

---

## 🛠️ One-Time Installation

Follow these steps **exactly** — copy and paste each command into **Windows CMD** or **WSL Terminal**, as instructed. You only need to do this **once**.

---

### 🪟 Step 1: Reset and Install Debian on Windows

> Open **Command Prompt (CMD)** as user (or Administrator, if you want) and run:

```cmd
wsl --shutdown && wsl --update && wsl --install Debian
```

---

### 🐧 Step 2: Set Up Debian (Inside WSL Terminal)

> After Debian installs, a WSL Terminal will open. Run this full command:

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install flatpak htop pipewire icewm x11-utils x11-xserver-utils xinit xrdp xorgxrdp -y && echo icewm-session > ~/.xsession && chmod +x ~/.xsession && sudo flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo && sudo poweroff
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
*   `sudo poweroff`: Power off the WSL Debian distribution to apply changes.

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

* You **don't need to reinstall** after rebooting — follow the reconnect steps.
* If your IP address changes, just run `hostname -I` inside Debian again and use that.

---
---

เหมือนกับที่เพลง Photograph ของ Ed Sheeran กล่าวไว้ :

> "And if you hurt me

> Well, that's okay, baby, only words bleed

> Inside these pages, you just hold me

> And I won't ever let you go."

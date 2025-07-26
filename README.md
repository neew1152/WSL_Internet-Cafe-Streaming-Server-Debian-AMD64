# ☕ WSL_Internet-Cafe-Streaming-Server-Debian-AMD64

This project helps you turn the WSL Debian into a server for Discord streaming and Firefox browsing.

### [❌ Don't have WSL yet?](https://github.com/neew1152/Installation-and-Configuration-WSL)

---

## 🧠 Minimum System Requirements for 720p (YouTube/Netflix Passed)

You don't need a supercomputer. Here's what your WSL should have:

| Component | Minimum Requirement |
|-----------|---------------------|
| CPU       | 2 – 6 Cores         |
| RAM       | 512 MB              |
| Swap      | 1536 MB             |
| Storage   | 6144 MB             |

---

## 🛠️ Installation

Follow these steps — copy and paste each command into **CMD** and **WSL Terminal**, as instructed.

---

### 🪟 Step 1: Install WSL Debian

> Run **CMD** as user (or Administrator, if you want) and run:

```cmd
wsl --shutdown && wsl --update && wsl --install Debian
```

---

### 🐧 Step 2: Set Up Debian (Inside WSL Terminal)

> After Debian installs, the current CMD will connect to the WSL Terminal. Run:

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

### 💻 Step 3: Connect the Desktop

> After powering off, the current WSL Terminal will reconnect to the CMD. Run:

```cmd
mstsc.exe && wsl -d Debian
```

This runs **Remote Desktop Connection** and reconnects to the WSL Terminal.

---

### 🌐 Step 4: Find WSL IP & Install Apps

> WSL Terminal, run:

```bash
hostname -I && sudo flatpak install flathub org.mozilla.firefox com.discordapp.Discord
```

* Copy the IP address from `hostname -I`
* Paste it into the **Remote Desktop Connection** window
* Press **Enter** — you're in! 🎉

---

## 📴 How to Shut Down

> From **WSL Terminal**:

```bash
sudo poweroff
```

> From **Command Prompt (CMD)**:

```cmd
wsl --shutdown
```

---

## 🔁 How to Reconnect

> CMD:

```cmd
mstsc.exe && wsl -d Debian
```

---
---

เหมือนกับที่เพลง Photograph ของ Ed Sheeran กล่าวไว้ :

> "And if you hurt me

> Well, that's okay, baby, only words bleed

> Inside these pages, you just hold me

> And I won't ever let you go."

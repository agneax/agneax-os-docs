# 07. Troubleshooting & Frequently Asked Questions

> 💬 **Got a question?** You're in the right place. This page covers the most common things users ask — from "Will it run on my laptop?" to "How do I install apps?". Scroll through or use Ctrl+F to find your topic.

---

## 🚦 Before You Begin — Quick Self-Check

```
✅ Did you verify the ISO checksum before flashing?
✅ Did you use Rufus or Etcher (not Windows default "copy to USB")?
✅ Is Secure Boot disabled in your BIOS?
✅ Are you booting from USB (not from the ISO file directly)?
```
If all four are ✅ — most issues are solvable below.

---

## 📦 Installation Issues

### ❓ The USB drive does not appear in my boot menu.

**Most likely cause:** Secure Boot is blocking unsigned boot media.

**Fix:**
1. Restart your PC and enter BIOS/UEFI settings (press `Del`, `F2`, or `F10` during startup — varies by manufacturer).
2. Find **Secure Boot** → set it to **Disabled**.
3. Save and restart. Try booting from USB again.
4. Also try inserting the USB into a rear USB port (direct to motherboard) instead of a front panel hub.

> 💡 **Tip:** On some laptops (especially HP), you also need to disable **Fast Boot** in BIOS.

---

### ❓ My screen goes black or shows garbled graphics when booting.

**Most likely cause:** Incompatible graphics driver loading at boot.

**Fix:**
1. At the GRUB bootloader menu, use arrow keys to select **AgneaX OS (Safe Graphics)**.
2. Press `Enter` to boot with basic graphics mode.
3. Once installed, open **System Settings → Display** to configure your GPU properly.

> 💡 **NVIDIA users:** After installation, open Terminal and run `sudo Linux-drivers autoinstall` to get the proprietary NVIDIA driver.

---

### ❓ The installer froze halfway through installation.

**Fix:**
1. Hold the power button to force-off your PC.
2. Reboot from USB again and retry the installation.
3. Try the **Erase Disk** option instead of Manual Partitioning — it is simpler and less prone to stalling.
4. If using a VM, increase RAM to at least 2 GB and storage to 25 GB.

---

### ❓ GRUB bootloader shows an error after installation.

**Fix:** This can happen with certain EFI partition configurations. Boot from the USB again, open Terminal, and run:
```bash
sudo grub-install --target=x86_64-efi --efi-directory=/boot/efi
sudo update-grub
```

---

## 🌐 Hardware & Peripheral Issues

### ❓ My Wi-Fi adapter is not detected.

**Most likely cause:** Your Wi-Fi card requires proprietary firmware not included in the base image.

**Fix:**
1. Temporarily connect via USB tethering (plug in your phone → enable hotspot/USB tethering).
2. Open **System Updater** and apply all available updates.
3. Restart — firmware for most Broadcom, Realtek, and Intel adapters is installed automatically.

If your adapter still doesn't work, open Terminal and run:
```bash
lspci | grep -i network
```
Share this output in a [bug report](https://github.com/agneax/agneax-os-docs/issues) and we'll help you find the right driver.

---

### ❓ No sound is coming from my speakers / headphones.

**Fix:**
1. Click the volume icon on the top status bar.
2. Make sure the volume slider is not at zero and the output is not muted (🔇).
3. Open **System Settings → Sound** and confirm the correct output device is selected.
4. If using HDMI audio, switch output to your HDMI device in the same Sound settings panel.

---

### ❓ My touchpad / trackpad isn't working properly.

**Fix:**
1. Open **System Settings → Mouse & Touchpad**.
2. Adjust sensitivity, tap-to-click, and two-finger scroll settings.
3. If the touchpad is completely dead, check if your laptop has a physical `Fn + F-key` touchpad toggle.

---

### ❓ External monitor is not detected.

**Fix:**
1. Open **System Settings → Display**.
2. Click **Detect Displays**.
3. Adjust resolution and arrangement as needed.
4. If you're using a USB-C to HDMI adapter, make sure it supports DisplayPort Alternate Mode.

---

## 🖥️ Desktop & General Usage

### ❓ How do I install apps?

**Three ways:**

| Method | Best for | How |
|---|---|---|
| **Package Installer** | .deb files you've downloaded | Double-click the `.deb` file |
| **Terminal (apt)** | Standard Linux packages | `sudo apt install <appname>` |
| **Snap** | Sandboxed universal apps | `sudo snap install <appname>` |
| **Flatpak** | More universal apps | `flatpak install <appname>` |

Popular examples:
```bash
sudo apt install vlc          # Media player
sudo snap install code        # VS Code
sudo apt install gimp         # Image editor
flatpak install spotify       # Spotify
```

---

### ❓ How do I uninstall an app?

```bash
sudo apt remove <appname>
# or for snap:
sudo snap remove <appname>
```
You can also use the **Package Installer** to uninstall `.deb` packages.

---

### ❓ How do I update AgneaX OS?

**Graphical way:** Open the **System Updater** from the dock → click **Check for Updates** → **Update All**.

**Terminal way:**
```bash
sudo apt update && sudo apt upgrade
```

---

### ❓ How do I switch between Light and Dark mode?

**Two ways:**
- Click the **Control Center** icon (top-right status bar) → toggle the 🌙 Dark Mode switch.
- Open **System Settings → Appearance** → choose Light or Dark theme.

---

### ❓ How do I pin an app to the Dock?

1. Open the app.
2. Right-click its icon in the Dock.
3. Select **Pin to Dock**.

It will stay there permanently even after closing the app.

---

### ❓ How do I take a screenshot?

- **Full screen:** Press `Print Screen`
- **Selected area:** Press `Shift + Print Screen`
- **Active window:** Press `Alt + Print Screen`

You can also open the **Screenshot** app from the launcher for more options (delay timer, cursor inclusion, etc.).

---

### ❓ How do I open the Task Manager?

Press `Ctrl + Alt + Delete` or search for **Task Manager** in the app launcher. It shows CPU, RAM, Disk, and Network usage in real time.

---

### ❓ Can I run Windows apps on AgneaX OS?

For some apps — yes! Install **Wine**:
```bash
sudo apt install wine
```
Then right-click any `.exe` file → **Open with Wine**. For better compatibility with games and complex software, consider **Bottles** (available via Flatpak):
```bash
flatpak install bottles
```

---

## 🔐 Privacy & Security

### ❓ Does AgneaX OS collect my data?

**No.** AgneaX OS does not include any telemetry, usage analytics, or tracking. Your data stays on your machine.

---

### ❓ Do I need antivirus software?

Linux is inherently more resistant to malware than Windows. For standard home use, you do not need antivirus software. If you're running a server or handling sensitive data, `ClamAV` is available:
```bash
sudo apt install clamav
```

---

### ❓ How do I set up a firewall?

The `ufw` firewall is pre-installed. Enable it with:
```bash
sudo ufw enable
sudo ufw status
```

---

## 🤔 "But I heard that..." — Common Myths Answered

### ❓ "Isn't Linux only for programmers and hackers?"

Not anymore — and AgneaX OS is proof. If you can use a smartphone, you can use AgneaX OS. The dock, top bar, and app launcher are designed to feel instantly familiar from day one.

---

### ❓ "Will my games work?"

Many do! Steam for Linux is fully supported:
```bash
sudo apt install steam
```
AgneaX OS uses the same AgneaX OS base that thousands of Steam games are tested on. Games with **Linux** or **SteamOS** support run natively. Windows-only games often work via **Proton** (Steam's compatibility layer).

---

### ❓ "Linux has no software / I can't find my apps"

The Linux software ecosystem gives you access to **over 60,000 packages** via `apt`, plus everything on **Snap Store** and **Flathub**. VS Code, Chrome, Firefox, Spotify, Discord, Zoom, Slack, Figma (via browser), and most popular tools are available.

---

### ❓ "If something breaks, I won't be able to fix it"

AgneaX OS ships on the AgneaX OS base base — the most widely documented Linux platform in the world. Any issue you encounter has almost certainly been solved on [AskLinux](https://askLinux.com), [Reddit r/linux](https://reddit.com/r/linux), or Stack Overflow. Plus, our [issue tracker](https://github.com/agneax/agneax-os-docs/issues) is always open.

---

## 📋 Frequently Asked Questions (Full List)

| Question | Answer |
|---|---|
| Is AgneaX OS free? | Yes, forever. |
| Can I try without installing? | Yes — boot from USB in live mode. |
| Can I dual-boot with Windows? | Yes — use Manual Partitioning in installer. |
| Is my data safe after install? | Your Windows files are untouched if you dual-boot correctly. |
| Is it based on Linux? | Yes — AgneaX OS base. |
| Can I use `apt install`? | Yes — full Linux apt compatibility. |
| Does it support Flatpak/Snap? | Yes — both are supported. |
| Is the source code open? | Core GPL components: yes. AgneaX custom apps: proprietary. |
| How often does it update? | Rolling system updates + major ISO releases. |
| Can I install it in VirtualBox/VMware? | Yes — works great in VMs for testing. |
| What if I break something? | You can always reinstall from USB in under 10 minutes. |
| Does it support HiDPI / 4K? | Yes — 100%, 125%, 150%, 200% scaling options. |
| Is Bluetooth supported? | Yes — toggle in Control Center or System Settings. |

---

## 🆘 Still Stuck?

We're here to help:

- 🐞 **Bug?** → [Submit a Bug Report](https://github.com/agneax/agneax-os-docs/issues/new?template=bug_report.md)
- 💡 **Idea?** → [Request a Feature](https://github.com/agneax/agneax-os-docs/issues/new?template=feature_request.md)
- 🔐 **Security issue?** → [Read our Security Policy](../SECURITY.md)

---

Previous: [06. Desktop Tour](06-desktop-tour.md) | Next: [08. How We Work](08-how-we-work.md)

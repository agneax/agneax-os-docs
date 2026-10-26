# Agneax OS Documentation & Releases

Welcome to the central hub for **Agneax OS** documentation, ISO downloads, issue tracking, and release notes.

Agneax OS is an elegant, responsive Linux distribution built for modern hardware. It delivers a distraction-free computing environment through the native **Agneax Desktop** and custom **Agneax UI** interface layer.

---

## System Requirements

| Specification | Minimum Requirement | Recommended Specification |
| :--- | :--- | :--- |
| **Processor** | 64-bit Dual-Core x86_64 CPU (2.0 GHz) | 64-bit Quad-Core CPU or better |
| **Memory (RAM)** | 2 GB RAM | 4 GB RAM or more |
| **Storage** | 20 GB free disk space | 64 GB SSD / NVMe storage |
| **Display** | 1024 x 768 resolution | 1920 x 1080 (Full HD) or higher |
| **Boot Mode** | Standard BIOS or UEFI | UEFI with 64-bit architecture |
| **Installation Media** | 8 GB USB flash drive | Fast USB 3.0 flash drive |

---

## Download Latest Release

Download the official installation image directly from GitHub Releases:

- **Current Release**: `v0.1.0`
- **Architecture**: `x86_64` (AMD64)
- **Format**: Hybrid Bootable ISO Image
- **Direct Download**: [GitHub Releases Page](https://github.com/agneax/agneax-os-docs/releases)

---

## Verifying the Download

Always verify the integrity and authenticity of your downloaded ISO file before writing it to installation media.

### On Linux or macOS
```bash
sha256sum agneax-os-v0.1.0-amd64.iso
```

### On Windows (PowerShell)
```powershell
Get-FileHash -Algorithm SHA256 .\agneax-os-v0.1.0-amd64.iso
```

Compare the resulting 64-character hash with the official hash listed in `SHA256SUMS.txt` on the release page. If the hashes match, your file is complete and safe to install.

---

## Quick Installation Summary

1. **Download**: Obtain the latest ISO and verify its SHA256 checksum.
2. **Flash**: Use a tool such as BalenaEtcher, Rufus, or `dd` to flash the ISO to a USB flash drive.
3. **Boot**: Insert the USB drive into your PC, restart, and select the USB drive from your system boot menu (usually F12, F11, or Del).
4. **Test Live**: Test Agneax OS directly in live mode without modifying your hard drive.
5. **Install**: Click **Install Agneax OS** on the desktop, follow the graphical installer prompts, and reboot when finished.

For full details, see the [Step-by-Step Installation Guide](docs/04-installation.md).

---

## Documentation Index

Explore the comprehensive user manual:

- [01. Introduction](docs/01-introduction.md)
- [02. System Requirements](docs/02-system-requirements.md)
- [03. Download and Verify](docs/03-download-and-verify.md)
- [04. Step-by-Step Installation](docs/04-installation.md)
- [05. First Boot and Setup](docs/05-first-boot-and-setup.md)
- [06. Desktop Tour](docs/06-desktop-tour.md)
- **Module Features**:
  - [Desktop Environment](docs/features/desktop-environment.md)
  - [App Launcher & Dock](docs/features/app-launcher-and-dock.md)
  - [File Manager](docs/features/file-manager.md)
  - [System Settings](docs/features/system-settings.md)
  - [Terminal](docs/features/terminal.md)
  - [System Updater](docs/features/system-updater.md)
  - [Package Installer](docs/features/package-installer.md)
  - [Multimedia Suite](docs/features/multimedia-suite.md)
  - [Application Engine](docs/features/application-engine.md)
- [07. Troubleshooting & FAQ](docs/07-troubleshooting-and-faq.md)
- [08. How We Work](docs/08-how-we-work.md)

---

## Reporting Issues & Feedback

Agneax OS source repositories are private, but user feedback is managed transparently here:

- **Bug Reports**: Encountered an issue? Submit a ticket using our [Bug Report Template](https://github.com/agneax/agneax-os-docs/issues/new?template=bug_report.md).
- **Feature Requests**: Have an idea for improvement? Submit a proposal via our [Feature Request Template](https://github.com/agneax/agneax-os-docs/issues/new?template=feature_request.md).
- **Security Vulnerabilities**: Please review our [Security Policy](SECURITY.md) to report security flaws responsibly.

# 07. Troubleshooting & Frequently Asked Questions

This section provides solutions to common issues encountered during setup or daily usage.

---

## Installation Issues

### 1. The USB drive does not show up in the boot menu.
- **Solution**: Ensure your motherboard has Secure Boot disabled. Try plugging the USB flash drive into a USB 2.0 port directly on the motherboard (rear I/O on desktop PCs) rather than front-panel hubs.

### 2. Screen goes black or displays distorted graphics upon booting.
- **Solution**: In the initial bootloader menu, select the **Safe Graphics** or **Nomodeset** boot entry. Once installed, the correct graphics drivers will be loaded automatically.

---

## Hardware & Peripheral Issues

### 1. Wi-Fi adapter is not detected.
- **Solution**: Some proprietary Wi-Fi chipsets require non-free firmware. Connect your PC via a temporary Ethernet cable or USB phone tethering, open **System Updater**, and apply all updates to install necessary firmware drivers.

### 2. Audio is not playing through the speakers.
- **Solution**: Open **System Settings > Sound**. Verify that the correct output device (e.g., Internal Speakers or Headphones) is selected and not muted.

---

## Frequently Asked Questions (FAQ)

### Is Agneax OS based on Linux?
Yes. Agneax OS is built on a stable, proven Linux foundation, pairing a rock-solid kernel and package base with our custom Agneax Desktop and Agneax UI components.

### Is the source code of Agneax OS publicly available?
The operating system core components and pre-built binaries are distributed as closed source through official ISO installation media. Our documentation, issue trackers, and release channels are public on GitHub.

### Can I dual-boot Agneax OS alongside Windows?
Yes. During installation, choose **Manual Partitioning**, allocate an existing empty partition for Agneax OS, and configure your EFI system partition. We recommend creating a full backup of your existing OS before partitioning.

### How do I install additional software?
You can install applications using the graphical Package Installer or through standard command-line package management tools in **Agneax Terminal**.

Next: [08. How We Work](08-how-we-work.md)

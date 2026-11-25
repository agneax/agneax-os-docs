# 04. Step-by-Step Installation Guide

This guide walks you through installing Agneax OS on a physical PC or virtual machine.

[SCREENSHOT: Graphical Installer Welcome Screen in Agneax OS]

## Pre-Installation Checklist

- [ ] Back up all valuable personal files to external storage.
- [ ] Ensure your PC is connected to a reliable power source.
- [ ] Connect your bootable Agneax OS USB drive.

---

## Step 1: Boot from USB Media

1. Turn off your computer completely.
2. Turn on the PC and repeatedly press your system's boot menu key:
   - **Dell**: `F12`
   - **HP**: `F9` or `Esc`
   - **Lenovo**: `F12` or `Fn + F12`
   - **ASUS / Acer**: `F8`, `F12`, or `Esc`
3. Select your USB drive from the boot list (choose the UEFI option if available).
4. In the bootloader menu, select **Agneax OS Live** and press **Enter**.

---

## Step 2: Explore the Live Desktop

The live environment boots directly into **Agneax Desktop**. You can test audio, display resolution, keyboard layout, and Wi-Fi before writing any changes to disk.

[SCREENSHOT: Agneax OS Live environment with the Install Desktop Icon highlighted]

---

## Step 3: Launch the Graphical Installer

1. Double-click the **Install Agneax OS** icon on the desktop.
2. Select your preferred installation language and click **Next**.
3. Choose your geographical region and timezone from the interactive map.
4. Select your keyboard layout and test keys in the text field.

[SCREENSHOT: Installer Timezone and Keyboard selection screen]

---

## Step 4: Storage & Disk Partitioning

Select how you want to prepare your hard drive:

- **Option A: Erase Disk (Recommended for clean installations)**
  - Automatically wipes the chosen drive and creates standard boot, root, and swap partitions.
  - Recommended for users dedicating the entire computer to Agneax OS.
- **Option B: Manual Partitioning (Advanced users)**
  - Allows you to set up dual-boot partitions or customize mount points (`/`, `/home`, `/boot/efi`).

[SCREENSHOT: Disk partitioning selection showing Erase Disk option]

---

## Step 5: User Account Setup

1. Enter your full name.
2. Enter your username (used for system login and home directory).
3. Enter a computer name (hostname on your local network).
4. Choose a strong password and re-enter it to confirm.
5. (Optional) Choose whether to log in automatically or require your password at startup.

[SCREENSHOT: User account creation screen]

---

## Step 6: Installation Execution

1. Review the installation summary screen carefully.
2. Click **Install Now** to begin copying system files.
3. The installer will format your disk and install Agneax OS. This usually takes 5 to 10 minutes depending on your storage speed.
4. When finished, check **Restart now** and click **Done**.
5. Remove the USB flash drive when prompted and press **Enter**.

Next: [05. First Boot and Setup](05-first-boot-and-setup.md)

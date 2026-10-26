# 03. Download and Verify the ISO

Follow these steps to obtain and authenticate the official Agneax OS installation media.

[SCREENSHOT: GitHub Releases asset download list showing ISO and checksum files]

## Step 1: Download the Installation Image

1. Open your web browser and navigate to the official [Agneax OS Releases Page](https://github.com/agneax/agneax-os-docs/releases).
2. Locate the latest stable release (e.g., `v0.1.0`).
3. Under the **Assets** section, download:
   - `agneax-os-v0.1.0-amd64.iso`
   - `SHA256SUMS.txt`

## Step 2: Verify File Integrity

Verifying the checksum ensures your download was not corrupted in transit and has not been tampered with.

### On Linux
Open a terminal in the folder containing your downloaded files:
```bash
sha256sum -c SHA256SUMS.txt --ignore-missing
```
**Expected output**: `agneax-os-v0.1.0-amd64.iso: OK`

### On macOS
```bash
shasum -a 256 agneax-os-v0.1.0-amd64.iso
```
Compare the output string with the hash in `SHA256SUMS.txt`.

### On Windows (PowerShell)
```powershell
Get-FileHash .\agneax-os-v0.1.0-amd64.iso -Algorithm SHA256
```
Confirm the `Hash` column matches the official release hash.

> **Caution**: If the checksums do not match, delete the downloaded file and download it again over a stable internet connection.

## Step 3: Create Bootable USB Media

Use an 8 GB or larger USB flash drive. All existing data on the USB drive will be erased.

### Recommended Tool (Cross-Platform)
1. Download and open **BalenaEtcher** (Windows, macOS, Linux).
2. Select **Flash from file** and choose your verified `agneax-os-v0.1.0-amd64.iso`.
3. Select your target USB flash drive under **Select target**.
4. Click **Flash!** and wait for the write and verification process to finish.

### Command Line Tool (Linux / macOS)
Identify your USB disk identifier carefully (e.g., `/dev/sdX`):
```bash
sudo dd if=agneax-os-v0.1.0-amd64.iso of=/dev/sdX bs=4M status=progress oflag=sync
```

Next: [04. Step-by-Step Installation](04-installation.md)

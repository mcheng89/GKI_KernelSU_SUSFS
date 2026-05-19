**IMPORTANT DISCLAIMER**

This software is provided for testing and educational purposes only. Use at your own risk.
The developers are not responsible for any damage, data loss, or issues that may occur.
Please ensure you have proper backups before installation.

## KernelSU-Next

A kernel-based root solution for Android devices.

- Version: {{KSU_VERSION}}
- Tag: {{KSU_GIT_TAG}}
- Branch: {{KSUN_BRANCH}}
- Commit: {{KSUN_COMMIT}}

- URL: https://github.com/KernelSU-Next/KernelSU-Next
- Manager: {{KSU_MANAGER}}

## SUSFS

A KSU addon for hiding root using kernel patches and a userspace module!

- SUS_PATH - Hide suspicious paths
- SUS_MOUNT - Hide mount points (no CLI support)
- SUS_KSTAT - Spoof kernel statistics
- SPOOF_UNAME - Kernel version spoofing
- SPOOF_CMDLINE - Boot parameter spoofing
- OPEN_REDIRECT - File access redirection
- SUS_MAP - Memory mapping protection
- AVC_SPOOF - Spoof procfs avc denial logs

- Version: v2.1.0
- Branches:

{{SUSFS_BRANCHES}}

- URL: https://gitlab.com/simonpunk/susfs4ksu

## Baseband Guard (BBG)

LSM-based baseband security

- Branch: main
- URL: https://github.com/vc-teahouse/Baseband-guard

## DroidSpaces

A lightweight, LXC-inspired container runtime for Android and Linux. Run full Linux distributions natively with zero performance penalty

- URL: https://github.com/ravindu644/Droidspaces-OSS

## Networking

- BBRv1 - Improved TCP congestion control
- Wireguard - Built-in VPN support
- IP Set & IPv6 NAT Support - Advanced firewall capabilities
- TTL Target Support - Network packet manipulation

## Other Features

- TMPFS_XATTR - Extended attributes for tmpfs (Mountify support)
- TMPFS_POSIX_ACL - POSIX ACLs for tmpfs

## Kernel Flasher

Recommended flashing utility

- URL: https://github.com/fatalcoder524/KernelFlasher

## Installation Instructions

### Prerequisites
- Unlocked bootloader.
- Backup your current boot image.
- Have root access using Magisk / KernelSU / Apatch (Any forks).

### Via Kernel Flasher
Download the correct AnyKernel3 ZIP for your device.
If you previously used another root method, clean it up first:
a. Magisk: perform a complete uninstall after flashing the AnyKernel3 ZIP.
b. KSU LKM (boot/init_boot/vendor_boot‑patched): Flash back the stock boot/init_boot/vendor_boot depending on what you patched.
c. KSU GKI: if you are 100% sure you already flashed stock init_boot/boot/vendor_boot, no action is needed; otherwise, follow the same steps as KSU LKM.
d. APatch: remove /data/adb contents to avoid leftover root conflicts after flashing the AnyKernel3 ZIP.
Flash the ZIP to the active slot using Kernel Flasher.
Install the KernelSU‑Next Manager APK, same version as mentioned in the release notes.
Open the KernelSU‑Next app.
Reboot the device if you performed any cleanup in step 2
**IMPORTANT DISCLAIMER**

> [!CAUTION]
> This software is provided for testing and educational purposes only. Use at your own risk. The developers are not responsible for any damage, data loss, or issues that may occur. Please ensure you have proper backups before installation.

# https://t.me/WildKernelsTG

## [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)

A kernel-based root solution for Android devices.

Manager: {{KSU_MANAGER}}

> [!IMPORTANT]
> For best compatiblity ensure your Manager Version and Kernel Version match eg. 30100 = 30100.

**Version**  
`{{KSU_VERSION}}`

**Tag**  
`{{KSU_GIT_TAG}}`

**Branch**  
`{{KSUN_BRANCH}}`

**Commit**  
`{{KSUN_COMMIT}}`

## [SUSFS v2.1.0](https://gitlab.com/simonpunk/susfs4ksu)

A KSU addon for hiding root using kernel patches and a userspace module!

Reccomended Module: [susfs4ksu-module by sidex15](https://github.com/sidex15/susfs4ksu-module)

- SUS_PATH - Hide suspicious paths
- SUS_MOUNT - Hide mount points (no CLI support)
- SUS_KSTAT - Spoof kernel statistics
- SPOOF_UNAME - Kernel version spoofing
- SPOOF_CMDLINE - Boot parameter spoofing
- OPEN_REDIRECT - File access redirection
- SUS_MAP - Memory mapping protection
- AVC_SPOOF - Spoof procfs avc denial logs

{{SUSFS_BRANCHES}}

## [Baseband Guard (BBG)](https://github.com/vc-teahouse/Baseband-guard)

A lightweight LSM (Linux Security Module) for the Android kernel, designed to block unauthorized writes to critical partitions/device nodes at the system level.

## [DroidSpaces-OSS](https://github.com/ravindu644/Droidspaces-OSS)

A lightweight, LXC-inspired container runtime for Android and Linux. Run full Linux distributions natively with zero performance penalty.

## Networking

- BBRv1 - Improved TCP congestion control
- Wireguard - Built-in VPN support
- IP Set & IPv6 NAT Support - Advanced firewall capabilities
- TTL Target Support - Network packet manipulation

## Other Features

- TMPFS_XATTR - Extended attributes for tmpfs (Mountify support)
- TMPFS_POSIX_ACL - POSIX ACLs for tmpfs

## [Kernel Flasher](https://github.com/fatalcoder524/KernelFlasher)

Recommended flashing utility

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

## Force Load Kernel Modules aka Bypass Mode — how to enable and what it does

> [!IMPORTANT]
> Most users do not need to do this so please try without this first! This has nothing to do with root detections and will not help you with them, this is for users who cannot boot my normal kernels and require this hack! 

**How to enable:** 
- To instruct the installer to use the bypass kernel when flashing, include an empty file named `ENABLE_BYPASS` at the root of the AnyKernel3 package (the ZIP) before flashing it to the device. You do not need to modify anykernel settings — just ensure `ENABLE_BYPASS` is present in the zip when you install it.

**What it does:**
- The Problem: Sometimes when installing a custom kernel, the device tries to load a kernel module that fails due to version mismatches, missing dependencies, or signature verification issues. This can cause boot failures or device instability.
- The Solution: These versions change one line from false to true to force load the kernel module, bypassing the failure check that would normally prevent loading.


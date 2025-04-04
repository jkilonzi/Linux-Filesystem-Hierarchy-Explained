# 🐧 Linux Filesystem Hierarchy – Explained

This document breaks down the Linux root (`/`) directory structure. It explains what each folder contains, its function, and why it's important for the operating system.

---

## 📁 `/bin` – **Essential User Binaries**

- **Contains:** Basic user command-line binaries.
- **Examples:** `ls`, `cp`, `mv`, `cat`, `bash`
- **Purpose:** These are essential for system operation in both single-user and multi-user modes.
- **Importance:** Required for both normal and emergency operations. Available to all users.

---

## 📁 `/boot` – **Boot Loader Files**

- **Contains:** Kernel image, initial RAM disk, and bootloader config files.
- **Examples:** `vmlinuz`, `initrd.img`, `grub/`
- **Purpose:** Holds files required to boot the system.
- **Importance:** Critical for system startup. Without it, your system won't boot.

---

## 📁 `/dev` – **Device Files**

- **Contains:** Special files representing devices.
- **Examples:** `sda`, `tty`, `null`, `random`
- **Purpose:** Interface between the kernel and hardware or virtual devices.
- **Importance:** Required for system interaction with hardware.

---

## 📁 `/etc` – **System-Wide Configuration Files**

- **Contains:** Configuration files and initialization scripts.
- **Examples:** `passwd`, `hosts`, `fstab`, `network/`, `ssh/`
- **Purpose:** Controls system settings and behavior.
- **Importance:** Core of system configuration. Any misconfiguration here can affect the system's operation.

---

## 📁 `/home` – **User Home Directories**

- **Contains:** Personal files, configs, and data for each user.
- **Examples:** `/home/alice`, `/home/bob`
- **Purpose:** Isolated environment for users to work in.
- **Importance:** Keeps user data separate from system files.

---

## 📁 `/initrd.img`, `/initrd.img.old` – **Initial RAM Disk Images**

- **Contains:** Temporary root filesystem used during early boot.
- **Purpose:** Loads drivers needed before accessing the actual root filesystem.
- **Importance:** Helps initialize the system before handing control to the main kernel.

---

## 📁 `/lib`, `/lib32`, `/lib64` – **Shared Libraries**

- **Contains:** Essential libraries needed by binaries in `/bin` and `/sbin`.
- **Examples:** `libc.so`, `ld-linux.so`, kernel modules
- **Purpose:** Provide code used by multiple programs to avoid duplication.
- **Importance:** Without these, even basic commands like `ls` would fail.

---

## 📁 `/lost+found` – **Recovered Files**

- **Contains:** Files recovered during disk repair (fsck).
- **Purpose:** Acts as a recovery folder for corrupted/ext4 file systems.
- **Importance:** Helpful in system recovery situations.

---

## 📁 `/media` – **Mount Points for Removable Media**

- **Contains:** Auto-mount points for USBs, DVDs, etc.
- **Examples:** `/media/usb`, `/media/cdrom`
- **Purpose:** Temporary access points for mounted external media.
- **Importance:** Allows users to access removable devices easily.

---

## 📁 `/mnt` – **Temporary Mount Point**

- **Contains:** Nothing by default.
- **Purpose:** Used by system administrators to mount filesystems manually.
- **Importance:** Temporary working area for maintenance tasks.

---

## 📁 `/opt` – **Optional Application Software**

- **Contains:** Add-on or third-party applications.
- **Examples:** `/opt/google/`, `/opt/vmware/`
- **Purpose:** Keeps non-essential, external software separate.
- **Importance:** Avoids cluttering the core system directories.

---

## 📁 `/proc` – **Kernel and Process Info (Virtual)**

- **Contains:** Virtual files representing kernel and process info.
- **Examples:** `/proc/cpuinfo`, `/proc/meminfo`, `/proc/1/`
- **Purpose:** Interface for interacting with the kernel.
- **Importance:** Crucial for monitoring and debugging system processes.

---

## 📁 `/root` – **Root User’s Home Directory**

- **Contains:** Files belonging to the superuser (`root`).
- **Purpose:** Acts as the root user’s workspace.
- **Importance:** Like `/home/username` but for the system administrator.

---

## 📁 `/run` – **Runtime System Information**

- **Contains:** PID files, sockets, and service-related runtime data.
- **Purpose:** Provides temporary data created at boot and cleared on shutdown.
- **Importance:** Used for system and service communication.

---

## 📁 `/sbin` – **System Binaries**

- **Contains:** System management and administrative commands.
- **Examples:** `fsck`, `reboot`, `shutdown`, `ifconfig`
- **Purpose:** Used for low-level system tasks, usually by root.
- **Importance:** Essential for booting, repairing, and recovering the system.

---

## 📁 `/snap` – **Snap Packages**

- **Contains:** Mount points for snap-managed applications.
- **Examples:** `/snap/core`, `/snap/firefox`
- **Purpose:** Used with the Snap package manager to isolate applications.
- **Importance:** Modern way to install and run sandboxed applications.

---

## 📁 `/srv` – **Service Data**

- **Contains:** Data for services like web servers and FTP.
- **Examples:** `/srv/www`, `/srv/ftp`
- **Purpose:** Standard location to store service-specific files.
- **Importance:** Keeps service-related data organized.

---

## 📁 `/sys` – **System Info (Virtual)**

- **Contains:** Information about devices and system status.
- **Examples:** `/sys/class`, `/sys/devices`
- **Purpose:** Exposes kernel data structures to user space.
- **Importance:** Used by system utilities and services to get/update hardware info.

---

## 📁 `/tmp` – **Temporary Files**

- **Contains:** Files created temporarily by applications.
- **Purpose:** Short-lived data storage.
- **Importance:** Automatically cleaned on reboot; useful for intermediate tasks.

---

## 📁 `/usr` – **User Programs and Data**

- **Contains:**
  - `/usr/bin` – Most user commands
  - `/usr/lib` – Libraries for user applications
  - `/usr/share` – Architecture-independent data
- **Purpose:** Secondary hierarchy for user apps, documentation, and libraries.
- **Importance:** Majority of userland programs are installed here.

---

## 📁 `/var` – **Variable Data Files**

- **Contains:** Logs, caches, mail spools, etc.
- **Examples:** `/var/log/`, `/var/lib/`, `/var/cache/`
- **Purpose:** Stores files that grow or change during system use.
- **Importance:** Essential for monitoring, logging, and system health.

---

## 📄 `vmlinuz`, `vmlinuz.old` – **Linux Kernel Images**

- **Contains:** The actual compressed Linux kernel used to boot the system.
- **Purpose:** Central part of the operating system.
- **Importance:** Without the kernel, the system can't operate.

---

### ✅ Summary

| Directory     | Purpose                                | Critical for Boot? | Example Contents          |
|---------------|----------------------------------------|--------------------|----------------------------|
| `/bin`        | Essential commands                     | ✅                 | `ls`, `cp`, `bash`         |
| `/boot`       | Boot files                             | ✅                 | `vmlinuz`, `grub`          |
| `/etc`        | Config files                           | ✅                 | `fstab`, `ssh/`            |
| `/home`       | User files                             | ❌                 | `/home/user`               |
| `/lib*`       | Shared libraries                       | ✅                 | `libc.so`                  |
| `/mnt`, `/media` | Mount points                       | ❌                 | `/mnt/usb`, `/media/cdrom` |
| `/opt`        | Optional software                      | ❌                 | `/opt/google`              |
| `/proc`, `/sys` | Kernel/proc info (virtual)          | ✅                 | `/proc/cpuinfo`            |
| `/root`       | Root user's home                       | ❌                 | `.bashrc`, `scripts/`      |
| `/run`        | Runtime info                           | ✅                 | `systemd`, `*.pid`         |
| `/sbin`       | System commands                        | ✅                 | `fsck`, `reboot`           |
| `/tmp`        | Temporary files                        | ❌                 | Session files              |
| `/usr`        | User apps, docs                        | ✅                 | `/usr/bin`                 |
| `/var`        | Logs, caches, spools                   | ✅                 | `/var/log`                 |

---

> ✨ This layout follows the [Filesystem Hierarchy Standard (FHS)](https://refspecs.linuxfoundation.org/FHS_3.0/fhs/index.html). It's designed for consistency and clarity across Unix-like systems.


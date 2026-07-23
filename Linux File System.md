# Linux File System Directories

## `/` (Root Directory)

**Definition:**
The root directory is the top-most directory in the Linux file system. Every file and directory starts from this location.

**Purpose:**
- Acts as the starting point of the Linux file system.
- Contains all other directories and files.
- Required for the operating system to function.

---

## `/bin` (Binary)

**Definition:**
Contains essential user command binaries (executables) that are required for basic system operation.

**Purpose:**
- Stores commonly used Linux commands.
- Commands are available to all users.
- Used even during system recovery.

**Examples:**
- `ls`
- `cp`
- `mv`
- `rm`
- `cat`
- `pwd`

---

## `/boot`

**Definition:**
Contains files required to boot the Linux operating system.

**Purpose:**
- Stores the Linux kernel.
- Stores the GRUB bootloader.
- Contains boot configuration files.

**Examples:**
- `vmlinuz`
- `initrd.img`
- `grub`

---

## `/dev` (Devices)

**Definition:**
Contains special files that represent hardware and virtual devices.

**Purpose:**
- Allows Linux to communicate with hardware devices.
- Represents disks, USB drives, terminals, and other devices as files.

**Examples:**
- `/dev/sda`
- `/dev/sdb`
- `/dev/null`
- `/dev/tty`

---

## `/etc` (Etcetera)

**Definition:**
Contains system-wide configuration files and settings.

**Purpose:**
- Stores configuration files for the operating system.
- Stores network, user, and application settings.
- Used by administrators to configure the system.

**Examples:**
- `/etc/passwd`
- `/etc/hosts`
- `/etc/fstab`
- `/etc/ssh`

---

## `/home`

**Definition:**
Contains personal home directories for normal users.

**Purpose:**
- Stores user documents, downloads, and projects.
- Each user has a separate home directory.
- Protects user data from other users.

**Example:**
- `/home/murali`
- `/home/john`

---

## `/lib` (Libraries)

**Definition:**
Contains shared libraries required by system programs and commands.

**Purpose:**
- Stores libraries used by applications.
- Required for commands in `/bin` and `/sbin`.
- Similar to DLL files in Windows.

---

## `/media`

**Definition:**
Used for automatically mounting removable storage devices.

**Purpose:**
- Provides access to USB drives.
- Mounts DVDs and CDs automatically.
- Supports external storage devices.

**Examples:**
- USB Drive
- DVD
- External Hard Disk

---

## `/mnt` (Mount)

**Definition:**
A temporary mount point used by system administrators.

**Purpose:**
- Used for manually mounting file systems.
- Commonly used during maintenance.
- Used to access additional disks.

---

## `/opt` (Optional)

**Definition:**
Contains optional third-party software packages.

**Purpose:**
- Stores software not included with the operating system.
- Keeps third-party applications separate from system files.

**Examples:**
- Google Chrome
- VMware
- Oracle Software

---

## `/proc` (Process Information)

**Definition:**
A virtual file system containing information about running processes and the Linux kernel.

**Purpose:**
- Displays CPU information.
- Displays memory information.
- Displays running process details.
- Used for system monitoring.

**Examples:**
- `/proc/cpuinfo`
- `/proc/meminfo`
- `/proc/uptime`

---

## `/root`

**Definition:**
The home directory of the root (administrator) user.

**Purpose:**
- Stores files owned by the root user.
- Used for system administration tasks.
- Separate from normal users' home directories.

---

## `/run`

**Definition:**
Contains temporary runtime data created while the system is running.

**Purpose:**
- Stores process IDs (PID files).
- Stores socket files.
- Stores lock files.
- Contents are cleared after reboot.

---

## `/sbin` (System Binary)

**Definition:**
Contains essential system administration commands.

**Purpose:**
- Used by system administrators.
- Performs system maintenance.
- Manages disks, networks, and boot processes.

**Examples:**
- `mount`
- `shutdown`
- `reboot`
- `fdisk`
- `mkfs`

---

## `/srv` (Service)

**Definition:**
Contains data used by services provided by the system.

**Purpose:**
- Stores web server files.
- Stores FTP server files.
- Used by network services.

**Examples:**
- Web Server
- FTP Server

---

## `/sys` (System)

**Definition:**
A virtual file system that provides information about hardware, devices, drivers, and the Linux kernel.

**Purpose:**
- Displays hardware information.
- Provides kernel information.
- Allows interaction with device drivers.

---

## `/tmp` (Temporary)

**Definition:**
Stores temporary files created by applications and users.

**Purpose:**
- Used for temporary storage.
- Files are often deleted automatically after reboot.
- Provides workspace for running applications.

---

## `/usr` (User System Resources)

**Definition:**
Contains user applications, libraries, documentation, and shared resources.

**Purpose:**
- Stores installed software.
- Stores user commands.
- Stores documentation and libraries.
- Contains most application files.

**Examples:**
- `/usr/bin`
- `/usr/lib`
- `/usr/share`

---

## `/var` (Variable)

**Definition:**
Contains files whose contents change frequently while the system is running.

**Purpose:**
- Stores log files.
- Stores cache files.
- Stores mail data.
- Stores databases and spool files.

**Examples:**
- `/var/log`
- `/var/cache`
- `/var/mail`
- `/var/spool`


### Easy Way to Remember

- **`/`** → Root directory
- **`/bin`** → Basic commands
- **`/boot`** → Boot files
- **`/dev`** → Devices
- **`/etc`** → Configuration files
- **`/home`** → User files
- **`/lib`** → Libraries
- **`/media`** → USB/DVD auto mounts
- **`/mnt`** → Temporary mounts
- **`/opt`** → Optional software
- **`/proc`** → Process information
- **`/root`** → Root user's home
- **`/run`** → Runtime information
- **`/sbin`** → System administration commands
- **`/srv`** → Service data
- **`/sys`** → System and hardware information
- **`/tmp`** → Temporary files
- **`/usr`** → User applications
- **`/var`** → Variable data (logs, cache, mail, databases)

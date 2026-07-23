# What is Linux?
**Linux is an open-source operating system (OS)** that manages your computer's hardware and software resources.

An Operating System acts as a **bridge between the user and the computer hardware**.


# What does Linux do?

Linux manages

* CPU
* RAM
* Hard Disk
* Keyboard
* Mouse
* Network
* Running Programs
* Security

Without Linux, applications like Docker or Python cannot communicate with the hardware.



# Timeline

```
1970
|
UNIX
|
1983
|
GNU Project
|
1991
|
Linux Kernel
|
GNU + Linux
|
Modern Linux
```



# What is Open Source?

Open Source means

* Anyone can view the source code
* Anyone can modify it
* Anyone can distribute it



# Why Companies Prefer Linux

Almost every cloud provider uses Linux.

Examples

* AWS
* Azure
* Google Cloud
* Docker
* Kubernetes
* Jenkins

Over 90% of cloud servers run Linux.



# Linux Kernel

The **Kernel** is the core (heart) of Linux.

It communicates directly with the hardware.

Everything passes through the kernel.



## Example

```
Firefox --> Kernel --> CPU-->RAM --> Disk

```

Firefox cannot directly access hardware.


# Responsibilities of Kernel

1. Memory Management
   - Controls RAM usage.
     - Chrome -- 2GB
     - Firefox -- 1GB
     - Docker -- 5MB
       
2. CPU Scheduling
   
   Many programs need the CPU.
   
    - Who runs first
    - How long each runs
      
3. Process Management

Every running program is a process

```
Firefox
Docker
SSH
Python
```

Kernel

* Starts processes
* Stops processes
* Monitors processes


4. Device Management

Controls hardware devices.

Examples

* Keyboard
* Mouse
* USB
* Printer
* Disk

Without the kernel, devices won't work.

5. File System Management

Controls files and directories.

Example

```
/home
/etc
/var
/tmp
```

Kernel

* Creates files
* Deletes files
* Reads files
* Writes files

---

6. Network Management

Handles

* Internet
* Wi-Fi
* Ethernet
* TCP/IP
* SSH

### Linux Distributions

A Linux distribution (distro) is a complete operating system built by combining:

Popular Linux Distributions

1. Ubuntu & Debian

Package Manager
```
apt
```

Install software
```
sudo apt install nginx
```
2. CentOS  &  Rocky Linux

Package Manager
```
yum
```
3. RHEL (Red Hat Enterprise Linux)

Commercial Linux.

- Used in
  - Banks
  - Hospitals
  - Government
  - Enterprises

4. Amazon Linux

# Linux Users & Groups - Quick Revision Sheet

## What is a User?
A user is an account that can log in to a Linux system and perform tasks.

## Types of Users

| User Type | UID | Description |
|-----------|-----|-------------|
| Root User | 0 | Superuser with full system access |
| System User | 1-999 | Used by services (nginx, mysql, sshd, etc.) |
| Normal User | 1000+ | Regular users created by administrators |

---

# What is a Group?

A group is a collection of users used to manage permissions easily.

Types of Groups:
- Primary Group → Default group assigned to a user.
- Secondary Group → Additional groups for extra permissions.

Example:
Murali
├── Primary Group → murali
├── Secondary Group → docker
├── Secondary Group → sudo
└── Secondary Group → developers

---

# Important User Files

| File | Purpose |
|------|----------|
| /etc/passwd | User account information |
| /etc/shadow | Encrypted passwords |
| /etc/group | Group information |
| /etc/gshadow | Group passwords |

---

# User Information Format

Example:

murali:x:1001:1001:Murali:/home/murali:/bin/bash

Meaning

Username : Password Placeholder : UID : GID : Comment : Home Directory : Login Shell

---

# Important Commands

## Current User

```bash
whoami
```

## Current User Details

```bash
id
```

## Current User UID

```bash
id -u
```

## Current User GID

```bash
id -g
```

## Logged-in Users

```bash
who
```

## Show Current Username

```bash
echo $USER
```

## Show Home Directory

```bash
echo $HOME
```

## Show Login Shell

```bash
echo $SHELL
```

---

# User Management

## Create User

```bash
sudo useradd username
```

Create Home Directory

```bash
sudo useradd -m username
```

Set Password

```bash
sudo passwd username
```

Delete User

```bash
sudo userdel username
```

Delete User with Home Directory

```bash
sudo userdel -r username
```

Rename User

```bash
sudo usermod -l newname oldname
```

Lock User

```bash
sudo usermod -L username
```

Unlock User

```bash
sudo usermod -U username
```

---

# Group Management

Create Group

```bash
sudo groupadd developers
```

Delete Group

```bash
sudo groupdel developers
```

Rename Group

```bash
sudo groupmod -n dev developers
```

Add User to Group

```bash
sudo usermod -aG developers username
```

Show User Groups

```bash
groups username
```

Current User Groups

```bash
groups
```

---

# Password Management

Change Password

```bash
passwd
```

Root Changes Any User Password

```bash
sudo passwd username
```

Expire Password

```bash
sudo passwd -e username
```

Lock Password

```bash
sudo passwd -l username
```

Unlock Password

```bash
sudo passwd -u username
```

Password Status

```bash
sudo passwd -S username
```

---

# Switch Users

Switch to Root

```bash
sudo su
```

Switch User

```bash
su username
```

Switch User with Environment

```bash
su - username
```

Return Back

```bash
exit
```

---

# File Ownership

View Ownership

```bash
ls -l
```

Example

-rw-r--r-- 1 murali developers 250 app.py

Owner = murali

Group = developers

---

Change Owner

```bash
sudo chown username file
```

Change Owner and Group

```bash
sudo chown username:group file
```

Recursive Ownership

```bash
sudo chown -R username:group directory/
```

Change Group

```bash
sudo chgrp group file
```

---

# Sudo Access

Ubuntu

```bash
sudo usermod -aG sudo username
```

RHEL / CentOS / Rocky

```bash
sudo usermod -aG wheel username
```

Verify

```bash
groups username
```

---

# Account Expiration

View Password Aging

```bash
sudo chage -l username
```

Expire Account

```bash
sudo chage -E 2026-12-31 username
```

Maximum Password Days

```bash
sudo chage -M 90 username
```

Minimum Password Days

```bash
sudo chage -m 7 username
```

Warning Days

```bash
sudo chage -W 7 username
```

---

# Permissions

Read = 4

Write = 2

Execute = 1

Examples

755 = rwxr-xr-x

644 = rw-r--r--

777 = rwxrwxrwx

---

# Frequently Used Commands

```bash
whoami
id
groups
who
w
cat /etc/passwd
cat /etc/group
cat /etc/shadow
ls -l
passwd
su -
sudo su
exit
```

---

# Important Interview Questions

✅ What is UID?
- Unique User Identifier.

✅ What is GID?
- Group Identifier.

✅ Root User UID?
- 0

✅ Normal User UID?
- 1000+

✅ System User UID?
- 1-999

✅ Where are user details stored?
- /etc/passwd

✅ Where are passwords stored?
- /etc/shadow

✅ Where are groups stored?
- /etc/group

✅ Difference between Primary and Secondary Group?
- Primary Group → Default group.
- Secondary Group → Additional groups for permissions.

✅ Difference between useradd and adduser?
- useradd → Low-level command.
- adduser → Interactive wrapper (Ubuntu/Debian).

---

# Real-Time User Creation

```bash
sudo useradd -m -s /bin/bash murali
sudo passwd murali
sudo groupadd developers
sudo usermod -aG developers murali
sudo usermod -aG sudo murali
groups murali
id murali
```

---

# Memory Trick

Root User  → UID = 0

Normal User → UID = 1000+

System User → UID = 1–999

User Info → /etc/passwd

Passwords → /etc/shadow

Groups → /etc/group

Create User → useradd

Modify User → usermod

Delete User → userdel

Create Group → groupadd

Delete Group → groupdel

Change Owner → chown

Change Group → chgrp

Change Password → passwd

Become Root → sudo su

Current User → whoami

User Details → id

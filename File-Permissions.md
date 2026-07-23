# Linux File Permissions

Understand how Linux controls access to files and directories using:

- Ownership
- Permissions
- Permission Numbers
- chmod
- chown
- chgrp
- umask
- Special Permissions (SUID, SGID, Sticky Bit)
- Access Control Lists (ACL)

---

# 1. What are File Permissions?

Every file and directory in Linux has security rules called **permissions**.

These permissions determine:

- Who can read the file
- Who can modify the file
- Who can execute the file

# Every File Has Three Owners

Linux divides users into three categories.

```
            File

         report.txt

 Owner     Group     Others

```

**Owner**

Person who created the file.

Example

```
Murali
```

Owner usually has maximum permissions.

***Group***

Multiple users belong to one group.

Example

```
Developers
HR
DevOps
```

Every member gets group permissions.

**Others**

Everyone else. Not owner.Not group member.

## Categories

```
User (u)
Group (g)
Others (o)
```

# Checking Permissions

Command

```bash
ls -l
```

Example

```bash
-rwxr-xr-- 1 murali developers 2500 Jul 20 script.sh
```

---

# Understanding Each Column

```
-rwxr-xr--  = File Type

rwx = Owner

r-x = Group

r-- = Others
```

***Owner Permissions***

```
rwx
```

Meaning

```
Read-Write-Execute
```
**Group Permissions***

```
r-x

Read-Execute
Cannot Write
```
***Others Permissions***

```
r--
Can only Read.
```

# Permission Numbers

Linux converts permissions into numbers.

```
Read(r) = 4

Write(w) = 2

Execute(x) = 1
```

# Numeric Permission Table

| Permission | Number |
|------------|--------|
| rwx | 7 |
| rw- | 6 |
| r-x | 5 |
| r-- | 4 |
| -wx | 3 |
| -w- | 2 |
| --x | 1 |
| --- | 0 |

## chmod Command

Used to change permissions.

Syntax

```bash
chmod permissions filename
```

Example

```bash
chmod 777 file.txt
chmod 755 script.sh
chmod 600 private.key

```


# Symbolic chmod

```
u = User
g = Group
o = Others
a = All
```

Adds execute permission to owner.

```bash
chmod u+x script.sh
```

Removes write permission from group.

```bash
chmod g-w file.txt
```

Give Read permision others

```bash
chmod o+r file.txt
```

Give Everyone Execute

```bash
chmod a+x file.sh
```

**Recursive Permission**

Apply to all files and directories.

```bash
chmod -R 755 project/
```

## chown Command

Changes owner.

Syntax

```bash
sudo chown <owner-name> <file-name>
```

Example

```bash
sudo chown murali report.txt
```

---

Owner and Group Together

```bash
sudo chown murali:developers report.txt
```

---

Recursive

```bash
sudo chown -R murali project/
```

---

# chgrp Command

Changes only group.

Syntax

```bash
sudo chgrp developers file.txt
```

---

# Default Permissions

When creating File

Default

```
666
```

Directory Default

```
777
```

But Linux subtracts **umask**.

---

## umask

Controls default permissions.

```bash
umask
```

Example

```
0022
```
File Calculation

```
666 - 022 = 644
```
Directory Calculation

```
777 - 022 = 755
```

Change umask

```bash
umask 027
```
# Special Permissions

Linux has three advanced permissions.

1. SUID
2. SGID
3. Sticky Bit

# 1. SUID (Set User ID)

When executable runs,

It runs as file owner.

Command

```bash
chmod u+s file
```

View

```
-rwsr-xr-x
```

Example

```
passwd
```

Normal users can change passwords because passwd has SUID.

Check

```bash
ls -l /usr/bin/passwd
```

---

# 2. SGID (Set Group ID)

Runs with group privileges.

Command

```bash
chmod g+s directory
```

View

```
rwxr-sr-x
```

Useful for shared project directories.

---

# 3. Sticky Bit

Used on directories.

Only owner can delete files.

Command

```bash
chmod +t directory
```

View

```
drwxrwxrwt
```

Example

```
/tmp
```

Everyone can create files, but only the file owner can delete their own files.


## Access Control Lists (ACL)

ACL provides permissions beyond Owner, Group, and Others.

Useful when one specific user needs access without changing ownership.

---

## Install ACL Tools

Ubuntu/Debian:

```bash
sudo apt install acl
```

RHEL/CentOS:

```bash
sudo yum install acl
```

---

## View ACL

```bash
getfacl file.txt
```

Example Output

```text
# file: file.txt
# owner: murali
# group: developers
user::rw-
user:john:r--
group::r--
mask::r--
other::---
```

---

## Give ACL Permission

Grant read/write access to user `john`:

```bash
setfacl -m u:john:rw file.txt
```

Grant execute access:

```bash
setfacl -m u:john:rwx script.sh
```

---

## Remove ACL

Remove ACL for a specific user:

```bash
setfacl -x u:john file.txt
```

Remove all ACL entries:

```bash
setfacl -b file.txt
```
# Best Practices

- Avoid using `777` unless absolutely necessary.
- Use `755` for directories.
- Use `644` for normal files.
- Use `600` for private files (SSH keys, secrets).
- Use groups to manage team access.
- Use ACLs when one extra user needs permissions.
- Verify permissions regularly with `ls -l` and `getfacl`.

---

# Frequently Used Commands

```bash
# View permissions
ls -l

# View hidden files with permissions
ls -la

# Change permissions (numeric)
chmod 755 file.sh

# Change permissions (symbolic)
chmod u+x file.sh

# Remove write permission from group
chmod g-w file.txt

# Add read permission to others
chmod o+r file.txt

# Apply permissions recursively
chmod -R 755 project/

# Change owner
sudo chown murali file.txt

# Change owner and group
sudo chown murali:developers file.txt

# Change group
sudo chgrp developers file.txt

# Check default umask
umask

# Set new umask
umask 027

# View ACL
getfacl file.txt

# Add ACL
setfacl -m u:john:rw file.txt

# Remove ACL
setfacl -x u:john file.txt

# Remove all ACLs
setfacl -b file.txt
```

---

# Interview Questions

### Q1. What are Linux file permissions?
Permissions define who can read, write, and execute files or directories.

### Q2. What do `r`, `w`, and `x` represent?
- `r` = Read (4)
- `w` = Write (2)
- `x` = Execute (1)

### Q3. What does permission `755` mean?
- Owner: `rwx` (7)
- Group: `r-x` (5)
- Others: `r-x` (5)

### Q4. What is the difference between `644` and `755`?
- `644`: Regular files (owner can edit, others can read).
- `755`: Executable files/directories (owner full access, others read and execute).

### Q5. What is the difference between `chmod`, `chown`, and `chgrp`?
- `chmod` → Changes permissions.
- `chown` → Changes owner (and optionally group).
- `chgrp` → Changes group only.

### Q6. What is `umask`?
`umask` defines the default permissions for newly created files and directories.

### Q7. What is SUID?
Allows an executable to run with the file owner's privileges.

### Q8. What is SGID?
Runs with the file group's privileges and ensures new files in a directory inherit the directory's group.

### Q9. What is the Sticky Bit?
Prevents users from deleting files they do not own in a shared directory.

### Q10. What is ACL?
Access Control Lists allow assigning permissions to specific users or groups beyond the standard owner/group/others model.

---

# Quick Revision Cheat Sheet

| Permission | Meaning | Number |
|------------|---------|--------|
| r | Read | 4 |
| w | Write | 2 |
| x | Execute | 1 |
| rwx | Full Access | 7 |
| rw- | Read + Write | 6 |
| r-x | Read + Execute | 5 |
| r-- | Read Only | 4 |

| Common Mode | Usage |
|-------------|-------|
| 777 | Full access to everyone (avoid) |
| 755 | Directories and executable scripts |
| 700 | Private directory |
| 644 | Regular files |
| 600 | Private/secret files |

| Command | Purpose |
|---------|---------|
| `ls -l` | View permissions |
| `chmod` | Change permissions |
| `chown` | Change owner |
| `chgrp` | Change group |
| `umask` | View/set default permissions |
| `getfacl` | View ACL |
| `setfacl` | Set ACL |

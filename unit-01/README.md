# LINUX ADMINISTRATION :ledger: 

## 1.Managing :card_file_box: From Command line :wavy_dash:

### 1.1 Useful Basics

**User**

```bash
apsrcreatix@ThinkPad-L430  ~ 
```

**Super User**

```bash
apsrcreatix@ThinkPad-L430  ~ sudo bash
[sudo] password for apsrcreatix: 
root@ThinkPad-L430:~# 
```

**Change the password**

```bash
apsrcreatix@ThinkPad-L430  ~ passwd
```

**History of commands used**

Use *history* command then :mag: for number written so you can use **!**[number]|[command].

Searching pattern in the history using *CTRL + r*

### 1.2 The Linux File System Hierarchy

#### 1. / – Root

- Only root user or super has write privilege under this directory.

#### 2. /bin – User Binaries

- Contains binary executables.
- Common linux commands you need to use in single-user modes are located under this directory.
- For example: ps, ls, ping, grep, cp.

#### 3. /sbin – System Binaries

- Commands located under this directory are used typically by system aministrator, for system maintenance purpose.
- For example: iptables, reboot, fdisk, ifconfig, swapon

#### 4. /etc – Configuration Files

- This directory contains static, persistent system configuration data.
- This also contains startup and shutdown shell scripts used to start/stop individual programs.
- For example: /etc/resolv.conf, /etc/logrotate.conf

#### 5. /dev – Device Files

- Contains device files.
- These include terminal devices, usb, or any device attached to the system.
- For example: /dev/tty1, /dev/usbmon0

#### 6. /proc – Process Information

- Contains information about system process.
- This is a pseudo filesystem contains information about running process. For example: /proc/{pid} directory contains information about the process with that particular pid.
- This is a virtual filesystem with text information about system resources. For example: /proc/uptime

#### 7. /var – Variable Files

- var stands for variable files.
- This directory contains dynamic configurational data, such as FTP and websites.
- This also includes — system log files (/var/log); packages and database files (/var/lib); emails (/var/mail); print queues (/var/spool); lock files (/var/lock); temp files needed across reboots (/var/tmp);

#### 8. /tmp – Temporary Files

- Directory that contains temporary files created by system and users.
- Files under this directory are deleted when system is rebooted.

#### 9. /usr – User Programs

- Contains binaries, libraries, documentation, and source-code for second level programs.
- **/usr/bin** contains binary files for user programs. *If you can’t find a user binary under /bin, look under /usr/bin.* For example: at, awk, cc, less, scp
- **/usr/sbin** contains binary files for system administrators. *If you can’t find a system binary under /sbin, look under /usr/sbin.* For example: atd, cron, sshd, useradd, userdel
- **/usr/lib** contains *libraries* for */usr/bin* and */usr/sbin*
- **/usr/local** contains users programs that you install from source. For example, when you install apache from source, it goes under /usr/local/apache2

#### 10. /home – Home Directories

- Home directories for all users to store their personal files.
- For example: /home/john, /home/nikita

#### 11. /boot – Boot Loader Files

- Contains boot loader related files.
- Kernel initrd, vmlinux, grub files are located under /boot

#### 12. /lib – System Libraries

- Contains library files that supports the binaries located under /bin and /sbin
- Library filenames are either ld* or lib*.so.*
- For example: ld-2.11.1.so, libncurses.so.5.7

#### 13. /opt – Optional add-on Applications

- opt stands for optional.
- Contains add-on applications from individual vendors.
- add-on applications should be installed under either /opt/ or /opt/ sub-directory.

#### 14. /mnt – Mount Directory

- Temporary mount directory where sysadmins can mount filesystems.

#### 15. /media – Removable Media Devices

- Temporary mount directory for removable devices.
- For examples, /media/cdrom for CD-ROM; /media/floppy for floppy drives; /media/cdrecorder for CD writer

#### 16. /srv – Service Data

- srv stands for service.
- Contains server specific services related data.
- For example, /srv/cvs contains CVS related data.

### 1.3 List of Useful Commands 

`ls [-a]|[-R]|[-l]|[-la]|[-laR]...[<foldername.>]`

`cd [foldername]|[..]|[-]|[~]|[../..]`

`pwd (present working directory)`

`cp`

`mv file1 file2 (renaming)`

`rm -r directory (recusive option for deletion) | -rf file|dirname (force remove)`

`mkdir (make directory)`

`mv dir1 dir2 (move if exist otherwise rename)`

### 1.4 Managing Linux file System Permissions

#### A) Basic Terms 

- drwxrwxrwx : owner-group-others
- d - directory
- r - read
- w - write 
- x - execute 
- wx - delete create
- drwx - everything

#### B) Managing permissions from command line using `chmod` , `chown`

- `chmod WhoWhatWhich file|directory`

Who is u(user),g(group),o(other),a(all). What is +(add),-(remove),=(set exactly). Which is r,w,x.

Example : go-rw for removing r,w permission from group and others. 

- `chmod ### file|directory`

''###'' = sum (r=4,w=2 & x=1). i.e, [0,7] range.

Example : 000 implies ---,111 implies --x--x--x,777 implies rwxrwxrwx.

- `chown [-R]...[owner:groupname]|<owner.> <previous-owner.>`

chown changes the ownership to other user from previous user.

Example : chown visitor:guests foodie implies changing permissions or ownership of foodie to vistor and the group to guests.

- **Command `umask`** without arguments will display current value of the shell's umask. 

## **Handy shortcuts for terminal** 

`Exit Session : CTRL + d`

`Jump to beginning :  CTRL + a`

`Jump to e :  CTRL + e`

`Clear towards beginning :  CTRL + u`

`Clear towards end :  CTRL + k`








# Linux Introduction Notes and Course 🐧

#### Filesystem Hierarchy Standard
The Filesystem Hierarchy Standard (FHS) is a reference describing the conventions used for the layout of a UNIX system. It has been made popular by its use in Linux distributions, but it is used by other UNIX variants as well

#### Directory structure
In the FHS, all files and directories appear under the root directory /, even if they are stored on different physical or virtual devices. Some of these directories only exist on a particular system if certain subsystems.

```
/
```
- Primary hierarchy root and root directory of the entire file system hierarchy.
```
/bin
```
- Essential command binaries that need to be available in single-user mode, including to bring up the system or repair it, for all users (cat, ls, cp).
```
/boot
```
- Boot loader files (kernels, initrd).
```
/dev
```
- Device files (/dev/null, /dev/disk0, /dev/sda1, /dev/tty, /dev/random).
```
/etc
```
- Host-specific system-wide configuration files.
There has been controversy over the meaning of the name itself. In early versions of the UNIX Implementation Document from Bell labs, /etc is referred to as the etcetera directory, as this directory historically held everything that did not belong elsewhere (however, the FHS restricts /etc to static configuration files and may not contain binaries).
```
/home
```
- Users' home directories, containing saved files, personal settings, etc.
```
/lib
```
- Libraries essential for the binaries in /bin and /sbin.
```
/media
```
- Mount points for removable media such as CD-ROMs (appeared in FHS-2.3 in 2004).
```
/mnt
```
- Temporarily mounted filesystems.
```
/opt
```
- Add-on application software packages.[7]
```
/proc
```
- Virtual filesystem providing process and kernel information as files. In Linux, corresponds to a procfs mount. Generally, automatically generated and populated by the system, on the fly.
```
/root
```
- Home directory for the root user.
```
/run
```
- Run-time variable data: Information about the running system since last boot, currently logged-in users and running daemons. Files under this directory must be either removed or truncated at the beginning of the boot process, but this is not necessary on systems that provide this directory as a temporary filesystem (tmpfs).
```
/sbin
```
- Essential system binaries (fsck, init, route).
```
/srv
```
- Site-specific data served by this system, such as data and scripts for web servers, data offered by FTP servers, and repositories for version control systems.
```
/sys
```
- Contains information about devices, drivers, and some kernel features.
```
/tmp
```
- Directory for temporary files (see also /var/tmp). Often not preserved between system reboots and may be severely size-restricted.
```
/usr
```
- Secondary hierarchy for read-only user data; contains the majority of (multi-)user utilities and applications. Should be shareable and read-only.
```
/var
```
- Variable files: files whose content is expected to continually change during normal operation of the system, such as logs, spool files, and temporary e-mail files.


# Linux commands
## Directory Manipulation Commands in Linux
```
pwd
```
- Get the full path of the current working directory.
```
cd -
```
- Navigate to the last directory you were working in.
```
cd ~
```
- or just cd Navigate to the current user’s home directory.
```
cd ..
```
- Go to the parent directory of current directory (mind the space between cd and ..)



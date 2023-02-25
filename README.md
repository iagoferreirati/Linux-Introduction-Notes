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

- pwd
  - Get the full path of the current working directory.
- cd -
  - Navigate to the last directory you were working in.
- cd ~
  - or just cd Navigate to the current user’s home directory.
- cd ..
  - Go to the parent directory of current directory (mind the space between cd and ..)

## Listing Files Inside a Directory
- ls -l 
  - List the files and directories in the current directory in long (table) format (It is recommended to use -l with ls for better readability).
- ls -ld 
  - dir-name List information about the directory dir-name instead of its contents.
- ls -a
  -  List all the files including the hidden ones (File names starting with a . are hidden files in Linux).
- ls -F 
  - Appends a symbol at the end of a file name to indicate its type (* means executable, / means directory, @ means symbolic link, = means socket, | means named pipe, > means door).
- ls -lt 
  - List the files sorted by last modified time with most recently modified files showing at the top (remember -l option provides the long format which has better readability).
- ls -lh 
  - List the file sizes in human readable format.
- ls -lR 
  - Shows all subdirectories recursively.
- tree 
  - Will generate a tree representation of the file system starting from the current directory.

## File or Directory - Create, Copy and Remove Commands in Linux
- cp -p 
  - source destination Will copy the file from source to destination directory. -p stands for preservation. It preserves the original attributes of file while copying like file owner, timestamp, group, permissions etc.
- cp -R 
  - source_dir destination_dir Will copy source directory to specified destination recursively.
- mv file1 file2 
  - In Linux there is no rename command as such. Hence mv moves/renames the file1 to file2.
- rm -i 
  - filename Asks you before every file removal for confirmation. IF YOU ARE A NEW USER TO LINUX COMMAND LINE, YOU SHOULD ALWAYS USE rm -i. You can specify multiple files.
- rm -R dir-name 
  - Will remove the directory dir-name recursively.
- rm -rf dir-name 
  - Will remove the directory dir recursively, ignoring non-existent files and will never prompt for anything. BE CAREFUL USING THIS COMMAND! You can specify multiple directories.
- rmdir dir-name 
  - Will remove the directory dir-name, if it’s empty. This command can only remove empty directories.
- mkdir dir-name 
  - Create a directory dir-name.
- mkdir -p dir-name/dir-name 
  - Create a directory hierarchy. Create parent directories as needed, if they don’t exist. You can specify multiple directories.
- touch filename 
  - Create a file filename, if it doesn’t exist, otherwise change the timestamp of the file to current time.

## File or Directory - Permissions and Groups Commands
- chmod < specification > filename Change the file permissions. Specifications = u user, g group, o other, + add permission, - remove, r read, w write, x execute.
- chmod -R < specification > dir-name Change the permissions of a directory recursively. To change the permission of a directory and everything within that directory, use this command.
- chmod go=+r myfile 
  - Add read permission for the owner and the group.
- chmod a +rwx myfile 
  - Allow all users to read, write or execute myfile.
- chmod go -r myfile 
  - Remove read permission from the group and others.
- chown owner1 filename 
  - Change ownership of a file to user owner1.
- chgrp grp_owner filename 
  - Change primary group ownership of file filename to group grp_owner.
- chgrp -R grp_owner dir-name 
  - Change the primary group ownership of directory dir-name to group grp_owner recursively. Use this command to change group ownership of a directory and everything within that directory.


##### Reference
- https://en.wikipedia.org/wiki/Filesystem_Hierarchy_Standard
- https://codeahoy.com/learn/linuxnotes/ch2/

# Linux Commands in DevOps: Complete Cheat Sheet

> Summary of the GeeksforGeeks article *"Linux command in DevOps"* (last updated 5 May 2026).
> Source: https://www.geeksforgeeks.org/linux-unix/linux-command-in-devops/

---

## 1. Summary of the page

Linux commands are the foundation of DevOps operations. They are used for **system administration, automation and troubleshooting**. They help engineers manage files, processes, users, networks and system resources efficiently, and are widely used on servers, in cloud environments and in CI/CD pipelines.

Main uses highlighted by the article:

- Manage and control running processes and services
- Automate repetitive tasks using shell scripting
- Debug issues using logs and system monitoring tools
- Enable secure remote server access (e.g., SSH)
- Configure system components such as permissions, storage and networks

The article is organized into these sections:

1. Basic commands
2. Creating files and directories
3. Copying files and directories
4. Removing files and directories
5. Renaming files and directories
6. User management
7. Group management
8. Process management
9. Linux file system permissions (plus file reading, searching and inspection commands)

---

## 2. Basic Commands

| # | Command | Definition | Example / Syntax |
|---|---------|------------|------------------|
| 1 | `pwd` | Displays the current working directory (your location in the file system). | `pwd` |
| 2 | `ls` | Lists files and directories in the current location. | `ls` |
| | `ls <path>` | Lists all files and directories in the specified path. | `ls /etc` |
| | `ls -l` | Long format: permissions, owner, size, modification time. | `ls -l` |
| | `ls -a` | Shows all files and folders, including hidden files (dotfiles). | `ls -a` |
| 3 | `uname` | Displays system information. | `uname` |
| | `uname -r` | Shows the kernel release version. | `uname -r` |
| 4 | `cd` | Changes the current directory. | `cd /path/to/dir` |
| 5 | `clear` | Clears the terminal screen for a clean workspace. | `clear` |
| 6 | `whoami` | Displays the currently logged-in user. | `whoami` |
| 7 | `history` | Shows previously executed commands. | `history` |
| 8 | `free` | Checks memory usage. | `free` |
| 9 | `nslookup` | Name Server Lookup: gets information from a DNS server for a domain. | `nslookup <domain name>` |
| 10 | `ssh-keygen` | Generates an SSH public/private key pair. | `ssh-keygen -t rsa` |
| 11 | `curl` | Transfers data from or to a server. | `curl [options] [URL]` |
| 12 | `curl -o` | Saves the downloaded data into a file on the local machine. | `curl -o [file_name] [URL...]` |
| 13 | `apt-get` | Manages packages (APT = Advanced Packaging Tool): install, update, upgrade, remove. | `apt-get [options] command` |
| 14 | `du` | Checks disk usage (space used by files and directories). | `du` |
| 15 | `df` | Checks available disk space on the system. | `df -h` |
| 16 | `ifconfig` | Views information about your network interfaces. | `ifconfig [OPTIONS] [INTERFACE]` |
| 17 | `ip` | Modern replacement for `ifconfig`: view and manage network settings, check IP addresses, configure interfaces, view routing tables. | `ip [OPTIONS] OBJECT {COMMAND \| help}` |

---

## 3. Creating Files and Directories

### Creating directories (`mkdir`)

| Use case | Definition | Command |
|----------|------------|---------|
| Single directory | Creates one directory. | `mkdir GFG` |
| Multiple directories | Creates several directories at once. | `mkdir GFG1 GFG2 GFG3` |
| Nested directories | Creates directories inside directories (`-p` creates parent folders as needed). | `mkdir -p /GFG/GFG1/GFG2` |
| Numbered series | Creates a series of numbered directories using brace expansion. | `mkdir gfg{1..3}` |

### Creating files

Files can be created with `vi`, `touch`, `echo`, `nano`, `cat`, etc.

| Command | Purpose | Example |
|---------|---------|---------|
| `touch` | Creates an empty file. | `touch file.txt` |
| `echo` | Creates a file with content. | `echo "Hello" > hello.txt` |
| `cat` | Creates/writes to a file via input (press `Ctrl + D` to save). | `cat > notes.txt` |
| `nano` | Opens a simple terminal editor. | `nano file.txt` |
| `vi` / `vim` | Opens a powerful terminal editor. | `vi file.txt` |

---

## 4. Copying Files and Directories

| Command | Definition | Example |
|---------|------------|---------|
| `cp` | Copies files and directories. The options `-rvf` mean: **r** = recursive, **v** = verbose, **f** = force overwrite. | `cp -rvf gfg1 gfg` |

---

## 5. Removing Files and Directories

| Command | Definition | Example |
|---------|------------|---------|
| `rm` | Deletes files and directories. **Deletion is permanent, so use it carefully.** `-rvf` = recursive, verbose, force. | `rm -rvf gfg` |

---

## 6. Renaming Files and Directories

| Command | Definition | Example |
|---------|------------|---------|
| `mv` | Renames files or directories (also used to move them). | `mv gfg gfg-devop` |

---

## 7. User Management

Managing users and their permissions keeps systems secure, organized and aligned with the organization's needs.

| # | Task | Command | Definition |
|---|------|---------|------------|
| 1 | Create a user | `sudo useradd [username]` | Creates a new user account. |
| 2 | Set a password | `sudo passwd [username]` | Sets or changes the password of a user. |
| 3 | Delete a user | `sudo userdel [username]` | Deletes a user account. |
| 4 | Switch user | `su [USER NAME]` | Switches to another user's account. Type `exit` to return to your original session. |
| 5 | Rename a user | `sudo usermod -l [newname] [oldname]` | Changes the username from the old name to the new name. |

---

## 8. Group Management

A group is a collection of user accounts, useful for managing and applying permissions to many users at once.

| Command | Description |
|---------|-------------|
| `sudo groupadd <groupname>` | Creates a new group. |
| `sudo groupdel <groupname>` | Deletes an existing group. |
| `sudo usermod -g <groupname> <username>` | Adds/assigns a user to a group. |

---

## 9. Process Management

Process management is the control and monitoring of processes running on a Linux system.

| # | Command | Definition | Example |
|---|---------|------------|---------|
| 1 | `ps` | Displays currently running processes. | `ps aux` |
| 2 | `top` | Real-time view of system processes, used for memory/resource monitoring. | `top` |
| 3 | `kill` | Terminates a process using its PID. | `kill 1234` |
| 4 | `pidof` | Gets the PID of a running process by name. | `pidof bash` |
| 5 | `systemctl` | Starts, stops, restarts or checks systemd-managed services (Docker, Nginx, etc.). | `sudo systemctl status nginx` |

---

## 10. Linux File System Permissions

Permissions improve system security.

### Permission types

| Symbol | Permission | Meaning |
|--------|-----------|---------|
| `r` | Read | View file contents |
| `w` | Write | Modify file contents |
| `x` | Execute | Run a file or access a directory |

### Permission categories

| Symbol | Category | Meaning |
|--------|----------|---------|
| `u` | User | Owner of the file |
| `g` | Group | Users who are part of the file's group |
| `o` | Others | All other users |

**Example:** if a file has read permission only for the user, then the user can read the file, the group cannot access it, and others cannot access it either.

### Numeric and symbolic permissions

| Number | Permission type | Symbol |
|--------|-----------------|--------|
| 0 | No permission | `---` |
| 1 | Execute | `--x` |
| 2 | Write | `-w-` |
| 3 | Write + Execute | `-wx` |
| 4 | Read | `r--` |
| 5 | Read + Execute | `r-x` |
| 6 | Read + Write | `rw-` |
| 7 | Read + Write + Execute | `rwx` |

### Permission and ownership commands

| # | Command | Definition | Syntax |
|---|---------|------------|--------|
| 1 | `ls -ld` | Checks the permissions of a directory. | `ls -ld` |
| 2 | `chmod` (Change Mode) | Changes the permissions of a file or directory. | `chmod [permissions] filename` |
| 3 | `chown` (Change Owner) | Changes the owner of a file or directory. | `chown [owner_name] [file name]` |

---

## 11. Reading, Searching and Inspecting Files

| # | Command | Definition | Syntax / Example |
|---|---------|------------|------------------|
| 4 | `cat` | Reads and concatenates text in files; displays the content of a file. | `cat <flag> {filename}` |
| | `cat -b` | Adds a number to each text line. | `cat -b file.txt` |
| | `cat -E` | Adds `$` at the end of each line. | `cat -E file.txt` |
| 5 | `grep` (Global Regular Expression Print) | Filters/searches a file for a pattern and displays all lines containing it. | `grep <flag or search_word> {file name}` |
| | `grep -i` | Case-insensitive search. | `grep -i hello file.txt` |
| | `grep -n` | Shows matching lines with their line numbers. | `grep -n hello file.txt` |
| | `grep -v` | Shows lines that do **not** contain the search string. | `grep -v hello file.txt` |
| 6 | `sort` | Prints the output of a file sorted alphabetically, numerically or in another specified way. | `sort filename` |
| 7 | `head` | Displays the first lines of one or more text files. | `head -n 2 gfg` |
| 8 | `tail` | Displays the last lines of one or more text files. | `tail -n 3 gfg` |
| 9 | `find` | Searches files and directories by criteria such as name, size, type and modification date. | `find [path] [expression]` |
| 10 | `stat` | Displays detailed permission and ownership metadata of a file. | `stat data.txt` |

---

## 12. Quick Reference by Category

| Category | Commands |
|----------|----------|
| Navigation | `pwd`, `ls`, `cd`, `clear` |
| System info | `uname`, `whoami`, `history`, `free`, `du`, `df` |
| Networking | `nslookup`, `ifconfig`, `ip`, `curl`, `ssh-keygen` |
| Packages | `apt-get` |
| Files & directories | `mkdir`, `touch`, `echo`, `cat`, `nano`, `vi`/`vim`, `cp`, `rm`, `mv` |
| Users & groups | `useradd`, `passwd`, `userdel`, `su`, `usermod`, `groupadd`, `groupdel` |
| Processes & services | `ps`, `top`, `kill`, `pidof`, `systemctl` |
| Permissions | `ls -ld`, `chmod`, `chown`, `stat` |
| Text processing & search | `cat`, `grep`, `sort`, `head`, `tail`, `find` |

---

## 13. Notes and Cautions

- `rm -rvf` deletes permanently, with no recycle bin. Double-check the path before running it.
- `ifconfig` is the older tool; `ip` is its modern replacement.
- `su` switches user; use `exit` to go back to your original session.
- `usermod -g` assigns a primary group, and `usermod -l` renames a user (do not confuse the two flags).
- Commands that modify users, groups or services generally require `sudo`.
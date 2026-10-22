# File Management in Linux: Cheat Sheet

> Summary of the GeeksforGeeks article *"File Management in Linux"* (last updated 1 Jun 2026).
> Source: https://www.geeksforgeeks.org/linux-unix/file-management-in-linux/

---

## 1. Summary

File management in Linux means handling files and directories: **creating, modifying, organizing and controlling access** within the filesystem.

- Linux treats **everything as a file**, including devices and system configuration.
- It keeps data organized and accessible.
- Common commands: `cp`, `mv`, `rm`, `ls`, `cat`.

---

## 2. Types of files

| Type | Definition | Details |
|------|------------|---------|
| **General files** | The most common type; store user data (text, images, binaries). | Documents, programs, scripts. May be human-readable text (ASCII), executable binaries or program data. |
| **Directories** | Containers that organize files and other directories in a hierarchy (like Windows folders). | Store file names and their metadata. |
| **Device files** | Represent hardware devices and handle I/O. | Used for printers, disks, terminals. Found mostly in `/dev/`. The OS treats hardware like regular files. |

### Important directories

| Directory | Role |
|-----------|------|
| `/` | Root directory (base of the system) |
| `/home/` | User home directories |
| `/bin/` | Essential user binaries |
| `/boot/` | Static boot files |

---

## 3. Common file operations

| # | Operation | Command | Definition |
|---|-----------|---------|------------|
| 1 | List files | `ls` | Lists files and directories in the current directory. Each file type has a different color (directories are usually blue). |
| | List with details | `ls -l` | Detailed listing: permissions, owner and group, size, last modification date. |
| 2 | Create a file | `touch filename` | Creates a new blank file. If the file exists, its content is untouched and only the timestamp may be updated. |
| 3 | Display content | `cat filename` | Shows the contents of a file in the terminal. For large files, use `more` or `less` to read page by page. |
| 4 | Copy a file | `cp source/filename destination/` | Copies the file to the destination, with the same name and content unless another name is given. |
| 5 | Move a file | `mv source/filename destination/` | Moves the file to another location, keeping its name and content. |
| 6 | Rename a file | `mv filename new_filename` | Renames the file without changing its data (`mv` is used for both moving and renaming). |
| 7 | Delete a file | `rm filename` | Permanently removes the file. Deleted files cannot easily be recovered, so use it carefully. |

---

## 4. Quick examples

```bash
ls                              # list files
ls -l                           # detailed list
touch notes.txt                 # create a file
cat notes.txt                   # display its content
cp notes.txt backup/            # copy to a folder
mv notes.txt archive/           # move to a folder
mv notes.txt todo.txt           # rename
rm todo.txt                     # delete (permanent)
```

---

## 5. Notes

- `ls -l` output helps you see which users or groups can access or manage each file, which is useful for system security.
- `mv` does two jobs: moving (different location) and renaming (same location, new name).
- Always double-check before using `rm`.

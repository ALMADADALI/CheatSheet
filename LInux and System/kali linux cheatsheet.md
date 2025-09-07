# 💻 Kali Linux Basics: Cheat Sheet 
---

## 📑 Table of Contents
1. 🧭 Navigation & Directory Management  
2. 📝 File Operations  
3. 🔍 Search for Files and Text  
4. 📦 Package Management with APT  
5. 🔒 Permissions and Ownership  
6. 📊 System Monitoring  
7. 🌐 Network Essentials  
8. 💾 File Compression and Archiving  
9. 🔧 Process Management  
10. ⏰ Scheduling with Cron  
11. 🔑 SSH & Remote Access  

---

## 🧭 Navigation & Directory Management

| Command              | Description                              | Example                |
|----------------------|------------------------------------------|------------------------|
| `pwd`                | Print current directory                  | `pwd`                  |
| `ls`                 | List directory contents                  | `ls`                   |
| `ls -l`              | List contents with details               | `ls -l`                |
| `ls -a`              | Include hidden files                     | `ls -a`                |
| `cd [directory]`     | Change directory                         | `cd Documents`         |
| `cd ..`              | Move up one directory                    | `cd ..`                |
| `cd ~`               | Go to the home directory                 | `cd ~`                 |
| `mkdir [name]`       | Create a new directory                   | `mkdir new_folder`     |
| `rm [file]`          | Delete a file                            | `rm file.txt`          |
| `rm -r [dir]`        | Remove a directory and contents          | `rm -r old_folder`     |
| `cp [src] [dest]`    | Copy files or directories                | `cp file1.txt file2.txt`|
| `mv [src] [dest]`    | Move or rename files or directories      | `mv file.txt new.txt`  |

---

## 📝 File Operations

| Command                  | Description                       | Example                  |
|--------------------------|-----------------------------------|--------------------------|
| `cat [file]`             | Display file contents             | `cat notes.txt`          |
| `less [file]`            | View contents with scroll option  | `less notes.txt`         |
| `head -n [num] [file]`   | Show first n lines of a file      | `head -n 5 notes.txt`    |
| `tail -n [num] [file]`   | Show last n lines of a file       | `tail -n 5 notes.txt`    |
| `nano [file]`            | Open file in nano editor          | `nano notes.txt`         |
| `vim [file]`             | Open file in vim editor           | `vim notes.txt`          |

---

## 🔍 Search for Files and Text

| Command                            | Description                          | Example                         |
|------------------------------------|--------------------------------------|---------------------------------|
| `find [path] -name [filename]`     | Find files by name in a path         | `find / -name file.txt`         |
| `locate [filename]`                | Quickly locate files (index-based)   | `locate file.txt`               |
| `grep '[text]' [file]`             | Search text within a file            | `grep 'error' log.txt`          |
| `grep -r '[text]' [dir]`           | Recursively search in directory      | `grep -r 'error' /var/logs`     |

---

## 📦 Package Management with APT

| Command                     | Description                          | Example                        |
|-----------------------------|--------------------------------------|--------------------------------|
| `sudo apt update`           | Refresh available packages           | `sudo apt update`              |
| `sudo apt upgrade`          | Install updates for all packages     | `sudo apt upgrade`             |
| `sudo apt install [pkg]`    | Install a specific package           | `sudo apt install vim`         |
| `sudo apt remove [pkg]`     | Remove a package                     | `sudo apt remove vim`          |
| `dpkg -i [file.deb]`        | Manually install a `.deb` package    | `dpkg -i mypackage.deb`        |

---

## 🔒 Permissions and Ownership

| Command                         | Description                  | Example                       |
| ------------------------------- | ---------------------------- | ----------------------------- |
| `chmod [mode] [file]`           | Change permissions           | `chmod 755 script.sh`         |
| `chown [user]:[group] [file]`   | Change ownership of file     | `chown root:staff file.txt`   |
| `chown -R [user]:[group] [dir]` | Change ownership recursively | `chown -R user:user /project` |

| Number | Permissions | Meaning |
|--------|-------------|---------|
| 7 | rwx | Read, Write, Execute |
| 5 | r-x | Read, Execute |
| 6 | rw- | Read, Write |
| 4 | r-- | Read only |
**Examples**:  
- `chmod 755 file.sh` → Owner: rwx, Group/Others: r-x  
- `chmod 644 file.sh` → Owner: rw-, Group/Others: r--

---

## 📊 System Monitoring

| Command          | Description                          | Example         |
|------------------|--------------------------------------|-----------------|
| `top`            | Real-time process monitoring         | `top`           |
| `htop`           | Enhanced process viewer (color)      | `htop`          |
| `df -h`          | Show disk usage                      | `df -h`         |
| `du -sh [dir]`   | Size of a directory                  | `du -sh /home`  |
| `free -h`        | Show memory usage                    | `free -h`       |
| `uname -a`       | System info                          | `uname -a`      |
| `ps aux`         | Show all running processes           | `ps aux`        |

---

## 🌐 Network Essentials

| Command               | Description                           | Example                        |
|-----------------------|---------------------------------------|--------------------------------|
| `ifconfig`            | Show network interface configuration  | `ifconfig`                     |
| `ip a`                | List IP addresses                     | `ip a`                         |
| `ping [host]`         | Check connectivity                    | `ping google.com`              |
| `netstat -tuln`       | List open ports                       | `netstat -tuln`                |
| `curl [URL]`          | Fetch data from URL                   | `curl http://example.com`      |
| `wget [URL]`          | Download file from URL                | `wget http://example.com/file.zip` |

---

## 💾 File Compression and Archiving

| Command                          | Description                          | Example                            |
|----------------------------------|--------------------------------------|------------------------------------|
| `tar -cvf archive.tar [dir]`     | Create `.tar` archive                | `tar -cvf backup.tar /data`        |
| `tar -xvf archive.tar`           | Extract `.tar` archive               | `tar -xvf backup.tar`              |
| `gzip [file]`                    | Compress file                        | `gzip file.txt`                    |
| `gunzip [file.gz]`               | Decompress `.gz` file                | `gunzip file.txt.gz`               |
| `zip [archive.zip] [file]`       | Zip file                             | `zip archive.zip file.txt`         |
| `unzip [archive.zip]`            | Unzip file                           | `unzip archive.zip`                |

---

## 🔧 Process Management

| Command         | Description                            | Example           |
|-----------------|----------------------------------------|-------------------|
| `kill [PID]`     | Terminate process by PID              | `kill 1234`        |
| `pkill [name]`   | Terminate by process name             | `pkill firefox`    |
| `bg`             | Resume a process in the background    | `bg`               |
| `fg`             | Bring background job to foreground    | `fg`               |
| `jobs`           | List jobs                             | `jobs`             |

---

## ⏰ Scheduling with Cron

| Command         | Description                         | Example                        |
|-----------------|-------------------------------------|--------------------------------|
| `crontab -e`     | Edit user’s cron jobs              | `crontab -e`                   |
| `* * * * * cmd`  | Cron syntax                        | `*/5 * * * * /script.sh`       |

---

## 🔑 SSH & Remote Access

| Command                                | Description                            | Example                                      |
|----------------------------------------|----------------------------------------|----------------------------------------------|
| `ssh user@host`                        | Connect to remote system               | `ssh user@192.168.1.10`                      |
| `scp [src] user@host:[dest]`           | Copy to remote system                  | `scp file.txt user@192.168.1.10:/path`       |
| `rsync -av [src] [dest]`               | Sync local and remote files            | `rsync -av /local user@remote:/destination`  |

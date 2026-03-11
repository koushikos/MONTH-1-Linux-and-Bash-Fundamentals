# MONTH-1-Linux-and-Bash-Fundamentals
Linux &amp; Bash Fundamentals Study Guide (Month 1) — A structured learning roadmap covering Linux filesystem hierarchy, essential commands, file permissions, process management, package managers, and Bash scripting with practical exercises and system administration scripts.

## A Structured Learning Guide for Cyber Security Students

---

## 📋 Overview

This comprehensive guide is designed for a B.Tech Computer Science student specializing in Cyber Security. The curriculum is structured over 4 weeks, following your study schedule:

| Day Type | Available Time |
|----------|----------------|
| College Days (Tue–Sat) | 1.5–2 hours |
| Off Days (Sun–Mon) | 4–5 hours |

**Prerequisites:**
- A Linux system (Ubuntu, Kali Linux, or Linux VM)
- Terminal- Curiosity access
 and willingness to practice

---

## 📅 Weekly Study Plan

### Week 1: Linux Filesystem & Navigation
| Day | Topic | Duration |
|-----|-------|----------|
| Tuesday | Linux Filesystem Hierarchy | 1.5 hours |
| Wednesday | Navigation commands (ls, cd, pwd) | 1.5 hours |
| Thursday | File operations (mkdir, rm, cp, mv) | 2 hours |
| Friday | Practice day & mini-challenges | 1.5 hours |
| Saturday | Review & hands-on practice | 2 hours |
| Sunday | Deep dive: Filesystem security | 4 hours |
| Monday | **Week 1 Project** | 4 hours |

### Week 2: Text Processing, Permissions & Processes
| Day | Topic | Duration |
|-----|-------|----------|
| Tuesday | File viewing (cat, less, more) | 1.5 hours |
| Wednesday | Search commands (grep, find) | 2 hours |
| Thursday | File permissions (chmod, chown) | 2 hours |
| Friday | Process management (ps, top, kill) | 1.5 hours |
| Saturday | Package management (apt, yum) | 2 hours |
| Sunday | Review &综合练习 | 4 hours |
| Monday | **Week 2 Project** | 4 hours |

### Week 3: Bash Scripting Basics
| Day | Topic | Duration |
|-----|-------|----------|
| Tuesday | Variables & user input | 1.5 hours |
| Wednesday | If/else conditionals | 2 hours |
| Thursday | For loops | 1.5 hours |
| Friday | While loops | 1.5 hours |
| Saturday | Practice day | 2 hours |
| Sunday | Functions in Bash | 4 hours |
| Monday | **Week 3 Project** | 4 hours |

### Week 4: Advanced Scripting & Real-World Projects
| Day | Topic | Duration |
|-----|-------|----------|
| Tuesday | Regular Expressions basics | 1.5 hours |
| Wednesday | grep regex patterns | 2 hours |
| Thursday | System monitoring script | 2 hours |
| Friday | Backup script | 1.5 hours |
| Saturday | Disk usage & log analyzer | 2 hours |
| Sunday | **Month 1 Final Project** | 4 hours |
| Monday | Review & certification prep | 4 hours |

---

# WEEK 1: Linux Filesystem & Navigation

---

## 📁 Chapter 1: Linux Filesystem Hierarchy

### 1. Simple Concept Explanation

Think of the Linux filesystem as a tree. Just like how files are organized in folders on Windows or Mac, Linux organizes everything in a hierarchical directory structure. The root (/) is the trunk of this tree, and all other directories branch out from it.

### 2. Technical Explanation

Linux uses a unified filesystem where everything is a file—devices, processes, even memory are represented as files. The Filesystem Hierarchy Standard (FHS) defines the directory structure:

- **Root Directory (/)**: The top-level directory containing everything
- **Single User Mode**: Uses /sbin and /bin for critical binaries
- **Multi-User Mode**: Uses /usr for user-installed software

### 3. Real-World Example

System administrators navigate this hierarchy daily:
- **DevOps Engineers**: Deploy applications to /var/www/html
- **Security Analysts**: Audit configuration files in /etc
- **Forensic Investigators**: Examine logs in /var/log

### 4. Key Directories Explained

| Directory | Purpose | Cyber Security Relevance |
|-----------|---------|--------------------------|
| `/bin` | Essential user binaries (ls, cp, mv) | Critical for system recovery |
| `/etc` | Configuration files | Primary target for attackers; must be secured |
| `/var` | Variable data (logs, caches) | Log analysis for intrusion detection |
| `/home` | User home directories | Contains user data and configs |
| `/root` | Root user home directory | Sensitive—contains root configs |
| `/usr` | User programs and libraries | Software installation target |
| `/tmp` | Temporary files | Common attack vector; cleared on reboot |
| `/boot` | Boot files | Attackers may target for bootkits |
| `/proc` | Process information | Used for system reconnaissance |
| `/dev` | Device files | Contains hardware representations |
| `/sys` | System information | Kernel data structures |
| `/opt` | Optional/third-party software | Application installations |
| `/srv` | Service data | Web server content |
| `/lost+found` | Recovered files | Forensic recovery |

### 5. Practical Terminal Examples

```bash
# Navigate to root and list contents
cd /
ls -la

# Output:
# drwxr-xr-x  19 root root  4096 Dec 25 10:00 .
# drwxr-xr-x   1 root root  4096 Dec 25 11:00 ..
# drwxr-xr-x   1 root root  4096 Dec 25 10:00 bin
# drwxr-xr-x   1 root root  4096 Dec 25 10:00 boot
# drwxr-xr-x   5 root root  4096 Dec 25 10:00 dev
# drwxr-xr-x   1 root root  4096 Dec 25 10:00 etc
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 home
# drwxr-xr-x  19 root root  4096 Dec 25 10:00 lib
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 media
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 mnt
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 opt
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 proc
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 root
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 run
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 sbin
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 srv
# drwxr-xr-x   1 root root root  4096 Dec 25 10:00 sys
# drwxr-xr-x 755 root root  4096 Dec 25 10:00 tmp
# drwxr-xr-x 755 root root  4096 Dec 25 10:00 usr
# drwxr-xr-x 755 root root  4096 Dec 25 10:00 var

# Explore /etc directory (configuration files)
ls /etc | head -20

# Output:
# adjtime
# apt
# bash.bashrc
# crontab
# debconf.conf
# default
# fstab
# group
# gshadow
# hostname
# hosts
# init.d
# ld.so.conf
# login.defs
# network
# passwd
# profile
# resolv.conf
# shadow
# sudoers

# Check /var/log directory (system logs - crucial for security)
ls -la /var/log

# Output:
# drwxr-xr-x  1 root root  4096 Dec 25 10:00 .
# drwxr-xr-x   1 root root  4096 Dec 25 10:00 ..
# -rw-r--r--  1 root root  12345 Dec 25 10:00 auth.log
# -rw-r--r--  1 root root  23456 Dec 25 10:00 syslog
# -rw-r--r--  1 root root  34567 Dec 25 10:00 kern.log
# -rw-r--r--  1 root root   5678 Dec 25 10:00 dmesg
```

### 6. Hands-on Practice Tasks

1. **Task 1**: Navigate to each major directory and list its contents
   ```bash
   cd /etc && ls | head -10
   cd /var && ls
   cd /usr && ls
   ```

2. **Task 2**: Create a diagram of the Linux filesystem on paper
   - Draw the root (/) at the center
   - Branch out each directory with its purpose

3. **Task 3**: Explore your home directory structure
   ```bash
   cd ~ && ls -la
   ```

4. **Task 4**: Find where your user files are stored
   ```bash
   echo $HOME
   ls -la $HOME
   ```

5. **Task 5**: Examine the /proc filesystem (virtual filesystem)
   ```bash
   ls /proc | head -20
   cat /proc/cpuinfo | head -10
   ```

### 7. Mini Challenge

**Challenge**: Navigate to /var/log, find the largest log file, and determine when it was last modified.

**Hint**: Use `ls -lhS` to sort by size!

**Solution**:
```bash
cd /var/log
ls -lhS | head -5
# Output:
# -rw-r----- 1 syslog admin  2.1M Dec 25 10:00 syslog
# -rw-r----- 1 root   admin  1.5M Dec 25 09:45 auth.log
# -rw-r--r-- 1 root   root   890K Dec 25 08:30 kern.log
```

### 8. Common Mistakes

| Mistake | Why It's Wrong | Correct Approach |
|---------|----------------|------------------|
| Running as root always | Security risk; can destroy system | Use regular user, sudo only when needed |
| Deleting files in /etc | Can break system | Never delete system config files |
| Ignoring /tmp | Security risk—attackers use it | Monitor and clean regularly |
| Changing permissions blindly | Can lock yourself out | Always backup before changes |

### 9. Cybersecurity Relevance

- **Penetration Testing**: Understanding filesystem is crucial for privilege escalation
- **Incident Response**: Logs in /var/log are primary evidence sources
- **System Hardening**: Securing /etc configurations is fundamental
- **Digital Forensics**: Understanding filesystem structures aids investigation
- **Malware Analysis**: Malware often hides in /tmp or /var/tmp

---

## 🔧 Chapter 2: Basic Linux Commands

### 1. Simple Concept Explanation

Linux commands are small programs that perform specific tasks. Think of them as tools in a toolbox. Just like you use a hammer to drive nails, you use `ls` to list files, `cp` to copy, and so on.

### 2. Technical Explanation

Every command in Linux is an executable program stored in /bin or /usr/bin. When you type a command:
1. The shell searches for the executable in $PATH
2. Loads it into memory
3. Executes it with any arguments you provided
4. Returns the output or error

### 3. Real-World Example

- **System Admins**: Use `ls -la` to see hidden files and permissions
- **DevOps**: Use `find` to locate configuration files across systems
- **Security Analysts**: Use `grep` to search for IOCs (Indicators of Compromise)

---

## 📂 ls - List Directory Contents

### 4. Commands with Explanation

```bash
ls [OPTIONS] [FILE/DIRECTORY]
```

| Option | Description |
|--------|-------------|
| `-l` | Long format (detailed) |
| `-a` | Show hidden files (starting with .) |
| `-h` | Human-readable sizes |
| `-S` | Sort by size |
| `-t` | Sort by time |
| `-r` | Reverse order |
| `-R` | Recursive (subdirectories) |

### 5. Practical Terminal Examples

```bash
# Basic listing
ls
# Output: Desktop Documents Downloads Music Pictures Public Templates Videos

# Detailed listing with permissions
ls -la
# Output:
# total 48
# drwxr-xr-x  5 koush koush  4096 Dec 25 10:00 .
# drwxr-xr-x  1 koush koush  4096 Dec 25 10:00 ..
# drwxr-xr-x  1 koush koush  4096 Dec 25 10:00 Desktop
# drwxr-xr-x  1 koush koush  4096 Dec 25 10:00 Documents
# drwxr-xr-x  1 koush koush  4096 Dec 25 10:00 Downloads
# -rw-r--r--  1 koush koush  1234 Dec 25 10:00 notes.txt

# Human-readable sizes
ls -lh
# Output:
# -rw-r--r--  1 koush koush  1.2K Dec 25 10:00 notes.txt

# Sort by size (largest first)
ls -lhS

# Sort by modification time (newest first)
ls -lt

# Show hidden files
ls -la

# Recursive listing
ls -R
```

### 6. Hands-on Practice Tasks

1. List all files including hidden ones: `ls -la`
2. List files sorted by size: `ls -lhS`
3. List files with detailed timestamps: `ls -l --time-style=long-iso`
4. Create a file and verify it appears in listing: `touch test.txt && ls -la test.txt`
5. List contents of /etc: `ls -la /etc`

---

## 🔄 cd - Change Directory

### 4. Commands with Explanation

```bash
cd [DIRECTORY]
cd ~       # Go to home directory
cd -       # Go to previous directory
cd ..      # Go to parent directory
cd /       # Go to root directory
cd .       # Current directory
```

### 5. Practical Terminal Examples

```bash
# Go to home directory
cd ~
# Output: (no output, just changes directory)

# Go to parent directory
cd ..

# Go to root
cd /

# Go to previous directory
cd -

# Navigate to specific path
cd /var/log

# Use absolute path from anywhere
cd /home/koush/Documents

# Use relative path
cd Documents/Projects
```

### 6. Hands-on Practice Tasks

1. Navigate to /var and then to /var/log
2. Use `cd -` to toggle between two directories
3. Use `cd ..` to move up multiple levels
4. Create a nested directory structure and navigate to it
5. Use `cd ~` and `pwd` to confirm home directory

---

## 📍 pwd - Print Working Directory

### 4. Commands with Explanation

```bash
pwd [OPTIONS]
pwd -P    # Show physical path (resolve symlinks)
pwd -L    # Show logical path (default)
```

### 5. Practical Terminal Examples

```bash
# Basic pwd
pwd
# Output: /home/koush

# After navigating
cd /var/log
pwd
# Output: /var/log

# Using logical vs physical
cd /usr/bin
pwd -L
# Output: /usr/bin
pwd -P
# Output: /usr/bin (usually same unless symlinked)
```

---

## 📁 mkdir - Make Directory

### 4. Commands with Explanation

```bash
mkdir [OPTIONS] DIRECTORY_NAME
mkdir -p    # Create parent directories as needed
mkdir -v    # Verbose mode (show what was created)
mkdir -m    # Set permissions
```

### 5. Practical Terminal Examples

```bash
# Create a single directory
mkdir myproject

# Create multiple directories
mkdir dir1 dir2 dir3

# Create nested directories
mkdir -p projects/cyber-security/network-scan

# Create with specific permissions
mkdir -m 755 secured_folder

# Create and show verbose output
mkdir -pv backup/2024/01
# Output: mkdir: created directory 'backup/2024/01'
```

### 6. Hands-on Practice Tasks

1. Create a "linux-practice" folder in your home directory
2. Create nested directories: `year/month/day`
3. Create multiple directories at once: `project1 project2 project3`
4. Create a directory with permissions 700 (only you can access)
5. Verify directory creation with `ls -ld`

---

## 🗑️ rm - Remove Files/Directories

### 4. Commands with Explanation

```bash
rm [OPTIONS] FILE
rm -r      # Recursive (for directories)
rm -f      # Force (no prompts)
rm -i      # Interactive (ask before delete)
rm -v      # Verbose
rm -d      # Remove empty directories
```

### 5. Practical Terminal Examples

```bash
# Remove a file
rm unwanted.txt

# Remove with confirmation
rm -i important.txt
# Output: rm: remove 'important.txt'? y

# Force remove (no prompt)
rm -f temporary.dat

# Remove directory and contents
rm -rf old_project/

# Remove empty directory
rmdir empty_folder

# Remove only files older than 7 days
find . -mtime +7 -delete
```

### ⚠️ SAFETY WARNING

```bash
# NEVER run these (they delete everything!):
# rm -rf /
# rm -rf *
# rm -rf .*
```

### 6. Hands-on Practice Tasks

1. Create test files and remove them individually
2. Create a directory with files and remove it with `rm -rf`
3. Use `rm -i` to practice safe deletion
4. Create files and remove them by pattern: `rm *.txt`
5. Use `rmdir` to remove an empty directory

---

## 📋 cp - Copy Files and Directories

### 4. Commands with Explanation

```bash
cp [OPTIONS] SOURCE DESTINATION
cp -r      # Recursive (directories)
cp -p      # Preserve attributes (permissions, timestamps)
cp -i      # Interactive (ask before overwrite)
cp -v      # Verbose
cp -u      # Update (copy only when source is newer)
```

### 5. Practical Terminal Examples

```bash
# Copy a file
cp document.txt backup_document.txt

# Copy to directory
cp notes.txt ~/Documents/

# Copy directory recursively
cp -r project_folder/ backup_folder/

# Copy with preserve attributes
cp -p important.log backup_important.log

# Interactive copy (ask before overwrite)
cp -i file.txt destination/
# Output: cp: overwrite 'destination/file.txt'? y

# Copy multiple files
cp file1.txt file2.txt file3.txt destination/
```

### 6. Hands-on Practice Tasks

1. Copy a file and rename it
2. Copy a file to a different directory
3. Copy an entire directory structure
4. Use `cp -p` to preserve timestamps
5. Practice with `cp -i` to prevent accidents

---

## ✏️ mv - Move/Rename Files

### 4. Commands with Explanation

```bash
mv [OPTIONS] SOURCE DESTINATION
mv -i      # Interactive (ask before overwrite)
mv -v      # Verbose
mv -n      # No overwrite
mv -f      # Force (no prompts)
```

### 5. Practical Terminal Examples

```bash
# Rename a file
mv oldname.txt newname.txt

# Move file to directory
mv report.pdf ~/Documents/

# Move and rename in one command
mv file.txt /home/koush/Desktop/newname.txt

# Interactive move
mv -i data.csv backup/
# Output: mv: overwrite 'backup/data.csv'? y

# Move multiple files
mv file1 file2 file3 destination/
```

### 6. Hands-on Practice Tasks

1. Rename a file using mv
2. Move a file to a different directory
3. Move and rename in one command
4. Use pattern matching: `mv *.txt text_files/`
5. Practice using `mv -i` for safety

---

## 📖 cat - Display File Contents

### 4. Commands with Explanation

```bash
cat [OPTIONS] FILE
cat -n    # Number lines
cat -s    # Squeeze multiple blank lines into one
cat -A    # Show non-printing characters
```

### 5. Practical Terminal Examples

```bash
# Display file contents
cat /etc/hostname

# Output:
# ubuntu-server

# Number all lines
cat -n script.sh
# Output:
#     1	#!/bin/bash
#     2	echo "Hello"
#     3	# This is a comment

# Display multiple files
cat file1.txt file2.txt

# Show non-printing characters (including tabs and line endings)
cat -A config.txt
# Output:
# This is line 1$
# Tab→here$
# End of file$

# Create a file with cat (heredoc)
cat > myfile.txt << EOF
Line 1
Line 2
Line 3
EOF
```

### 6. Hands-on Practice Tasks

1. Display the contents of /etc/passwd
2. Use `cat -n` to see line numbers
3. View multiple files at once
4. Create a file using cat with heredoc
5. View hidden characters in a file

---

## 🔍 grep - Search Text Patterns

### 4. Commands with Explanation

```bash
grep [OPTIONS] PATTERN [FILE]
grep -i      # Case insensitive
grep -r      # Recursive search
grep -n      # Show line numbers
grep -v      # Invert match (show non-matching lines)
grep -c      # Count matches
grep -w      # Match whole words
grep -A     # Show lines after match
grep -B     # Show lines before match
```

### 5. Practical Terminal Examples

```bash
# Search for a word in a file
grep "error" /var/log/syslog

# Output:
# Dec 25 10:00:01 server1 systemd[1]: Failed to start Error service

# Case insensitive search
grep -i "warning" system.log

# Show line numbers
grep -n "failed" auth.log

# Invert match (lines WITHOUT the pattern)
grep -v "success" app.log

# Recursive search in directory
grep -r "password" /etc/

# Count matches
grep -c "error" logfile.txt

# Search for multiple patterns
grep -E "error|warning|critical" system.log

# Show context (lines before and after)
grep -B 2 -A 2 "failed" auth.log
```

### 6. Hands-on Practice Tasks

1. Search for your username in /etc/passwd: `grep $USER /etc/passwd`
2. Find all lines containing "error" in /var/log/syslog
3. Use `grep -i` to search case-insensitively
4. Count how many times "root" appears in /etc/passwd
5. Search recursively for a pattern in a directory

---

## 🔎 find - Search for Files

### 4. Commands with Explanation

```bash
find [PATH] [OPTIONS]
find -name        # Search by name
find -type       # Search by type (f=file, d=directory)
find -size       # Search by size
find -mtime      # Search by modification time
find -perm       # Search by permissions
find -user       # Search by owner
find -exec       # Execute command on results
```

### 5. Practical Terminal Examples

```bash
# Find files by name
find /home -name "*.txt"

# Find directories
find / -type d -name "logs"

# Find files modified in last 7 days
find /var -mtime -7

# Find files larger than 100MB
find / -size +100M

# Find files with specific permissions
find / -perm 777

# Find files owned by specific user
find /home -user koush

# Find and delete empty files
find . -empty -delete

# Find and execute command
find /var/log -name "*.log" -exec ls -lh {} \;

# Find SUID files (security concern!)
find / -perm -4000 2>/dev/null
```

### 6. Hands-on Practice Tasks

1. Find all .txt files in your home directory
2. Find all directories named "backup"
3. Find files modified in the last 24 hours
4. Find files larger than 10MB in /var
5. Find all SUID files on the system (security check!)

---

## 📊 Week 1 Practice Project

### Project: Linux Filesystem Explorer

Create a script that:
1. Displays the filesystem hierarchy starting from /
2. Shows file counts per directory
3. Identifies the largest files in /var/log
4. Lists all hidden files in user's home directory
5. Creates a summary report

**Solution Script**:
```bash
#!/bin/bash

echo "=== Linux Filesystem Explorer ==="
echo ""

echo "Top-level directory structure:"
ls -la / | grep "^d" | awk '{print $9}'
echo ""

echo "File count in key directories:"
echo "/bin: $(ls /bin | wc -l) files"
echo "/etc: $(ls /etc | wc -l) files"
echo "/usr: $(ls /usr | wc -l) files"
echo ""

echo "Largest files in /var/log:"
ls -lhS /var/log 2>/dev/null | head -5
echo ""

echo "Hidden files in home directory:"
ls -la ~ | grep "^\." | awk '{print $9}'
echo ""

echo "=== Report Complete ==="
```

---

# WEEK 2: Text Processing, Permissions & Processes

---

## 📄 Chapter 3: File Permissions

### 1. Simple Concept Explanation

File permissions in Linux are like a security system for your files. Just as your house has locks and only certain people (family, guests) can enter, Linux files have permissions that control who can read, write, or execute them.

### 2. Technical Explanation

Every file in Linux has three types of permissions for three types of users:
- **Owner (u)**: The user who created the file
- **Group (g)**: A group of users who share permissions
- **Others (o)**: Everyone else on the system

Each permission type has three modes:
- **Read (r)**: View file contents or list directory
- **Write (w)**: Modify file or add/remove files in directory
- **Execute (x)**: Run file as program or access directory

### 3. Real-World Example

- **Web Servers**: PHP files need execute permission to run
- **SSH Keys**: Private keys must be 600 (owner read/write only)
- **Log Files**: Usually 644 (readable by all, writable by root)
- **System Configs**: Often 600 or 640 for security

### 4. Permission Notation

```
Symbolic:  rwx r-x r--
Numeric:   7   5   4

rwx = 4+2+1 = 7 (Read + Write + Execute)
r-x = 4+0+1 = 5 (Read + Execute)
r-- = 4+0+0 = 4 (Read only)
```

**Common Permission Codes:**

| Permission | Numeric | Description |
|------------|---------|-------------|
| --- | 0 | No permissions |
| r-- | 4 | Read only |
| -w- | 2 | Write only |
| --x | 1 | Execute only |
| rw- | 6 | Read and Write |
| r-x | 5 | Read and Execute |
| -wx | 3 | Write and Execute |
| rwx | 7 | Full permissions |
| rwsr-xr-x | 4755 | SUID set |
| rwxr-sr-x | 2755 | SGID set |
| rwxr-xr-t | 1755 | Sticky bit |

### 5. Understanding Permission Strings

```
drwxr-xr-x  5  koush  koush  4096  Dec 25 10:00  Documents
↑         ↑  ↑      ↑     ↑     ↑        ↑       ↑
|         |  |      |     |     |        |       +-- Name
|         |  |      |     |     |        +---------- Month
|         |  |      |     |     +------------------- Day
|         |  |      |     +------------------------- Year
|         |  |      +------------------------------ Group
|         |  +------------------------------------- Owner
|         +---------------------------------------- File type (d=dir, -=file, l=link)
+----------------------------------------------- Permissions (rwx r-x r--)
                                                  (owner group others)
```

---

## chmod - Change File Permissions

### 4. Commands with Explanation

```bash
chmod [OPTIONS] MODE FILE
chmod u+x file        # Add execute for owner
chmod g-w file        # Remove write from group
chmod o=r file        # Set others to read only
chmod 755 file        # Set rwxr-xr-x
chmod 644 file        # Set rw-r--r--
chmod -R 755 dir      # Recursive
chmod +x file         # Add execute for all
```

### 5. Practical Terminal Examples

```bash
# Add execute permission for owner
chmod u+x script.sh

# Remove write permission for group and others
chmod go-w file.txt

# Set specific permissions (rwxr-xr-x)
chmod 755 program

# Set secure permissions (rw-------)
chmod 600 private_key

# Common web file permissions
chmod 644 index.html      # Web files
chmod 755 scripts/        # CGI scripts
chmod 600 .env           # Environment variables

# Recursive permission change
chmod -R 755 projects/

# Make file executable
chmod +x myscript.sh
```

### 6. Hands-on Practice Tasks

1. Create a file and set permissions to 755
2. Create a private file with 600 permissions
3. Add execute permission to a script
4. Remove all permissions from a test file
5. Use `ls -l` to verify permission changes

---

## chown - Change File Owner

### 4. Commands with Explanation

```bash
chown [OPTIONS] OWNER:GROUP FILE
chown user file           # Change owner
chown user:group file    # Change owner and group
chown :group file        # Change group only
chown -R user:group dir  # Recursive
```

### 5. Practical Terminal Examples

```bash
# Change file owner
sudo chown john file.txt

# Change owner and group
sudo chown www-data:www-data /var/www

# Change group only
chown :developers project/

# Recursive change (requires sudo)
sudo chown -R www-data:www-data /var/www/html
```

### 6. Hands-on Practice Tasks

1. Create a file and change its ownership to your user
2. Use sudo to change ownership to root
3. Change both owner and group
4. Recursively change ownership of a directory

---

## 📊 Chapter 4: Process Management

### 1. Simple Concept Explanation

A process is a running program. Just like you can have multiple apps open on your computer, Linux can run hundreds of programs simultaneously. Process management is how we control these running programs.

### 2. Technical Explanation

Every process in Linux has:
- **PID (Process ID)**: Unique identifier
- **PPID (Parent PID)**: The process that started it
- **UID/GID**: User and group that owns it
- **Priority**: CPU scheduling priority (nice value)
- **State**: Running, sleeping, stopped, zombie

### 3. Real-World Example

- **System Monitoring**: Use `top` to check system performance
- **Kill Malware**: Terminate suspicious processes
- **Service Management**: Control system services (Apache, MySQL)
- **Resource Management**: Identify resource-heavy processes

---

## ps - Process Status

### 4. Commands with Explanation

```bash
ps [OPTIONS]
ps -e     # Show all processes
ps -f     # Full format
ps -u     # User-oriented format
ps -p     # Show specific PID
ps aux    # BSD style (all, user, command)
ps -ef    # Standard format (all, full)
```

### 5. Practical Terminal Examples

```bash
# Basic process list
ps
# Output:
#   PID TTY          TIME CMD
#  1234 pts/0    00:00:00 bash
#  5678 pts/0    00:00:00 ps

# Show all processes
ps -ef

# Output:
# UID        PID  PPID  C STIME TTY          TIME CMD
# root         1     0  0 Dec25 ?        00:00:05 /sbin/init
# root       123     1  0 Dec25 ?        00:00:00 /usr/sbin/sshd
# koush     1234     1  0 Dec25 pts/0   00:00:00 bash

# BSD style with user info
ps aux

# Output:
# USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
# root         1  0.0  0.0   2384  1464 ?        Ss   Dec25   0:05 /sbin/init
# root       123  0.0  0.0  12345  5678 ?        S    Dec25   0:00 /usr/sbin/sshd

# Find specific process
ps -ef | grep apache2

# Show process tree
ps -ef --forest

# Show processes for current user
ps -u $USER
```

---

## top - Interactive Process Viewer

### 4. Commands with Explanation

```bash
top [OPTIONS]
top -p     # Monitor specific PIDs
top -u     # Show processes for specific user
top -d     # Set delay (seconds)
top -n     # Number of iterations
```

### 5. Practical Terminal Examples

```bash
# Run top (interactive)
top

# Top output (sample):
# top - 10:00:00 up 5 days,  3:22,  2 users,  load average: 0.52, 0.58, 0.59
# Tasks: 145 total,   1 running, 144 sleeping,   0 stopped,   0 zombie
# %Cpu(s):  5.3 us,  2.1 sy,  0.0 ni, 92.6 id,  0.0 wa,  0.0 hi,  0.0 si
# MiB Mem :   8192.0 total,   2048.0 free,   4096.0 used,   2048.0 buff/cache
# MiB Swap:   2048.0 total,   1024.0 free,   1024.0 used.   3072.0 avail Mem
# 
#     PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
#    1234 root      20   0  123456  45678  12345 S  10.0   0.5   0:05.23 systemd
#    5678 koush    20   0   98765  34567  23456 S   5.0   0.4   0:02.45 firefox
#    9012 koush    20   0   65432  23456  12345 S   2.0   0.3   0:01.23 gnome-shell

# Top commands (in interactive mode):
# q          - Quit
# k          - Kill process
# r          - Renice process
# c          - Show command path
# M          - Sort by memory
# P          - Sort by CPU
# 1          - Show all CPUs
```

### 6. Hands-on Practice Tasks

1. Run `top` and identify processes using most CPU
2. Press 'M' to sort by memory usage
3. Press 'k' to kill a process (try with a test process)
4. Use `top -u $USER` to see only your processes
5. Monitor system with `top` for 5 minutes

---

## kill - Terminate Processes

### 4. Commands with Explanation

```bash
kill [OPTIONS] PID
kill -l              # List all signals
kill -SIGTERM PID    # Graceful termination (default)
kill -SIGKILL PID    # Force kill (cannot be ignored)
kill -SIGSTOP PID    # Stop process
kill -SIGCONT PID   # Continue stopped process
```

### 5. Practical Terminal Examples

```bash
# Find process ID
ps -ef | grep firefox

# Graceful termination (15 = SIGTERM)
kill 12345

# Force kill (9 = SIGKILL)
kill -9 12345

# Kill all processes by name
killall firefox
killall -9 chrome

# Kill by pattern
pkill -f "python.*server"

# Send specific signal
kill -SIGUSR1 12345

# Common signals:
# 1   SIGHUP    - Hangup (reload config)
# 9   SIGKILL   - Force kill
# 15  SIGTERM   - Graceful termination
# 19  SIGSTOP   - Stop process
# 18  SIGCONT   - Continue stopped process
```

### 6. Hands-on Practice Tasks

1. Start a background process: `sleep 100 &`
2. Find its PID with `ps` or `jobs`
3. Gracefully kill it with `kill`
4. Start another and force kill with `kill -9`
5. Practice using `killall`

---

## 📦 Chapter 5: Package Management

### 1. Simple Concept Explanation

Package managers are like app stores for Linux. They handle installing, updating, and removing software. Instead of downloading installers from websites, you use commands to manage software from repositories.

### 2. Technical Explanation

Package managers work with packages (software bundles) that include:
- **Binary files**: The actual executable programs
- **Dependencies**: Other packages required to run the software
- **Configuration files**: Default settings
- **Metadata**: Package name, version, description

Popular package managers:
- **apt**: Debian, Ubuntu
- **yum/dnf**: Red Hat, CentOS, Fedora
- **pacman**: Arch Linux
- **zypper**: openSUSE

### 3. Real-World Example

- **System Updates**: Regular security patches
- **Installing Tools**: Penetration testing tools (nmap, metasploit)
- **Development**: Installing Python, Node.js, compilers
- **Containers**: Base images with pre-installed packages

---

## apt - Advanced Package Tool (Debian/Ubuntu)

### 4. Commands with Explanation

```bash
apt update             # Update package lists
apt upgrade            # Upgrade installed packages
apt install PACKAGE   # Install package
apt remove PACKAGE    # Remove package
apt purge PACKAGE     # Remove including config
apt search PACKAGE   # Search for package
apt show PACKAGE     # Show package info
apt list --installed # List installed packages
apt autoremove       # Remove unused dependencies
```

### 5. Practical Terminal Examples

```bash
# Update package lists (always do this first!)
sudo apt update

# Output:
# Hit:1 http://archive.ubuntu.com/ubuntu focal InRelease
# Reading package lists... Done
# Building dependency tree       
# Reading state information... Done
# 245 packages can be upgraded.

# Upgrade all packages
sudo apt upgrade

# Install a package
sudo apt install nmap

# Output:
# Reading package lists... Done
# Building dependency tree
# Reading state information... Done
# nmap is already the newest version (7.80+dfsg1-2).

# Install multiple packages
sudo apt install git curl wget

# Remove a package
sudo apt remove nmap

# Remove with configuration files
sudo apt purge nmap

# Search for packages
apt search "network scanner"
# Output:
# Sorting... Full Text Search...
# nmap/focal 7.80+dfsg1-2 amd64
#   Network scanner

# Show package information
apt show nmap

# List installed packages
apt list --installed | grep nmap

# Clean up
sudo apt autoremove
```

---

## yum/dnf - Yellowdog Updater Modified (RHEL/CentOS/Fedora)

### 4. Commands with Explanation

```bash
yum update             # Update packages
yum install PACKAGE    # Install package
yum remove PACKAGE    # Remove package
yum search PACKAGE    # Search for package
yum info PACKAGE      # Show package info
yum list installed    # List installed
yum autoremove       # Remove unused
dnf update            # Fedora equivalent
```

### 5. Practical Terminal Examples

```bash
# Update all packages
sudo yum update
# or on Fedora
sudo dnf update

# Install a package
sudo yum install httpd

# Install multiple packages
sudo yum install nmap tcpdump wireshark

# Remove package
sudo yum remove httpd

# Search for packages
yum search "network analyzer"

# List installed
yum list installed | grep nginx

# Show package info
yum info httpd
```

---

## 📖 Week 2 Practice Project

### Project: System Audit Script

Create a script that:
1. Lists top 5 CPU-consuming processes
2. Lists top 5 memory-consuming processes
3. Shows system uptime and load average
4. Lists recent failed login attempts
5. Shows disk usage

**Solution Script**:
```bash
#!/bin/bash

echo "=== System Audit Report ==="
echo "Generated: $(date)"
echo ""

echo "--- Top 5 CPU Processes ---"
ps aux --sort=-%cpu | head -6
echo ""

echo "--- Top 5 Memory Processes ---"
ps aux --sort=-%mem | head -6
echo ""

echo "--- System Uptime & Load ---"
uptime
echo ""

echo "--- Disk Usage ---"
df -h | grep -E "^/dev"
echo ""

echo "--- Failed Login Attempts ---"
if [ -f /var/log/auth.log ]; then
    grep "Failed password" /var/log/auth.log | tail -5
else
    echo "No auth.log found"
fi

echo ""
echo "=== Report Complete ==="
```

---

# WEEK 3: Bash Scripting Basics

---

## 💻 Chapter 6: Bash Scripting Fundamentals

### 1. Simple Concept Explanation

Bash scripting is like writing a recipe. You write a set of instructions that Linux follows step by step. Instead of typing commands one by one, you combine them into a script that runs automatically.

### 2. Technical Explanation

Bash (Bourne Again Shell) is a command interpreter that also provides programming capabilities:
- **Variables**: Store data
- **Conditionals**: Make decisions (if/else)
- **Loops**: Repeat actions
- **Functions**: Reusable code blocks
- **Input/Output**: Read from user, display output

### 3. Real-World Example

- **Automation**: Daily backup scripts
- **Monitoring**: System health checks
- **Security**: Intrusion detection scripts
- **DevOps**: Deployment automation
- **Forensics**: Log analysis scripts

---

## Variables

### 4. Commands with Explanation

```bash
# Variable assignment (NO spaces around =)
variable="value"
name="John"
age=25

# Access variable with $
echo $name
echo ${name}

# Special variables
$0      # Script name
$1-$9   # Arguments 1-9
$#      # Number of arguments
$*      # All arguments
$?      # Exit status of last command
$$      # Current process ID
```

### 5. Practical Terminal Examples

```bash
#!/bin/bash

# Basic variables
name="CyberStudent"
version=1

echo "Welcome $name!"
echo "Version: ${version}.0"

# Command substitution
current_date=$(date)
echo "Today is: $current_date"

# Arithmetic
a=10
b=5
sum=$((a + b))
echo "$a + $b = $sum"

# String operations
text="linux fundamentals"
echo ${text^}      # Capitalize first letter
echo ${text^^}    # All uppercase

# Special variables example
echo "Script name: $0"
echo "First argument: $1"
echo "Number of args: $#"
```

### 6. Hands-on Practice Tasks

1. Create a script that declares and prints variables
2. Use command substitution to store date in a variable
3. Perform arithmetic operations
4. Create variables from user input
5. Use special variables in a script

---

## User Input

### 4. Commands with Explanation

```bash
read [OPTIONS] VARIABLE
read -p "Prompt" VARIABLE    # Show prompt
read -s VARIABLE             # Silent input (passwords)
read -n CHARS VARIABLE       # Read N characters
read -t TIMEOUT VARIABLE     # Timeout
```

### 5. Practical Terminal Examples

```bash
#!/bin/bash

# Basic input
echo "What is your name?"
read name
echo "Hello, $name!"

# With prompt
read -p "Enter your username: " username
echo "Username: $username"

# Silent input (password)
read -s -p "Enter password: " password
echo ""
echo "Password entered (length: ${#password})"

# With timeout
read -t 5 -p "Quick question (5 sec timeout): " answer
echo "Answer: $answer"

# Multiple inputs
read -p "Enter name and age: " name age
echo "Name: $name, Age: $age"
```

### 6. Hands-on Practice Tasks

1. Create a script that asks for user's name and greets them
2. Create a login simulation with password input
3. Ask for multiple values in one line
4. Use timeout with read

---

## Conditionals - if/else

### 4. Commands with Explanation

```bash
if [ CONDITION ]; then
    # commands
elif [ CONDITION ]; then
    # commands
else
    # commands
fi

# Comparison operators
-eq    # Equal
-ne    # Not equal
-lt    # Less than
-le    # Less than or equal
-gt    # Greater than
-ge    # Greater than or equal

# String operators
=       # Equal
!=      # Not equal
-z      # Empty string
-n      # Not empty

# File operators
-e      # File exists
-f      # Regular file
-d      # Directory
-r/w/x  # Read/Write/Execute permission
```

### 5. Practical Terminal Examples

```bash
#!/bin/bash

# Basic if statement
age=18
if [ $age -ge 18 ]; then
    echo "You are an adult"
fi

# If-else
score=75
if [ $score -ge 90 ]; then
    echo "Grade: A"
elif [ $score -ge 80 ]; then
    echo "Grade: B"
elif [ $score -ge 70 ]; then
    echo "Grade: C"
else
    echo "Grade: F"
fi

# String comparison
name="admin"
if [ "$name" = "admin" ]; then
    echo "Welcome, administrator!"
fi

# File existence check
if [ -f "/etc/passwd" ]; then
    echo "Password file exists"
fi

# Directory check
if [ -d "/tmp" ]; then
    echo "Temp directory exists"
fi

# AND/OR conditions
age=25
citizen="yes"
if [ $age -ge 18 ] && [ "$citizen" = "yes" ]; then
    echo "You can vote"
fi

# NOT operator
if [ ! -f "file.txt" ]; then
    echo "File does not exist"
fi
```

### 6. Hands-on Practice Tasks

1. Create a script that checks if a file exists
2. Create a grade calculator using if-elif-else
3. Create a password strength checker
4. Create a script that checks system resources
5. Create a simple login checker

---

## Loops

### 4. Commands with Explanation

```bash
# For loop - C-style
for ((i=0; i<10; i++)); do
    echo $i
done

# For loop - in range
for i in {1..5}; do
    echo $i
done

# For loop - in list
for file in *.txt; do
    echo $file
done

# While loop
while [ CONDITION ]; do
    # commands
done

# Until loop
until [ CONDITION ]; do
    # commands
done
```

### 5. Practical Terminal Examples

```bash
#!/bin/bash

# For loop with range
echo "Counting 1 to 5:"
for i in {1..5}; do
    echo "Number: $i"
done

# For loop with list
echo "Text files:"
for file in *.txt; do
    echo "  $file"
done

# For loop - C style
for ((i=0; i<5; i++)); do
    echo "Count: $i"
done

# While loop - read file line by line
echo "Reading file line by line:"
while IFS= read -r line; do
    echo "$line"
done < file.txt

# While loop - countdown
countdown=5
while [ $countdown -gt 0 ]; do
    echo "T-minus $countdown"
    countdown=$((countdown - 1))
done
echo "Blast off!"

# Until loop
num=1
until [ $num -gt 3 ]; do
    echo "Number: $num"
    num=$((num + 1))
done
```

### 6. Hands-on Practice Tasks

1. Create a script that prints numbers 1-10 using a for loop
2. List all files in current directory using for loop
3. Create a countdown timer using while loop
4. Read a file line by line and display each line
5. Create a script that calculates factorial using for loop

---

## Functions

### 4. Commands with Explanation

```bash
# Function definition
function_name() {
    # commands
    return value
}

# Or with function keyword
function function_name {
    # commands
}

# Function with parameters
function greet() {
    echo "Hello, $1!"
}

# Return values via variables
get_sum() {
    result=$(( $1 + $2 ))
    echo $result
}
```

### 5. Practical Terminal Examples

```bash
#!/bin/bash

# Basic function
hello() {
    echo "Hello, World!"
}
hello

# Function with parameters
greet() {
    echo "Welcome, $1!"
}
greet "CyberStudent"

# Function with return value
add() {
    sum=$(( $1 + $2 ))
    return $sum
}
add 5 3
echo "Result: $?"

# Better: Return via echo
multiply() {
    result=$(( $1 * $2 ))
    echo $result
}
product=$(multiply 4 5)
echo "4 x 5 = $product"

# Function with local variables
calculate() {
    local a=$1
    local b=$2
    local sum=$((a + b))
    echo "Sum: $sum"
}
calculate 10 20

# Function with return status
check_file() {
    if [ -f "$1" ]; then
        return 0  # Success
    else
        return 1  # Failure
    fi
}

if check_file "test.txt"; then
    echo "File exists!"
else
    echo "File not found"
fi
```

### 6. Hands-on Practice Tasks

1. Create a function that prints a welcome message
2. Create a function that takes two numbers and returns their sum
3. Create a function to check if a file exists
4. Create multiple functions and call them from main
5. Create a calculator using functions

---

## 📖 Week 3 Practice Project

### Project: User Management Script

Create a script that:
1. Has a menu system
2. Creates a new user
3. Lists all users
4. Shows user information
5. Deletes a user

**Solution Script**:
```bash
#!/bin/bash

# User Management Script

show_menu() {
    echo "=== User Management Menu ==="
    echo "1. Create new user"
    echo "2. List all users"
    echo "3. Show user info"
    echo "4. Delete user"
    echo "5. Exit"
    echo -n "Choose option: "
}

create_user() {
    echo -n "Enter username: "
    read username
    sudo useradd -m $username
    echo "User $username created successfully!"
}

list_users() {
    echo "All users on system:"
    awk -F: '{print $1}' /etc/passwd
}

show_user_info() {
    echo -n "Enter username: "
    read username
    if id $username &>/dev/null; then
        id $username
        echo "Home: $(getent passwd $username | cut -d: -f6)"
    else
        echo "User not found!"
    fi
}

delete_user() {
    echo -n "Enter username to delete: "
    read username
    if id $username &>/dev/null; then
        sudo userdel -r $username
        echo "User $username deleted!"
    else
        echo "User not found!"
    fi
}

# Main loop
while true; do
    show_menu
    read choice
    case $choice in
        1) create_user ;;
        2) list_users ;;
        3) show_user_info ;;
        4) delete_user ;;
        5) echo "Goodbye!"; exit 0 ;;
        *) echo "Invalid option!" ;;
    esac
    echo ""
done
```

---

# WEEK 4: Advanced Scripting & Real-World Projects

---

## 🔍 Chapter 7: Regular Expressions

### 1. Simple Concept Explanation

Regular expressions (regex) are patterns used to match text. Think of them as advanced search patterns that can find specific text, validate formats (like email addresses), and extract information from text.

### 2. Technical Explanation

Regex uses special characters to define patterns:
- **Literals**: Regular characters (a, b, 1)
- **Metacharacters**: Special meaning (. * + ? ^ $ [] {} () | \)
- **Anchors**: Start/end of string (^ $)

### 3. Real-World Example

- **Log Analysis**: Find IP addresses in server logs
- **Data Extraction**: Extract emails from text
- **Input Validation**: Validate passwords, emails, phone numbers
- **Search & Replace**: Find and modify patterns in editors
- **Malware Detection**: Pattern matching for IOCs

### 4. Regex Quick Reference

| Pattern | Meaning |
|---------|---------|
| `.` | Any single character |
| `*` | Zero or more |
| `+` | One or more |
| `?` | Zero or one |
| `^` | Start of string |
| `$` | End of string |
| `[]` | Character class |
| `[^]` | Negated class |
| `{}` | Repetition |
| `()` | Group |
| `\|` | Alternation |
| `\` | Escape |

### 5. Practical Terminal Examples

```bash
# Basic grep with regex
echo "test123demo" | grep -E "[0-9]+"

# Find all numbers
echo "abc123def456" | grep -oE "[0-9]+"

# Match email pattern
echo "contact@example.com" | grep -E "[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}"

# IP address validation
echo "192.168.1.1" | grep -E "^([0-9]{1,3}\.){3}[0-9]{1,3}$"

# Extract dates
echo "2024-12-25" | grep -E "[0-9]{4}-[0-9]{2}-[0-9]{2}"

# Phone number pattern
echo "(555) 123-4567" | grep -E "^\([0-9]{3}\) [0-9]{3}-[0-9]{4}$"

# Using in files
grep -E "error|warning|critical" /var/log/syslog
grep -E "[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}" access.log
```

---

## sed - Stream Editor

### 4. Commands with Explanation

```bash
sed [OPTIONS] 'COMMAND' FILE
sed -i          # In-place edit
sed 's/old/new/'           # Replace first match
sed 's/old/new/g'          # Replace all
sed '/pattern/d'           # Delete matching lines
sed -n '1,5p'              # Print lines 1-5
sed '/pattern/p'           # Print matching
```

### 5. Practical Terminal Examples

```bash
# Replace text
sed 's/old/new/' file.txt

# Replace all occurrences
sed 's/word/WORD/g' file.txt

# Case insensitive replace
sed 's/old/new/gi' file.txt

# Delete lines containing pattern
sed '/error/d' logfile.txt

# Print specific lines
sed -n '5,10p' file.txt

# In-place editing
sed -i 's/old/new/g' file.txt

# Multiple commands
sed -e 's/old/new/' -e '/pattern/d' file.txt
```

---

## awk - Text Processing

### 4. Commands with Explanation

```bash
awk 'PATTERN {ACTION}' FILE
awk -F:           # Field separator
awk '{print $1}'  # Print first field
awk '$1 > 100'    # Conditional
BEGIN {}          # Before processing
END {}            # After processing
```

### 5. Practical Terminal Examples

```bash
# Print first column
awk '{print $1}' file.txt

# Use custom delimiter
awk -F: '{print $1}' /etc/passwd

# Print specific fields
awk -F: '{print $1, $6}' /etc/passwd

# Conditional printing
awk -F: '$3 >= 1000 {print $1}' /etc/passwd

# Using BEGIN and END
awk 'BEGIN {print "Users:"} {print $1} END {print "---"}' /etc/passwd

# Calculate sum
awk '{sum+=$1} END {print sum}' numbers.txt

# Print with formatting
awk '{printf "%-10s %s\n", $1, $2}' file.txt
```

---

## 📊 Chapter 8: System Administration Scripts

---

## 🖥️ System Monitoring Script

### 1. Simple Concept Explanation

System monitoring scripts help track system resources like CPU, memory, disk, and network. They're essential for maintaining system health and detecting anomalies.

### 2. Technical Explanation

This script uses Linux system files and commands:
- `/proc/meminfo`: Memory information
- `/proc/loadavg`: Load averages
- `df`: Disk usage
- `free`: Memory usage

### 3. Real-World Example

- **DevOps**: Monitor server health
- **Security**: Detect resource abuse
- **Performance**: Identify bottlenecks
- **Alerts**: Trigger alerts on thresholds

### 4. Solution Script

```bash
#!/bin/bash

# System Monitoring Script

echo "========================================="
echo "       SYSTEM MONITORING REPORT"
echo "========================================="
echo "Generated: $(date)"
echo ""

# System information
echo "--- System Info ---"
echo "Hostname: $(hostname)"
echo "Uptime: $(uptime -p)"
echo "Kernel: $(uname -r)"
echo ""

# CPU Load
echo "--- CPU Load Average ---"
load=$(uptime | awk -F'load average:' '{print $2}')
echo "Load: $load"
echo ""

# Memory Usage
echo "--- Memory Usage ---"
free -h | awk 'NR==1{print $0} NR==2{print $0}'
echo ""

# Disk Usage
echo "--- Disk Usage ---"
df -h | grep -E "^/dev" | awk '{print $1, $2, $3, $4, $5, $6}'
echo ""

# Top CPU Processes
echo "--- Top 5 CPU Processes ---"
ps aux --sort=-%cpu | head -6 | tail -5 | awk '{print $11, $3"%", $4"%"}'
echo ""

# Top Memory Processes
echo "--- Top 5 Memory Processes ---"
ps aux --sort=-%mem | head -6 | tail -5 | awk '{print $11, $4"%", $3"%"}'
echo ""

# Network Connections
echo "--- Network Connections ---"
echo "Established: $(netstat -an 2>/dev/null | grep ESTABLISHED | wc -l)"
echo "Listening: $(netstat -an 2>/dev/null | grep LISTEN | wc -l)"
echo ""

echo "========================================="
```

---

## 💾 Backup Script

### 1. Simple Concept Explanation

Backup scripts automate the process of copying important files to a safe location. This is critical for disaster recovery and protecting against data loss.

### 2. Technical Explanation

The backup script:
- Creates timestamped directories
- Uses `rsync` or `cp` for file copying
- Compresses backups to save space
- Provides logging for verification

### 3. Real-World Example

- **System Admins**: Daily database backups
- **DevOps**: Application backup to S3
- **Security**: Preserving evidence
- **Compliance**: Data retention policies

### 4. Solution Script

```bash
#!/bin/bash

# Automated Backup Script

# Configuration
SOURCE_DIR="/home/koush/Documents"
BACKUP_DIR="/backup"
DATE=$(date +%Y%m%d_%H%M%S)
BACKUP_NAME="backup_$DATE"
LOG_FILE="/var/log/backup.log"

# Log function
log() {
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] $1" | tee -a $LOG_FILE
}

# Check if source exists
if [ ! -d "$SOURCE_DIR" ]; then
    log "ERROR: Source directory not found!"
    exit 1
fi

# Create backup directory
log "Starting backup..."
mkdir -p "$BACKUP_DIR/$BACKUP_NAME"

# Perform backup
if cp -r "$SOURCE_DIR" "$BACKUP_DIR/$BACKUP_NAME"; then
    log "Backup completed successfully!"
    
    # Compress backup
    log "Compressing backup..."
    tar -czf "$BACKUP_DIR/${BACKUP_NAME}.tar.gz" -C "$BACKUP_DIR" "$BACKUP_NAME"
    
    # Clean up uncompressed
    rm -rf "$BACKUP_DIR/$BACKUP_NAME"
    
    log "Backup compressed: ${BACKUP_NAME}.tar.gz"
    
    # Show backup size
    SIZE=$(du -h "$BACKUP_DIR/${BACKUP_NAME}.tar.gz" | cut -f1)
    log "Backup size: $SIZE"
    
    # List recent backups
    log "Recent backups:"
    ls -lh "$BACKUP_DIR" | tail -5
    
else
    log "ERROR: Backup failed!"
    exit 1
fi

log "=== Backup Complete ==="
```

---

## 📊 Disk Usage Checker

### 1. Simple Concept Explanation

Disk usage checkers help identify which directories are consuming the most space. This is essential for managing storage and cleaning up unnecessary files.

### 2. Technical Explanation

This script uses:
- `du`: Disk usage analyzer
- `sort`: Order by size
- `head/tail`: Limit output

### 3. Real-World Example

- **System Admin**: Clean up old logs
- **DevOps**: Monitor container storage
- **Security**: Find suspicious large files
- **Forensics**: Identify data storage

### 4. Solution Script

```bash
#!/bin/bash

# Disk Usage Analyzer

echo "========================================="
echo "       DISK USAGE ANALYSIS"
echo "========================================="
echo ""

# Overall disk usage
echo "--- Overall Disk Usage ---"
df -h | grep -E "^/dev" | awk '{print "Filesystem: " $1 "\nTotal: " $2 "\nUsed: " $3 "\nAvailable: " $4 "\nUse%: " $5 "\nMount: " $6}'
echo ""

# Largest directories in /var
echo "--- Largest Directories in /var ---"
du -sh /var/* 2>/dev/null | sort -rh | head -10
echo ""

# Largest directories in /home
echo "--- Largest Directories in /home ---"
du -sh /home/* 2>/dev/null | sort -rh | head -10
echo ""

# Largest files
echo "--- Top 10 Largest Files ---"
find / -type f -size +100M 2>/dev/null | xargs du -h 2>/dev/null | sort -rh | head -10
echo ""

# Log file sizes
echo "--- Log File Sizes ---"
du -sh /var/log/* 2>/dev/null | sort -rh | head -10
echo ""

echo "========================================="
```

---

## 📋 Log Analyzer

### 1. Simple Concept Explanation

Log analyzers help security professionals and system administrators identify issues, attacks, and anomalies by parsing system logs.

### 2. Technical Explanation

This script analyzes:
- Authentication logs (`/var/log/auth.log`)
- System logs (`/var/log/syslog`)
- Common attack patterns
- Failed login attempts

### 3. Real-World Example

- **Security**: Detect brute force attacks
- **Forensics**: Investigate incidents
- **Compliance**: Audit access
- **Monitoring**: Alert on anomalies

### 4. Solution Script

```bash
#!/bin/bash

# Log Analyzer Script

echo "========================================="
echo "         LOG ANALYSIS REPORT"
echo "========================================="
echo "Generated: $(date)"
echo ""

# Log file location (adjust for your distro)
LOG_FILE="/var/log/syslog"
AUTH_LOG="/var/log/auth.log"

if [ ! -f "$LOG_FILE" ]; then
    LOG_FILE="/var/log/messages"
fi

echo "--- Failed Login Attempts ---"
if [ -f "$AUTH_LOG" ]; then
    grep "Failed password" "$AUTH_LOG" | tail -10
else
    grep "Failed" "$LOG_FILE" | tail -10
fi
echo ""

echo "--- Successful Root Logins ---"
grep "session opened for root" "$LOG_FILE" 2>/dev/null | tail -5
echo ""

echo "--- Recent Errors ---"
grep -i "error" "$LOG_FILE" | tail -10
echo ""

echo "--- Recent Warnings ---"
grep -i "warn" "$LOG_FILE" | tail -10
echo ""

echo "--- Service Restarts ---"
grep -i "systemd\|started\|stopped" "$LOG_FILE" | tail -10
echo ""

echo "--- SSH Connections ---"
grep "sshd" "$LOG_FILE" | tail -10
echo ""

echo "--- Disk Space Warnings ---"
grep -i "no space\|disk full" "$LOG_FILE" 2>/dev/null
echo ""

echo "========================================="
```

---

## 🎯 Month 1 Final Project

### Project: Security Dashboard Script

Create a comprehensive script that combines all learned concepts:

```bash
#!/bin/bash

# Comprehensive Security Dashboard

# Colors for output
RED='\033[0;31m'
GREEN='\033[0;32m'
YELLOW='\033[1;33m'
NC='\033[0m' # No Color

echo "╔════════════════════════════════════════╗"
echo "║     SECURITY DASHBOARD - MONTH 1        ║"
echo "╚════════════════════════════════════════╝"
echo ""

# System Info
echo -e "${GREEN}=== SYSTEM INFORMATION ===${NC}"
echo "Hostname: $(hostname)"
echo "IP Address: $(hostname -I | awk '{print $1}')"
echo "Uptime: $(uptime -p)"
echo ""

# Security Checks
echo -e "${GREEN}=== SECURITY CHECKS ===${NC}"

# 1. Check for root account access
echo -n "Root account access: "
if [ "$(sudo -n true 2>/dev/null; echo $?)" -eq 0 ]; then
    echo -e "${GREEN}YES (sudo access)${NC}"
else
    echo -e "${YELLOW}No sudo access${NC}"
fi

# 2. Failed logins
failed_logins=$(grep "Failed password" /var/log/auth.log 2>/dev/null | tail -20 | wc -l)
echo "Failed login attempts (recent): $failed_logins"
if [ $failed_logins -gt 10 ]; then
    echo -e "${RED}⚠️ WARNING: Many failed logins!${NC}"
fi

# 3. Open ports
echo ""
echo "Open Network Ports:"
netstat -tuln 2>/dev/null | grep LISTEN | awk '{print $4, $7}' | head -10

# 4. Running services
echo ""
echo "Active Services:"
systemctl list-units --type=service --state=running | grep ".service" | head -10

# 5. System resources
echo ""
echo "System Resources:"
echo "CPU Load: $(uptime | awk -F'load average:' '{print $2}')"
free -h | awk 'NR==2{print "Memory: " $3 "/" $2}'

# 6. Disk usage
echo ""
echo "Disk Usage:"
df -h | grep -E "^/dev" | awk '{print $1 ": " $5 " used"}'

# 7. Recent system events
echo ""
echo "Recent System Events:"
journalctl -n 5 --no-pager 2>/dev/null | awk '{print $1, $2, $3, $5, $6, $7}' || \
    tail -5 /var/log/syslog | awk '{print $1, $2, $3, $5, $6}'

echo ""
echo "╔════════════════════════════════════════╗"
echo "║        DASHBOARD COMPLETE              ║"
echo "╚════════════════════════════════════════╝"
```

---

# 📚 Essential Linux Commands for Cybersecurity

## Must-Know Commands

| Category | Commands |
|----------|----------|
| **File Operations** | ls, cd, pwd, mkdir, rm, cp, mv, cat, less, head, tail |
| **Search** | grep, find, locate, which |
| **Permissions** | chmod, chown, chgrp, umask |
| **Process** | ps, top, htop, kill, killall, pkill |
| **Networking** | netstat, ss, ip, ping, traceroute, curl, wget |
| **Text Processing** | awk, sed, cut, sort, uniq, wc |
| **System Info** | uname, df, du, free, uptime |
| **Logs** | journalctl, tail, less, grep |
| **Archive** | tar, zip, unzip, gzip |
| **SSH** | ssh, scp, sftp |
| **Package Mgmt** | apt, yum, dnf |
| **User Management** | useradd, usermod, userdel, passwd, sudo |

---

# 🎓 Tips to Build Strong Linux Skills Quickly

## 1. Practice Daily
- Spend 30 minutes daily in the terminal
- Avoid GUI for routine tasks
- Use Linux as your primary OS

## 2. Learn Shortcuts
- `Ctrl+C`: Cancel current command
- `Ctrl+Z`: Suspend process
- `Ctrl+A/E`: Move to start/end of line
- `Ctrl+U/K`: Cut from cursor to beginning/end
- `Tab`: Auto-complete
- `Ctrl+R`: Search command history

## 3. Understand the Manual
```bash
man command_name    # Full documentation
command_name --help # Quick help
```

## 4. Use Version Control
```bash
git init
git add .
git commit -m "Initial commit"
```

## 5. Build Projects
- System monitoring dashboard
- Log analyzer
- Backup automation
- User management system

## 6. Practice Security
- Use `chmod` properly
- Understand file ownership
- Audit permissions regularly
- Check logs frequently

## 7. Join Communities
- Linux forums
- Stack Overflow
- Reddit r/linux
- GitHub for open-source security tools

## 8. Read Source Code
- Study scripts in `/etc/init.d/`
- Examine scripts in `/usr/bin/`
- Contribute to open source

## 9. Use Linux for Everything
- Set up a home lab
- Practice in VMs
- Use TryHackMe or HackTheBox

## 10. Never Stop Learning
- Linux is vast—keep exploring
- Read man pages regularly
- Follow Linux security blogs

---

# 📋 Monthly Assessment

## Self-Test Questions

1. What is the function of /etc directory?
2. Explain the difference between chmod 755 and chmod 700
3. How do you find all SUID files on a system?
4. Write a script to monitor failed SSH login attempts
5. What is the difference between grep and egrep?
6. How do you kill a zombie process?
7. Explain the purpose of the sticky bit
8. Write a function in bash that calculates factorial

## Practical Challenges

1. **Challenge 1**: Set up a home lab with 2 Linux VMs
2. **Challenge 2**: Write a script that performs daily system backup
3. **Challenge 3**: Create a log monitoring alert system
4. **Challenge 4**: Build a simple IDS (Intrusion Detection System)
5. **Challenge 5**: Automate user creation with proper permissions

---

# ✅ Conclusion

Congratulations on completing Month 1 of your Linux & Bash Fundamentals journey!

## What You Should Know Now:

✓ Linux filesystem hierarchy  
✓ Basic file operations  
✓ File permissions and ownership  
✓ Process management  
✓ Package management  
✓ Bash scripting basics  
✓ Regular expressions  
✓ System monitoring scripts  
✓ Log analysis basics  

## What's Next (Month 2):

- Advanced bash scripting
- Cron jobs and scheduling
- Network configuration
- Firewall basics (iptables, ufw)
- SELinux/AppArmor
- Container basics (Docker)
- Basic network security

---

**Remember**: The key to mastering Linux is practice. Spend time in the terminal every day, break things, fix them, and never stop exploring!

*Good luck on your cybersecurity journey!* 🔐🐧

---

*Document Version: 1.0*  
*Created for: Cyber Security Student*  
*Study Duration: Month 1 (4 weeks)*


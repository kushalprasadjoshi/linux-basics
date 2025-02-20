# Basic Linux

Access the [Basic Linux Handbook](/resources/linux-basics-handbook.pdf) here.

[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)](https://github.com/KushalPrasadJoshi/linux-basics/pulls)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)

## Table of Contents
1. [Users in Linux](#users-in-linux)
2. [Text Editors](#text-editors)
    - [Vim](#vim)
3. [Basic File System](#basic-file-system)
4. [Paths in Linux](#paths-in-linux)
5. [Terminal Shortcuts](#terminal-shortcuts)
6. [Basic Linux Commands](#basic-linux-commands)
    - [Introducing Commands](#introducing-commands)
    - [Working With Directories](#working-with-directories)
    - [Working With Files](#working-with-files)
7. [Chmod Calculator](#chmod-calculator)
8. [Executing Software](#executing-software)
9. [Process Manipulation](#process-manipulation)
10. [Changing Hostname](#changing-hostname)
11. [Changing Domain Name](#changing-domain-name)
12. [Configuring Apache Server](#configuring-apache-server)
13. [Changing Apache Port](#changing-apache-port)
14. [Software Installation Without Apt](#software-installation-without-apt)
    - [From Debian Files](#from-debian-files)
    - [From GitHub](#from-github)
15. [Error Resolving in Linux Apt](#error-resolving-in-linux-apt)
    - [Check for Root Access](#check-for-root-access)
    - [Check Your Connection](#check-your-connection)
    - [Editing the Sources List](#editing-the-sources-list)
    - [Using Fix-Broken](#using-fix-broken)
    - [Removing the Apt List](#removing-the-apt-list)
16. [Running Multiple Commands in a Single Terminal](#running-multiple-commands-in-a-single-terminal)
    - [Semicolon (`;`)](#semicolon-)
    - [And (`&&`)](#and-)
    - [Or (`||`)](#or-)

## Users in Linux
- **Regular User:** Home directory
- **Root User:** Full access [ADMIN] (the superuser of the system)
- **Service User:** Service access (for servers)

> **Note:**  
> If a regular user gains root access, they can use `sudo` before any command to utilize root privileges.  
> To get full root access, use the `sudo su` command.

## Text Editors

### Vim
Vim is a popular text editor in Linux. Common commands include:
- **I:** Enter insert mode
- **esc:** Exit insert mode
- **:wq:** Exit and save changes
- **:q!:** Exit without saving changes

## Basic File System
- **/bin:** Basic programs (e.g., `ls`, `cd`, `mv`)
- **/sbin:** System programs (e.g., `fdisk`, `sysctl`, `mkfs`)
- **/etc:** Configuration files (default values)
- **/temp:** Temporary files
- **/usr/bin:** Applications (e.g., `apt`, `nmap`)
- **/usr/share:** Application support and data files
- **/home:** Personal directories of users
- **/root:** Home directory of the superuser [ADMIN]

## Paths in Linux
Below is an example of a directory structure:
```
Desktop
├── IntelliJ idea.desktop
├── Joshi
├── Kushal
│   ├── Birthday
│   └── Happy
│       └── hero.txt
├── Prasad
│   ├── Hello
│   └── Sir
├── firefox-esr.desktop
└── libreoffice-startcenter.desktop
```

> **Note:**  
> - `gedit cd /Desktop/Kushal/Happy/hero.txt` is an absolute path (accessible from anywhere).  
> - `gedit hero.txt` is a relative path (requires you to be in the `Happy` directory, for example).

## Terminal Shortcuts
- **Tab:** Autocomplete names  
- **Double Tab:** Open selection menu  
- **Ctrl + C:** Abort the current process  
- **Ctrl + L:** Clear the terminal (same as running `clear`)  
- **Ctrl + D:** Exit the terminal (same as the `exit` command)  
- **Ctrl + Alt + D:** Minimize all terminals/commands (toggle)  
- **Ctrl + U:** Clear the current line  
- **Ctrl + Z:** Suspend the current process to the background  
- **Ctrl + A:** Move the cursor to the beginning of the line  
- **Ctrl + E:** Move the cursor to the end of the line  
- **Shift + Ctrl + C:** Copy text in the terminal  
- **Shift + Ctrl + V:** Paste text in the terminal

## Basic Linux Commands

### Introducing Commands
- **help:** Shows basic commands and their uses.
- **man:** Displays the complete manual for a command or program.
- **ls:** Lists all files and folders in a directory.
  - `ls -a` shows hidden files and folders.
  - `ls -l` displays permissions, dates, and user/group information.
  - `ls -R` lists directories recursively.
- **cd:** Change directory.
- **pwd:** Show the present working directory.
- **clear:** Clear the terminal screen.
- **history:** Displays the history of commands.
- **echo / printf:** Print text to the terminal.
- **mkdir:** Create a new directory.

> **Note:**  
> - Prepend a filename with a dot (e.g., `.Kushal`) to make it hidden.  
> - Use `cd ..` to move up one directory.  
> - To create a directory with spaces, use quotes (e.g., `mkdir "Kushal Prasad Joshi"`) or escape the spaces (e.g., `mkdir Kushal\ Prasad\ Joshi`).

### Working With Directories
- **dir:** Same as `ls`.
- **mkdir:** Create a directory.
- **cp:** Copy a file or folder.
- **mv:** Move a file or folder.
- **rm:** Remove (delete) a file or folder.
  - Use `rm -r folder` to remove directories recursively.

### Working With Files
- **sudo su root:** Grant root privileges.
- **cat:** Display the contents of a file.
- **nano:** Command-line text editor.
- **gedit:** Graphical text editor.
- **chmod:** Change file or directory permissions.
  - Example: `chmod +wxr filename` adds permissions, while `chmod -wxr filename` removes them.
  
> **Note:**  
> In newer Linux versions, you can often use `sudo su` instead of `sudo su root`.

## Chmod Calculator
- **Usage:**  
  ```bash
  chmod filename ch-number
  ```
  Changes file permissions based on the given numeric mode.  
- **Change Group:**  
  Use the `chgroup` command as needed.

> **Note:**  
> The format for permissions is typically Owner, Group, Public.

## Executing Software
- **./filename:** Execute a shell file.
- **bash filename:** Run a shell script.
- **apt-get update:** Update the packages list.
- **apt-get upgrade:** Upgrade all installed software.
- **apt-get install software_name:** Install specific software.
- **apt-get update software_name:** Update packages for a particular software.
- **apt-get upgrade software_name:** Upgrade a particular software.

> **Note:**  
> - `apt-get update` refreshes the package store.  
> - `apt-get upgrade` updates all packages and tools.  
> - In newer Linux distributions, the `apt` command is often used in place of `apt-get`.

## Process Manipulation
- **top:** Displays processes consuming the most resources.
- **ps:** Shows the current processes.
  - `ps -a` includes background processes.
- **kill:** Terminate a process manually.
- **w:** Shows who is logged on and what they are doing.
- **whoami:** Displays the current user's username.
- **touch:** Create an empty file.

> **Note:**  
> - Use `kill PID` to terminate a process by its process ID (PID).  
> - `Ctrl + C` can stop an ongoing process in the terminal.

## Changing Hostname
1. Gain root access:
    ```bash
    sudo su
    ```
2. Navigate to the configuration directory:
    ```bash
    cd /etc
    ```
3. Edit the hostname file:
    ```bash
    gedit hostname
    ```
4. Restart the system:
    ```bash
    reboot
    ```

## Changing Domain Name
1. Gain root access:
    ```bash
    sudo su
    ```
2. Navigate to the configuration directory:
    ```bash
    cd /etc
    ```
3. Edit the hosts file:
    ```bash
    gedit hosts
    ```
4. Start the Apache server:
    ```bash
    service apache2 start
    ```
5. Access your domain by entering your IP address and port (e.g., `Kushal:80`) in a browser.

## Configuring Apache Server
1. Start the Apache server:
    ```bash
    service apache2 start
    ```
2. Navigate to the web directory:
    ```bash
    cd /var/www/html/
    ```
3. Edit the index page:
    ```bash
    sudo gedit index.html
    ```

> **Note:**  
> Use `ifconfig` to find your IP address (e.g., `inet 192.168.78.141`).  
> Apache typically runs on port 80 by default.

## Changing Apache Port
1. Navigate to the configuration directory:
    ```bash
    cd /etc/apache2
    ```
2. Edit the ports configuration file:
    ```bash
    gedit ports.conf
    ```
    Change the port number (e.g., from 80 to 8080).
3. Restart Apache:
    ```bash
    service apache2 restart
    ```
4. Verify by accessing your IP with the new port (e.g., `192.168.78.141:8080`).

## Software Installation Without Apt

### From Debian Files
1. Navigate to the Downloads folder:
    ```bash
    cd Downloads
    ```
2. Install the package:
    ```bash
    dpkg -i filename
    ```

### From GitHub
1. Clone the repository:
    ```bash
    git clone url
    ```
2. Navigate to the folder:
    ```bash
    cd folder
    ```
3. Execute the file:
    ```bash
    ./exefile
    ```

> **Note:**  
> Always follow the installation instructions provided on GitHub for best results.

## Error Resolving in Linux Apt

### Check for Root Access
- Ensure you have root privileges by using `sudo su`.

### Check Your Connection
- Verify that you are connected to the internet.

### Editing the Sources List
1. Navigate to the apt configuration directory:
    ```bash
    cd /etc/apt
    ```
2. Edit the sources list:
    ```bash
    gedit sources.list
    ```
    Make sure that important lines are not commented out (lines starting with `#`).
3. Update the package list:
    ```bash
    apt update
    ```

### Using Fix-Broken
```bash
apt-get install --fix-broken
```

### Removing the Apt List
```bash
rm -rf /var/lib/apt/list/*
apt-get update
```

## Running Multiple Commands in a Single Terminal

### Semicolon (`;`)
- The second command will run regardless of the success of the first command.  
  **Example:**
  ```bash
  cd ; ls
  ```

### And (`&&`)
- The second command runs only if the first command is successful.  
  **Example:**
  ```bash
  cd && ls
  ```

### Or (`||`)
- The second command runs only if the first command fails.  
  **Example:**
  ```bash
  cd || ls
  ```

## License
This repository is licensed under an **All Rights Reserved** license. You may fork and use the code for personal, educational, and non-commercial purposes only. Modifying, distributing, or using the code for commercial purposes is strictly prohibited without explicit permission. Please refer to the [LICENSE](LICENSE) file for further details.

---

Go to [Table of Contents](#table-of-contents).
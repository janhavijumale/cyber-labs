# 🪟 Windows Fundamentals – Part 1

---

## 🖼️ GUI vs CLI
- Windows uses a **Graphical User Interface (GUI)** by default
- CLI in Windows = **Command Prompt** or **PowerShell**

---

## 💾 File Systems

### NTFS – New Technology File System
- Default file system in modern Windows
- **Journaling** file system – can auto-repair using logs
- Supports:
  - Files > 4GB
  - File/folder **permissions**
  - **Compression**
  - **Encryption (EFS)**

### FAT32 / FAT16
- Older file system (used in USBs, SD cards, etc.)
- Does **not** support:
  - Journaling
  - File-level permissions
  - Large files > 4GB

📍 **To check file system in Windows**:
- Right-click on **C:\ Drive → Properties** → See file system type

---

## 🔐 NTFS File & Folder Permissions

- NTFS allows you to grant or deny access using these permission levels:
  - Full Control
  - Modify
  - Read & Execute
  - List Folder Contents
  - Read
  - Write

📍 **To view permissions**:
1. Right-click file/folder → Properties
2. Go to **Security tab**
3. Select the user/group to view specific permissions

---

## 📦 Alternate Data Streams (ADS)

- Feature of NTFS that allows **multiple data streams** in a single file
- Every file has at least one data stream: `$DATA`
- **ADS is hidden** in Windows Explorer by default

🛡️ **Security Insight**:
- Malware can use ADS to **hide data**
- Legit use: downloaded files from the Internet store metadata in ADS
- You can view ADS using **PowerShell** or third-party tools

---
## 🗂️ Windows System Folder – `C:\Windows`

- The default folder for the **Windows Operating System** is: C:\Windows
- However, it can reside on **other drives** or in **other directories**.

---

## 🔄 Environment Variable: `%WINDIR%`

- `%WINDIR%` is the **system environment variable** that always points to the current Windows directory (no matter its location).
- ✅ Example usage in Command Prompt:
     echo %WINDIR%


🧠 **Environment variables** store system-level info like:
- OS paths
- Temp folder locations
- Processor count
- User profile paths

---
---

## 🧠 What is an Environment Variable?

An **environment variable** is like a **shortcut name** that stores information about your system.  
It helps the **operating system, scripts, or programs** know important locations or settings — **without hardcoding values**.

---

### 🧾 Think of it like:

> `%windir%` → "Hey system, where is Windows installed?"  
> `%userprofile%` → "Where is this user’s personal folder?"  
> `%temp%` → "Where should temporary files be stored?"

---

## 🖥️ Why Environment Variables Are Useful

- Help software run on **any Windows machine** (flexible, portable)
- Save time and avoid errors (no need to write full paths)
- Allow scripts to adapt to different users or systems

---

### 🔧 Common Environment Variables in Windows:

| Variable         | What it Represents        | Example Value                             |
|------------------|----------------------------|--------------------------------------------|
| `%windir%`        | Windows directory           | `C:\Windows`                                |
| `%userprofile%`   | Current user folder         | `C:\Users\Username`                          |
| `%temp%`          | Temp files directory        | `C:\Users\Username\AppData\Local\Temp`       |
| `%programfiles%`  | Default install location    | `C:\Program Files`                          |
| `%path%`          | Executable search paths     | (used by cmd/PowerShell to find commands)   |

---

## 🛡️ Why Cybersecurity Professionals Care

- Malware can abuse environment variables to **find paths or hide files**
- Analysts use them to **write flexible detection scripts**
- Penetration testers use them in payloads to **adapt to the system**

---

## 📁 Inside the Windows Folder

- The Windows folder contains many subfolders. One of the most important is:

### 🔧 `System32` Folder
- Contains **critical OS files**, drivers, libraries, and system utilities
- Many tools used in Windows operations and cybersecurity tasks reside here

⚠️ **Caution**:
- Accidentally modifying or deleting files in `System32` can render Windows **unusable**

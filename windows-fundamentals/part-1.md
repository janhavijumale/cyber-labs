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


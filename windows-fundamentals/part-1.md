
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

  ![image](https://github.com/user-attachments/assets/e221551f-1986-43d9-998d-ec4a5e482565)


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

---

## 👤 User Account Types in Windows

Windows systems support two main types of local user accounts:

| Account Type     | Permissions & Capabilities                                      |
|------------------|---------------------------------------------------------------|
| Administrator     | Full system access. Can install programs, create/delete users, change system settings. |
| Standard User     | Limited to modifying their own files. Cannot install apps or change system-level settings. |

🧠 **To check or change account type:**
1. Open **Settings > Accounts > Other users**
2. Select a user → Click **Change account type**
3. Choose between `Standard User` or `Administrator`

📌 Standard Users **cannot** see the "Add someone else to this PC" option.

---

## 🗂️ User Profile Folders

- When a new user logs into Windows for the first time, Windows automatically creates a **user profile**.
- Default path:  
C:\Users<username>


Each user profile contains standard folders:
- `Desktop`
- `Documents`
- `Downloads`
- `Music`
- `Pictures`

🔁 The **User Profile Service** runs on first login to create this profile.

---

## 🧰 Local Users and Groups Management

You can manage users and groups using the `lusrmgr.msc` tool.

📌 To open:
1. Press `Win + R` → Type `lusrmgr.msc`

You will see two folders:
- **Users** – lists all local users
- **Groups** – lists predefined local groups (like Administrators, Users, Guests, etc.)

👥 Users can be added to one or more groups to inherit group-level permissions.

---

## 🔍 How to View Existing Users

1. Click the **Start Menu**
2. Search for **Other User** → Open **System Settings > Other users**
3. From there, you can view and manage all existing accounts

---

## 🛡️ User Account Control (UAC)

### 🔍 Why UAC Was Introduced:
- Most home users run as **local administrators**, which poses security risks.
- Malware run under an admin account can make **system-wide changes**.
- Microsoft introduced **User Account Control (UAC)** in Windows Vista to reduce this risk.

---

### ⚙️ How UAC Works:

| Situation | Behavior |
|----------|----------|
| 🧑 Logged in as Admin | OS runs apps without elevated rights by default |
| 🔐 Admin Action Required | UAC prompts for confirmation |
| 👤 Logged in as Standard User | UAC prompts for **admin credentials** |

- ✅ This prevents apps from making unauthorized system changes.
- ❌ UAC does **not apply** to the built-in Administrator account (by default).

---

### 🖼️ UAC in Action:

- When installing a program, if UAC elevation is needed:
  - A **shield icon** appears on the program’s icon.
  - A **UAC dialog box** appears asking for permission (or admin credentials if you’re a standard user).
  
---

---

## ⚙️ Settings vs Control Panel in Windows

On a Windows system, the two primary locations to configure system settings are:

| Menu           | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| **Control Panel** | Classic interface used for advanced and legacy system settings              |
| **Settings**       | Modern interface introduced in Windows 8, now the default for most user-level tasks |

---

### 🖥️ Evolution of System Configuration:
- **Control Panel** has long been the go-to location for:
  - Adding/removing hardware (e.g., printers)
  - Uninstalling programs
  - Accessing advanced settings
- **Settings Menu** was introduced with **Windows 8**, designed with touch interfaces in mind.
  - More **user-friendly** and **streamlined**
  - Now the **default** interface for many configurations in Windows 10 and 11

---

### 🔄 How They Work Together:
- Some tasks start in **Settings** and redirect to the **Control Panel**
- 🧭 Example:  
  1. Open **Settings** → Network & Internet  
  2. Click on **Change adapter options**  
  3. This opens the **Control Panel's** Network Connections window

---

### 🔍 Best Practice: Search for Settings
If unsure where a setting is located:
- Use the **Start Menu** search (e.g., search for “wallpaper”)
- Windows will show results from **both** Settings and Control Panel
- Clicking the **best match** opens the correct menu directly

---

✅ Summary:
- Use **Settings** for day-to-day configurations
- Use **Control Panel** for **advanced** or **legacy** options

---

## 🧰 Task Manager in Windows

The **Task Manager** provides detailed information about the applications and processes running on a system.

### 🧭 How to Access:
- Right-click the taskbar → Select **Task Manager**
- Shortcut: `Ctrl + Shift + Esc`

---

### 🪟 First View (Simple Mode):
Shows only currently open applications (not background processes). You can:
- 🟥 **End Task**: Force-close unresponsive apps
- 🧠 Useful if the app is frozen and won't close normally

---

### 📜 Right-Click Options on an App:

| Option             | Description |
|--------------------|-------------|
| 🔁 **Switch To**         | Brings the selected app window to focus |
| ❌ **End Task**          | Terminates the selected process |
| ➕ **Run New Task**      | Open a new program or file (like a mini Run window) |
| 📌 **Always On Top**     | Keeps Task Manager above all windows |
| 📂 **Open File Location**| Opens the location of the app’s `.exe` file |
| 🔍 **Search Online**     | Bing search for the program name — useful to identify unknown apps |
| ⚙️ **Properties**         | Opens file properties to view version, compatibility settings, etc. |

---

### 📊 Task Manager in System Tray
- Displays CPU usage as an icon
- Hover to see quick stats (CPU, RAM, Disk, Network)
- Enable: `Options > Hide When Minimized` to keep it in system tray without showing on taskbar

---

### 🧩 Tabs in Full View

| Tab             | Description |
|------------------|-------------|
| **Processes**     | Lists running apps & background processes |
| **Performance**   | Real-time graphs for CPU, Memory, Disk, Network |
| **App History**   | Resource usage per app (for Store apps) |
| **Startup**       | Manage apps that auto-start with Windows |
| **Users**         | View active user sessions and their resource usage |
| **Details**       | Advanced view of all running processes |
| **Services**      | Start/Stop system services |

---

✅ Summary:
Task Manager is an essential tool for monitoring system performance, troubleshooting, and managing running applications.




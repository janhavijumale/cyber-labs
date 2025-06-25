## 🛠️ System Configuration Utility (MSConfig)

The **System Configuration utility (MSConfig)** is a tool used primarily for **advanced troubleshooting** and **diagnosing startup issues**.

> 📌 Note: Requires **administrator privileges** to open.

---

### 📥 How to Open:
- Start Menu → Search for `msconfig`
- Run dialog → Type `msconfig`

---

### 🧩 Tabs in MSConfig

| **Tab**     | **Purpose** |
|-------------|-------------|
| **General** | Select which devices/services load at boot. Options: Normal, Diagnostic, Selective. |
| **Boot**    | Configure various **boot options** for the OS. |
| **Services**| Lists all system **services** (running or stopped). |
| **Startup** | *Deprecated here*. Use **Task Manager** instead for managing startup programs. |
| **Tools**   | Run various **system tools** with command references provided. |

---

### 📝 Notes:

- **Startup Tab**: Microsoft recommends managing startup apps through **Task Manager** (`taskmgr`).
- **Tools Tab**: Contains a list of system utilities. You can:
  - Use the command listed under "Selected Command"
  - Run via **Run prompt**, **Command Prompt**, or click **Launch**

---
## 🧰 System Configuration Tools – Continued

The `System Configuration (msconfig)` panel gives access to a range of system utilities. Below are the key tools and their functions:

---

### 🖥️ Computer Management (`compmgmt`)

Divided into 3 main sections:

| Section | Description |
|--------|-------------|
| **System Tools** | Manage system behavior and users. |
| **Storage** | Manage disk partitions and drives. |
| **Services and Applications** | Control services and applications running in the background. |

---

### 🔁 System Tools

#### 📅 Task Scheduler
- Automates tasks like running scripts or apps on a schedule.
- Tasks can trigger on **login, logoff, or at set intervals**.
- Option to **Create Basic Task** for ease of use.

#### 🧾 Event Viewer
- Displays logs and audits of system events.
- Used for **troubleshooting** and **investigating activity**.

**Three Pane Layout:**
- **Left**: Tree of log providers
- **Center**: Summary of selected logs
- **Right**: Actions pane

**Types of Events:**

| Event Type | Description |
|------------|-------------|
| Information | Successful operations |
| Warning     | Potential issues |
| Error       | Failed operations |
| Critical    | Serious failures |
| Verbose     | Detailed information for debugging |

**Standard Logs:**

| Log Name | Description |
|----------|-------------|
| Application | Logs from installed apps |
| Security    | Security-related events |
| Setup       | Setup/install events |
| System      | Events from Windows system components |
| Forwarded Events | Events collected from other machines |

---

### 📂 Shared Folders

- View active **network shares**, like `C$` and `ADMIN$`.
- **Sessions**: Who is connected.
- **Open Files**: What those users are accessing.
- Right-click to **view permissions**.

---

### 👥 Local Users and Groups

- Previously covered in Part 1 (`lusrmgr.msc`)
- Manage users, groups, and their permissions.

---

### 📈 Performance Monitor (`perfmon`)

- Monitor system performance **in real-time or via logs**.
- Useful for diagnosing performance bottlenecks.

---

### 🖧 Device Manager

- View and configure **hardware devices**.
- Option to **disable, update, or uninstall** devices.

---

## 💾 Storage Tools

### 🧱 Disk Management

Used for managing drives and partitions.

| Task | Example |
|------|---------|
| Create partitions | New drive setup |
| Extend volume     | Use unallocated space |
| Shrink volume     | Reclaim unused space |
| Change drive letter | E.g., D: → E: |

---

## 🔧 Services and Applications

### ⚙️ Services
- Background apps that **start with Windows**.
- Can **start/stop**, view **Properties**, and configure **startup type** (Manual, Automatic, Disabled).

### 📡 WMI Control

- **WMI (Windows Management Instrumentation)** allows scripting tools like PowerShell or VBScript to interact with system components.
- Superseded by **PowerShell**, as WMIC is deprecated in Windows 10 (21H1+).

---
---
## 📊 System Information (`msinfo32`)

---

### 🧠 What is System Information?

System Information (msinfo32.exe) is a built-in Windows tool that provides a **comprehensive overview** of your system’s:

- Hardware specifications  
- Installed components  
- Software environment

Per Microsoft:  
> "This tool gathers information about your computer and displays a comprehensive view of your hardware, system components, and software environment, which you can use to diagnose computer issues."

---

### 🗂️ Sections in System Summary

| Section | Description |
|--------|-------------|
| **Hardware Resources** | Low-level technical specs (e.g., IRQs, memory ranges) — mostly for advanced users |
| **Components** | Info on installed hardware like input devices, display, multimedia, etc. |
| **Software Environment** | Info about running processes, environment variables, network connections, and more |

---

### 🔧 Environment Variables (📁 `%WINDIR%`, etc.)

Environment variables store key system data and are **used by both the OS and applications**.

| Variable | Purpose |
|----------|---------|
| `%WINDIR%` | Path of the Windows directory (e.g., `C:\Windows`) |
| `%TEMP%` / `%TMP%` | Path to temporary file storage |
| `%USERNAME%` | Currently logged-in user |
| `%PATH%` | Directories searched for executable programs |

#### 🧭 Where to View/Edit Them:

- `Control Panel > System and Security > System > Advanced system settings > Environment Variables`
- Or: `Settings > System > About > System Info > Advanced System Settings > Environment Variables`

---

### 🔍 Tip: Use the Search Bar

- At the **bottom of the msinfo32 window**, there's a **search bar**.
- Example: Select `Components`, then search for `IP address` to quickly locate network-related info.

---
---

## 📊 Resource Monitor (`resmon`)

---

### 🧠 What is Resource Monitor?

Resource Monitor (`resmon`) is a built-in Windows tool used for **advanced system diagnostics and troubleshooting**.

Per Microsoft:  
> "Resource Monitor displays per-process and aggregate CPU, memory, disk, and network usage information. It allows advanced filtering, deadlock detection, service control, and more."

---

### 🧰 Key Features

- Real-time monitoring of **CPU, Memory, Disk, and Network** usage
- Per-process usage statistics
- Ability to:
  - **Start/stop/pause/resume services**
  - **Close unresponsive apps**
  - **Isolate processes** (advanced filtering)
  - **Identify deadlocks and file locking conflicts**

---

### 🧭 Overview Tabs

| Tab      | Description |
|----------|-------------|
| **CPU**    | Shows per-process CPU usage, services, and threads |
| **Memory** | Displays RAM usage, hard faults/sec, and used/available memory |
| **Disk**   | Displays read/write activity, disk queue length, and file I/O |
| **Network**| Shows current TCP connections, listening ports, and bandwidth usage |

---

### 📈 Real-Time Graphs

- A **right-hand pane** in `resmon` displays **live system performance graphs** for each category.

> 💡 Note: The data shown is specific to your system and will vary from reference images.

---
---

## 💻 Command Prompt (cmd)

---

### 🧾 Overview

The **Command Prompt** (`cmd`) allows users to interact with the operating system through a **text-based interface**. Although modern operating systems primarily use a GUI, the command line remains a powerful tool for **automation, troubleshooting**, and **administrative tasks**.

> 🏁 In early systems, CMD was the **only** way to control the OS.

---

### 📌 Basic Commands

| Command   | Description                              |
|-----------|------------------------------------------|
| `hostname`| Displays the name of the current computer |
| `whoami`  | Displays the username of the logged-in user |
| `cls`     | Clears the command prompt screen          |

---

### 🌐 Network & System Info

| Command     | Description                                                |
|-------------|------------------------------------------------------------|
| `ipconfig`  | Shows network adapter configuration                        |
| `ipconfig /?`| Displays help manual for the `ipconfig` command            |
| `netstat`   | Displays TCP/IP network connections and statistics         |
| `netstat -a`, `-b`, `-e` | Appends different views for network info      |

---

### 🧰 `net` Command – Network Management

The `net` command is used to manage **network resources** and **local user accounts**.

#### 📚 Usage:
``bash
net help
net help user
net help localgroup

> 📝 Use `net help <subcommand>` instead of `/?` to get help.

---

### 🧰 `net` Sub-Commands

| Sub-command      | Purpose                              |
|------------------|--------------------------------------|
| `net user`       | View and manage user accounts        |
| `net localgroup` | Manage local groups                  |
| `net share`      | Manage shared folders                |
| `net session`    | View sessions connected to the system|

---

### 🛠️ Help and Manuals

| Command         | Description                            |
|-----------------|----------------------------------------|
| `<command> /?`  | Shows help manual for most commands    |
| `net help`      | Used specifically for the `net` command

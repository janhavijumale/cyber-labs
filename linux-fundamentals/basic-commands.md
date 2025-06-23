
# 🐧 Linux Basics – Part 1

A beginner-friendly reference sheet of essential Linux commands with descriptions, examples, and their full names.

---

## 📌 User & Output

| Command | Full Name | Description | Example | Output |
|---------|------------|-------------|---------|--------|
| `echo` | N/A | Outputs the text you provide | `echo Hello` | Hello |
| `whoami` | Who Am I | Shows the current logged-in user | `whoami` | kali |

---

## 📂 File & Directory Navigation

| Command | Full Name | Description | Example | Output |
|---------|------------|-------------|---------|--------|
| `ls` | Listing | Lists files and folders in the current directory | `ls` | Lists items |
| `cd` | Change Directory | Navigates between directories | `cd /home` | Moves to /home |
| `pwd` | Print Working Directory | Displays the current directory path | `pwd` | /home/kali |
| `cat` | Concatenate | Displays contents of a file | `cat notes.txt` | Shows file content |

---

## 🧠 Tips
- Use `ls -la` to view hidden files and permissions
- Use `cd ..` to go one directory back
- Combine `cat`, `less`, or `more` to read long files

---
---

## 🔍 File Search & Keyword Matching (Beginner Friendly)

### 📁 `find` – To locate files and folders

| Command | Description | Example Output |
|---------|-------------|----------------|
| `find . -name file.txt` | Search for `file.txt` in the current folder and subfolders | `./folder1/file.txt` |
| `find . -name "*.txt"` | Search for all `.txt` files in the current folder | `./notes.txt`, `./docs/info.txt` |

🧠 **Tip**:  
- `.` means current folder  
- `*` is a wildcard — matches anything

---

### 📄 `grep` – To search **inside files**

| Command | Description | Example Output |
|---------|-------------|----------------|
| `grep "password" file.txt` | Show lines that contain the word "password" in `file.txt` | `3: admin password is 1234` |

🧠 **Use when you're looking for a word inside a text file**

---




# 🛡️ Windows Command Line Enumeration & Investigation

## 📋 Objective
This lab focused on navigating a Windows Server 2022 Core environment using the Command Line Interface (CLI) to identify running services, manage processes, and locate hidden system files.

---

## 🔍 Task 1: Network & Service Enumeration
I utilized `netstat` and `tasklist` to map active network ports to specific system services.

* **Key Finding:** Identified Port 3389 (RDP) listening under PID 984, managed by `TermService`.
* **Commands used:** - `netstat -ano | findstr :3389`
  - `tasklist /svc /fi "pid eq 984"`

![Network Enumeration](./network-ports.png)

---

## ⚙️ Task 2: Process Analysis & Management
In this phase, I audited the running process tree to identify specific applications and learned how to terminate unresponsive or suspicious tasks.

* **Technique:** Filtering the task list for specific image names.
* **Commands used:**
  - `tasklist /fi "imagename eq cmd.exe"`
  - `taskkill /f /pid <PID>`

![Process Audit](./process-list.png)

---

## 🏴‍☠️ Task 3: File System Investigation (The Treasure Hunt)
I performed a deep-dive into the file system to locate hidden files and discover hidden "flag" data.

* **Technique:** Using recursion and attribute filters to find files across the entire C:\ drive.
* **Commands used:**
  - `dir /s /b C:\flag.txt`
  - `type C:\Treasure\Hunt\flag.txt`

![Flag Discovery](./flag-discovery.png)

---

## 🧠 Skills Demonstrated
* Windows Server Administration
* CLI-based Enumeration
* System Audit & Incident Response Basics

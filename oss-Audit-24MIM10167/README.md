# Bash Scripts Collection

A collection of 5 beginner-friendly Bash scripts for Linux system utilities — covering system info, package checking, directory analysis, log parsing, and file generation.

---

## 📁 Scripts Overview

| # | Script | Description |
|---|--------|-------------|
| 1 | `sysinfo.sh` | Displays kernel, user, uptime, and date |
| 2 | `pkgcheck.sh` | Checks if a package is installed via `dpkg` |
| 3 | `dirinfo.sh` | Lists size and permissions of key directories |
| 4 | `loganalyzer.sh` | Counts ERRORs and WARNINGs in a log file |
| 5 | `manifesto.sh` | Generates a FOSS project manifesto text file |

---

## 🚀 Getting Started

### Prerequisites

- Linux OS (Ubuntu/Debian recommended)
- Bash shell (`bash --version`)
- `dpkg` (for script 2 — pre-installed on Debian/Ubuntu)
- `du`, `stat` (for script 3 — pre-installed on most distros)

### Clone or Download

```bash
git clone https://github.com/yourusername/bash-scripts.git
cd bash-scripts
```

Make all scripts executable:

```bash
chmod +x *.sh
```

---

## 📄 Script Details

### 1. `sysinfo.sh` — System Info

Prints a quick snapshot of the current system.

```bash
bash sysinfo.sh
```

**Output:**
```
--- SYSTEM IDENTIFIED ---
Kernel: 6.5.0-41-generic
User: user
Uptime: up 3 hours, 42 minutes
Date: Tue Mar 31 10:24:37 IST 2026
```

---

### 2. `pkgcheck.sh` — Package Checker

Prompts for a package name and checks if it is installed using `dpkg-query`.

```bash
bash pkgcheck.sh
```

**Example — Package found:**
```
Enter package to check: curl
STATUS: curl is installed (Version: 7.88.1-10+deb12u5)
```

**Example — Package not found:**
```
Enter package to check: nmap
STATUS: nmap is NOT found.
```

---

### 3. `dirinfo.sh` — Directory Info

Scans `/etc`, `/home`, and `/var/log` and prints their size and permission bits.

```bash
bash dirinfo.sh
```

**Output:**
```
DIR             SIZE            PERM
/etc            12M             755
/home           4.8G            755
/var/log        236M            755
```

> You can edit the `dirs` array inside the script to scan custom directories.

---

### 4. `loganalyzer.sh` — Log Analyzer

Reads a file named `syslog.txt` and counts lines containing `ERROR` or `WARNING`.

```bash
bash loganalyzer.sh
```

**Requires:** A `syslog.txt` file in the same directory. Example:

```
[INFO]    Service started successfully
[WARNING] Disk usage above 80%
[ERROR]   Failed to connect to database
[WARNING] Memory usage high
[ERROR]   Timeout on port 8080
```

**Output:**
```
Log Analysis for: syslog.txt
--------------------------
Total Errors:   2
Total Warnings: 2
```

> If `syslog.txt` is missing, the script exits with an error message.

---

### 5. `manifesto.sh` — FOSS Manifesto Creator

Interactively collects project details and writes a formatted manifesto to `manifesto.txt`.

```bash
bash manifesto.sh
```

**Example session:**
```
--- FOSS Manifesto Creator ---
Enter your Project Name: OpenLibre
What is your main mission? empower users with free and open software
What is your core value? freedom and transparency
--------------------------------------------
Success! Your manifesto has been saved to 'manifesto.txt'.
```

**Generated `manifesto.txt`:**
```
PROJECT:    OpenLibre
MISSION:    Our goal is to empower users with free and open software.
PHILOSOPHY: We believe that freedom and transparency is essential for all users.
CREATED BY: user on 2026-03-31
```

---

## File Structure

```
bash-scripts/
├── sysinfo.sh
├── pkgcheck.sh
├── dirinfo.sh
├── loganalyzer.sh
├── manifesto.sh
├── syslog.txt        # Required by loganalyzer.sh
└── README.md
```

---

## Notes

- All scripts are written in pure Bash — no external dependencies beyond standard Linux utilities.
- Scripts 1, 3, and 5 run without any input files.
- Script 2 requires `dpkg` and is intended for Debian/Ubuntu systems.
- Script 4 requires a `syslog.txt` file to be present in the working directory.
- Terminal screenshots in this project were rendered using SVG — no external screenshot tools were used.

---

## License

This project is open-source and free to use under the [MIT License](LICENSE).

---

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

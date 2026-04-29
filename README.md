# DFGMU

DFGMU is a small Windows utility project that reimplements basic shell commands (`dir` and `cd`) as standalone executables for learning and experimentation.

This project was developed as part of the Digital Forensics program at George Mason University.

---

## Overview

This repository contains two programs:

- `rdir.exe` – lists files in a directory (similar to `dir`)
- `rcd.exe` – changes the working directory of the process (similar to `cd`)

The goal of this project was to better understand:
- Windows file system interactions
- Process-level directory handling
- Command-line argument parsing

---

## Features

### rdir.exe
- Lists files in a specified directory (defaults to current directory)
- Supports:
  - `/a` – include hidden files
  - `/o` – display file owner
  - `/d` – recurse through subdirectories

### rcd.exe
- Changes the working directory of the running process
- Accepts:
  - relative paths (`..`)
  - absolute paths (`E:\`)

---

## Limitations

- Uses ANSI APIs (`SetCurrentDirectoryA`)  
- Does **not** support Unicode / wide-character paths  
- `rcd.exe` does not change the directory of the parent shell (expected behavior for child processes)

---

## Usage

No installation required.

1. Download the executable or build from source  
2. Open a command prompt  
3. Navigate to the directory containing the executables  

### Examples

```cmd
rdir.exe
rdir.exe /a /o
rdir.exe E:\ /d

rcd.exe ..
rcd.exe E:\

Understanding how basic file system operations are implemented at the API level can be useful in:
- forensic analysis of process behavior
- identifying anomalous file enumeration activity
- reverse engineering simple tooling used by threat actors

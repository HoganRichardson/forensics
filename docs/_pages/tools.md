---
title: Tools
permalink: /tools/
---
This page contains a list of tools I have used/been exposed to throughout forensics, with a short description of the usefullness of each.

## Command-line Utilities
### Vanilla Tools
* `dd` performs a 1:1/byte-for-byte copy of a file/folder

### Disk Structures/Partition Tables
* `lsblk -a`
* `df -a`

### macOS-specific
* [`ls -l@`](<https://ss64.com/osx/ls.html>) will display all 'forks' or Alternate Data Stream files in the directory
* `hdiutil` & `diskutil` can be used for mounting and managing disk images/partitions

## Complete Tooling Environments
### 'Push Button Forensics' - Full Toolsets
* **[Autopsy](<https://www.sleuthkit.org/autopsy/>)**
* **[RedLine](<https://www.fireeye.com/services/freeware/redline.html>)** - a similar tool to Autopsy (Windows only)

### Memory Analysis
* **Volatility**
* **Rekall**

Note: I will endeavour to add links to html man pages for the above tools where available.

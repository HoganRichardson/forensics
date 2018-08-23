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
### Full Toolsets
* **Sleuthkit Suite**
	* **SIFT** - The 'Kali' of forensics
	* **[Autopsy](<https://www.sleuthkit.org/autopsy/>)**
	* `sleuthkit` commandline tools is what underpins Autopsy. See all the [TSK commands](<https://wiki.sleuthkit.org/index.php?title=TSK_Tool_Overview>) for details. 
* **[RedLine](<https://www.fireeye.com/services/freeware/redline.html>)** - a similar tool to Autopsy (Windows only)

### Memory Analysis
* **Volatility**
* **Rekall**

## File Scraping
### Unallocated Cluster Tools
* **Photorec** - Windows-based unallocated file carving tool
* `bulk_extractor` - linux-based 'string'/regex extractor tool. Extracts string artefacts from the file. 

Note: I will endeavour to add links to html man pages for the above tools where available.

## Windows Analysis Tools
### Registry Analysis
* `regedit`
* MiTeC Windows Registry Recovery
* RegRipper
	* SAM plugin for inspecting user information

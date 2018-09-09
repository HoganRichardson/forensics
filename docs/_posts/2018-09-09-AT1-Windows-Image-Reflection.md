---
tags: at1 reflection
title: AT1 Windows Image Reflection
---
## Overview
![image-left]({{ "/assets/images/windows.png" | absolute_url }}){: .align-left} The Windows image brought to light some ideas that were hinted at in the USB image. This Windows machine was used by multiple users, and they appeared to be involved in some way or another in suspicious activity. 

The USB drive can be confirmed as being attached to the machine, though it appears that a matching file was read of a drive with a diffrent name (perhaps this was due to the mounting of the NTFS/FAT partitions on the system?). 

The Windows machine shows activity relating to *Operation Powerful Owl*, including copies of the Dropbox folders, as well as further documents. A VeraCrypt volume had been recently mounted to drive letter `A:\`, and the key for this drive was located in the same directory as the VeraCrypt installation, whichi allowed me to mount the drive to my own system. 

The computer apperas to be managed by NGL (the internet history reveals a likely name for this company to be *Next-Gen Livestock*). There are admin and guest accounts set up with the NGL prefix. 

## My Perspective
From the investigations that I undertook, it appears that this Windows computer was used as part of the so-called *Operation Powerful Owl* in order to steal genetic modification data. The multi-user machine has been used to create and modify files on an encrypted drive, and run encryption and erasure tools. The user accounts include "Robert Donnees-Cachees", who is likely to be the same 'Robert' as referred to in the message left on the USB drive. Given that the USB was found in the same location as the computer, and with 8 logons (the largest of all users), Robert appears to be the main user of this machine.

The internet history also implies malicious activity. There are numerous searches relating to how to hide and encrypt data on a computer, and whether or not an employer would be able to see certain activity. The internet download history also shows the installation of various software products that are linked to this operation. 

Ultimately, this computer contains activity that proves the use of encryption/data hiding tools and techniques in order to try and extract certain company information and utilise the GM research for some sort of alterior motive.

## Reflection on Tooling
I initially used RegRipper to analyse the registry files, and whilst this gave a comprehensive text file, it was a little annoying to have to use different perl scripts to extract various information. I later installed [MiTeC Registry Recovery Tool](http://www.mitec.cz/wrr.html), which was much easier to navigate, since the raw hierarchical structure of the familiar Windows registry could be navigated through, making it much easier for me to find what I was looking for. 

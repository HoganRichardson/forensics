---
tags: AT1 reflection
title: AT1 USB Image Reflection
---
## Overview
![image-left]({{ "/assets/images/usb.png" | absolute_url }}){: .align-left} My first approach with the USB drive was to open the image in Autopsy, and from there get a feel for the content. There were several files on the USB drive, including a needle/haystack type search through Wikipedia `.html` files. Running the ingest modules helped, but didn't reveal all the interesting files (especially not ADS files). 

Upon the completion of my investigation, I had found encrypted `.zip` files (one was disguised as a `.html` file), passwords and messages stored in unallocated space and in Alternate Data Streams of files. 

I have located the GnuPG certificate/key file but did not find a use for this key. It appears to be an encryption key, not a decryption key.

## My Perspective
This USB drive appears to have been used to share files/tools in relation to the so-called *"Operation P.O."*. We now know that P.O. stands for *Powerful Owl*. 
There was hidden content on the USB used to share a Dropbox URL and tools for encryption and deletion of files. It appears that this USB was filled with 'junk' content to try and hide the true purpose of it's use to transfer files.

Ultimately this USB drive shows activity of malicious behaviour and data transfer based on the use of data-hiding techniques that try and disguise and hide data from an uninformed third party. This would be effective had the USB fallen into the hands of someone unintended. 

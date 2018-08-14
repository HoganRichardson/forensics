---
tags: challenge writeup week03
---
Below is a writeup of solutions to Alternate Data Stream challenges from week03. I didn't get time to try these myself, but here are some notes from the follow-up tutorial.

**hfsplusads0**
* Running `ls -l@` (on macOS) reveals the existance of a 'ResourceFork' on the README.txt file. 
* To reveal this flag, you need to leak the resource fork file like so: `cat README.txt/..namedfork/rsrce`
	* This flag was also revealed by simply running strings on the disk image
* Another way of finding this information is to use the [xattr tool](<https://github.com/xattr/xattr>).

**hfsplusads1**
* Run `xattr -l ./*` to reveal a base64-encoded flag
	* In this scenario, this uses the Apple "Resource Fork"

**hfsplusads2**
* This is the SVG challenge. There are two files in the alternate data stream, which, when combined, form a new svg containing the flag

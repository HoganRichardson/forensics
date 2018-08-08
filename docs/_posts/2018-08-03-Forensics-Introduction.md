I was very excited to begin lectures for Forensics this week. This first overview lecture covered some important aspects of Digital Forensics that I hadn't thought about coming into this course: the _science_ component! The key things that stood out were the importance of the Scientific Method, and the various components of the Law (such as Rules of Evidence, Admissibility etc.). The most important aspect of course is ABD: **A**lways **B**e **D**ocumenting!

![]({{"/assets/images/abd.png"}})

_Image from [Lecture Slides]("https://webcms3.cse.unsw.edu.au/COMP6445/18s2/resources/20138"), adapted from [https://youtu.be/LHgQSwgKygk?t=1m18s]("https://youtu.be/LHgQSwgKygk?t=1m18s")_

When we discussed the forensic incident response field, I realised that this could be something that I would be interested in doing further. It's very interesting to see how this methodical approach can be applied to a real-time situation. Hopefully there will be some challenges simulating this during the course (and if not, I'll have to make one).

## Tooling: Notes from the First Tutorials
Some notes from the tools I installed during the Week 2 tutorial (before lecture).
* Basic Commandline Tools
	* `dd` - convert and copy drives - doesn't use the file system, interracts with drive directly
	* `fdisk` - formatting drives
	* `shread` - destroys data (completely...no really, completely). Perform pass throughs of the disk - tries to access each individual address on the disk (writes garbage or 0's). After 1 pass, it may not completely destroy the data
	* `file` - estimates type of file. Often for images
	* `strings` - searches for strings in a file
* Extra Tools (I will look further into these later)
	* `bmap`
	* `blkls` - list blocks - see which device you are using
	* `tsk/tct`
	* `gdb` - binaries (obviously)
	* `steghide` - steganography analyser
* Full Tooling environments
	* autopsy - takes forensic image of machine
	* redline (similar - Windows only)
	* ftk imager - industry standard at performing an 'acquisition' of a machine. A real pain to download without giving them an email address.
	* SIFT - The "Kali" of Forensics. Note: take a snapshot immediately after installing VM so it can be easily reset
* Memory Analysis
	* Volatility
	* rekall

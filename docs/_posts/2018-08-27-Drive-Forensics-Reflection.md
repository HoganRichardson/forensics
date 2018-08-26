---
tags: reflection week05
---
Over the last two weeks we've been delving heavily into **drive** forensics, examining ways of recovering deleted files on different file systems, and how data can be hidden in areas on the drive that aren't accessible through normal means.

One of the things that stood out to me was the fact that 'every action has a consequence', so even if something has been removed off a system, it may still be possible to gain an insight into what the user has been doing, and whether any malicious behaviour has been conducted. For example, even if *known bad* data can't be recovered from a system, the presence of tools that allow users to write to unformatted parts of a drive could indicate that the user has been trying to hide something. This is why the timeline of events is so important, and examining all events that occurred in the critical period can give a significant insight into what activity might have gone on.

### Top ways of stealing Company Data
This brings me on to one aspect that was pointed out in the lecture, but not examined in detail: the top three ways in which employees steal company data. These are:

1. USB Drive
2. Email
3. Cloud

This has some interesting consequences, especially considering it from an IT management point of view. Consider this: You have deployed security software on your managed devices to disallow all USB devices by default (I actually came across this scenario recently). You've also deployed an encryption mechanism on your email server so that attachments can only be unlocked with specific permissions. None of this stops an employee from visiting the website of their favourite cloud storage provider or web-based email client and uploading some files! It would be infeasible (and potentially hindering to users) to blacklist every cloud storage site, so the last two are quite difficult to prevent. Whilst forensics often deals with the aftermath of something being (or alleged being) stolen, I think it's also important to consider what IT managers might do in prevention efforts.

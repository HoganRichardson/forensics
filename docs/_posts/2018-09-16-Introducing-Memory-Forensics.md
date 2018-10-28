---
tags: week8 reflection
---
We’ve shifted gear away from drive forensics and into a much more volatile space: memory!

So far we have explored the similarities and differences between drive and memory forensics, including acquisition and analysis processes, as well as being introduced to some key tools that will assist with memory forensic investigations. I’m excited to delve into this new space and learn some different nd new concepts.

We have explored how Windows processes are established and run, as well as the underlying hierarchy and data structures that the OS maintains. This is something new that I wasn't aware of, but there is also an air of familiarality from the Operating Systems course as we look at the way processes are run in a system. 

*It can hide, but it has to run!*

Looking at malware will be an interesting topic, and certainly will reveal various hiding techniques in memory. I have set up the [**Fireye Flare VM**](https://github.com/fireeye/flare-vm) on my machine, which has a variety of pre-installed tools that I'm sure will become useful. Tim mentioned a 'cold boot' attack, but didn't go into detail. After some [extra reading](https://en.wikipedia.org/wiki/Cold_boot_attack), it reveals a very interesting technique that could be potentially useful for recovering memory from a machine that has been powered off.

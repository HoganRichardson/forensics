---
title: AT1 and Tooling Tips
tags: week06 AT1 reflection
---
I have been working on image01 of assessment task 1 this week, and throuhgout the course of investigation, I have learned a bit more about how some key tools work, developed some small scripts and wasted some time because of lack of understanding of some tools. 

So, I began investigations by importing the image into Autopsy, however, what I didn't realise was that when I imported the `.E01` file, it didn't automatically run the injest modules, so I spent a lot of time trawlling through content that could have been picked out by autopsy: in particular, as you'll see later on, trying to crack a zip file when there was another HTML file that I already had the password to! This, however, was a worthwhile lesson as it has reminded me to always know how the tools I'm using work before jumping in and trying things (I should have taken a more systematic approach). 

Having found an encrypted `.zip` archive, I thought that one potential way in would be to try and guess the password through brute force. I already had the basis of a multithreaded python script, so I modified it slightly to work with th `7z` command line tool. [I have attached the script below](#crackpy).

It's been an interesting experience looking into this image, and examining the various files and evidence. Putting a puzzle together like this is a very unique experience, and not one I'm that familiar with. Normally, my problem solving has a clear correctness (e.g. writing a program, solving a mathematical problem). There is usually a clear path to the end goal, and at each step, you can normally identify whether you are moving in the right direction. This investigation doesn't have this supportive nature. The aim here is to gather and sift through a large amount of information in order to come up with some sort of conclusion or present some evidence that shows certain activity. I do like the openness of this challenge (as opposed to those which find flags), because it feels more *real* and there is less about the right/wrong approach, and more about the information discovered. In fact, I would go so far as to say that this is my most enjoyed security assessment task yet!
 
### `crack.py`
{% highlight python %}
import multiprocessing
import requests
import tqdm
import sys
import subprocess

if len(sys.argv) < 4:
    print("Usage: python3 crack.py [passwordfile] [zipfile] [outdir] <optional [startindex]>")
    sys.exit(1)

file = sys.argv[2]
outdir = sys.argv[3]
start = int(sys.argv[4]) if len(sys.argv) >= 5 else 0

with open(sys.argv[1], 'rb') as f:
    passwords = str(f.read(), 'latin-1').splitlines()

def makeRequest(password):
    result = subprocess.run(['7z', '-p' + password, '-o'+outdir+'/' + password, 'x', file], stdout=subprocess.PIPE, stderr=subprocess.PIPE)

    if result.returncode == 0:
        return True

    return False

match = []
p = multiprocessing.Pool()
for i, result in enumerate(tqdm.tqdm(p.imap(makeRequest, passwords), total=len(passwords)), start):
    if result == True:
        print('\n\n')
        print(passwords[i])
        print('\n\n')
        sys.exit()
{% endhighlight %}

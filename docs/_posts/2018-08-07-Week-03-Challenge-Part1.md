The challenge for this week is to work on a `.dmg` image, to try and discover as many hidden flags by performing a forensic analysis on the image. And, in the spirit of [Batman]({{"/assets/images/abd.png"}}), I would like to make a verbose description of all steps that I have followed to analyse this image. I'm expecting a few things to be hidden in the Alternate Data Stream (ADS) files, since that has been the focus of the 'technical' side of things this week.

I will not be releasing the flags in this post. The idea of the journal is that if the steps are followed, the same results should be able to be produced.

## Journal


<i class="fas fa-user-md"></i> Hogan Richardson

<i class="far fa-clock"></i> 2018-08-09

| Job # | Journal Type |
|-------|--------|
| z5112937_c6845_0001 | Evidence Analysis |

### Log

| Time | Journal Notes |
|-------|-------|
| 0918 | Downloaded file from Google Drive |
| 0918 | Calculated MD5 Hash of the file. This hash will be recalculated and compared to this copy to verify that I haven't altered the image in some way whilst investigating. `92b359fd11ab1753c4d151017f45ad02` |
| 0920 | Made a copy of the image called `hfsplus-working.dmg` |
| 0920 | Performed a `strings` analysis on the file. This revealed two flags immediately. It also indicated that there was an `svg` fie on the image somewhere (Lines 37-130). At the end of the file there is some sort of Apple plist-like file. At line 2709-2718 is a markdown file. |
| |Strings Output: [<i class="fas fa-file-alt"></i>](<https://drive.google.com/file/d/1kS3E5m6hnPOy8baUloQEx-y4TfEi0MI5/view?usp=sharing>)  `md5: 502b68c01a3401b531e4219882a42f6d`|
| 0927 | Mounted the image on my file system (`hdiutil attach hfsplus-working.dmg`) and explored the directory structure. Used the `ls -l@` command (macOS) to see additional metadata files. |
| 0944 | **level0** contains flag.txt file. By performing a base64decode on this, the flag is revealed. |
| 0950 | **level1** contains several direectories, with several text files. All these text files contain a single line (which seems to be a base64-encoded value). I wrote a [short script](#lssh-script) which cat'd out all these files, and piped this through less. As I scrolled through, I noticed 40 identical values, so I decoded this value, and it revealed the flag. | 
| 1003 | **level2** contained a file `guess.what`. By running the `file` command, it estiomated that this was a .zip file (which could be a false positive...). When I `cat` this file, there is the text 'flag2.jpg', which may indicate that this is some sort of image. |
| 1012 | After making a copy of `guess.what`, renamed it with .zip extension, and attempted to unzip. It then prompted a password for flag2.jpg (the only file inside the zip folder). 

... to be continued

## Appendix
### `ls.sh` script
{% highlight bash %}
#!/bin/bash
for i in {0..39}
do
   for j in {0..40}
   do
      cat "$i/$j.txt"
   done
done
{% endhighlight %}

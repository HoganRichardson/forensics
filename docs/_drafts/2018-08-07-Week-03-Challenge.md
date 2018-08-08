The challenge for this week is to work on a `.dmg` image, to try and discover as many hidden flags by performing a forensic analysis on the image. And, in the spirit of [Batman]({{"/assets/images/abd.png"}}), I would like to make a verbose description of all steps that I have followed to analyse this image. I'm expecting a few things to be hidden in the Alternate Data Stream (ADS) files, since that has been the focus of the 'technical' side of things this week.

I will not be releasing the flags (just yet). They will be added to this blog post at the end of next week.

## Journal
* Downloaded file from Google Drive
* Calculated MD5 Hash of this file (this hash will be recalculated and compared to this copy to verify that I haven't altered the image in some way whilst investigating). 
* Make a copy of the image called `hfsplus-working.dmg`. 

	_Investigations Begin!_
* Perform a strings analysis on the image 	
	```
	$ strings hfsplus-working.dmg
	```

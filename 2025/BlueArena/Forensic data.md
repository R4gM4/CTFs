Category : forensics
Difficulty : easy - 60 points
___
First thing first ! We are pleased with a very nice file containing lots of information :
	`chal.dat: data`

...
Well, we quickly see that this file does not contain ASCII text. Let's open it in Cyberchef and begin our investigation.

Since it was my third challenge (I previously did MLE and Forensic 1), my first action was cooking some ROT47. 
![](attachment/616e6fe3fc57e6d1741827e1f8756c0b.png)

Nice, a PNG file again. But something is missing...
![](attachment/fce12b1295adfb79a855efdcf8a0d40c.png)

Where is the other part of the flag ? :(

Since it is a PNG file, we might want to try a steg command :D
zsteg will do the job for us !
![](attachment/93f58e3e73d2d8f4c5d3ee339d43c91b.png)

BINGO we now have our two parts.

Flag : `BLUEARENA{1m4g3_1s_gr4bb3d_f1n6_1t}`

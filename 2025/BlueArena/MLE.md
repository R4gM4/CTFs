Category : forensics
Difficulty : easy - 20 points
___
So wa basically have this file
	`mle1: ASCII text`

With this content inside.
```txt
d` e3 fg de da dd ce db da dd bd ca ed ba ch fg ec dc c6 ee c6 cg ch f2 ea e2 da ee dh e2 c6 e6 e` df bc f2 eb bb b_ b5
```

Before even thinking how the author encoded this, we must keep in mind that it is a *very easy challenge*, so they used usual encoding methods. First thing to notice is that characters are in pairs, so the decoded string will be hexadecimal. Well, the appearance of " \` " and " \_ " indicates the use of ROT algorithm. ROT13 doesn't work so it will be ROT47 !

In Cyberchef we cook `ROT47` then `From Hex` recipe and the output is `QkxVRUFSRU5Be2IxdTNfNHIzbjRfYjNnaW4zc30=`. The " = " at the end means it is base64. When applying `From Base64` we get the flag :)

Flag : `BLUEARENA{b1u3_4r3n4_b3gin3s}`

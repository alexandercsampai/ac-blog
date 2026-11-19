+++
date = '2026-11-19T15:59:04+01:00'
draft = true
title = 'Phone recovery'
+++
I have a Xiaomi MI 9T PRO
About 2 years ago my phone died out of nowhere, the full failure was just while using it the display turned off. 
The phone become unresponsive for any input, not showing up on my computer, not even fastboot or recovery worked.
At that time I had very little experitse in understanding low level hardware debugging so I put it aside and maybe in future I'll get to it and possibly try to recover it.
  
That time came two days ago. First I found that my laptop did see it, just not in the normal way. The phone was in QDL mode- Qualcomm Download loader. This is a bad sign because it 
means the fastboot partition and ecovery partition is missing. 
I found a firehose ufs loaded that is signed for this phone and used that to query the phone for info, 
First I tried reading lun 1 and lun 4 partitons to figure out if any data is in intact. 
I saved a binary file from lun 1 and compared to another binary file I read from Lun1 just a few moments later,checked their hash and it mached 
when i done this to lun 4 the hash didn't match at all. 
Thought first it's just corrupted flash, so i went and got the official fastboot images and settings from xiaomi and flahsed them.
After reading the binary files from lun 1 and lun 4 i found neither of them got flashed, the storage is fully locked up.
This means the storage is read-only, can't be flashed, and it run out of spare blocks it could use to balance usage.
I can't repair the phone, I would need to replace the chip or the whole board just to get it working and that's not worth on a 7 year old phone. 
  
Thank you for reading my blog post! have a nice day<3 

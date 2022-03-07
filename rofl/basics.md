---
layout: page
title: File Transfer Basics
---


Question on one some corporate newsgroup:

----

Noticed something weird today. Was using FTP to xfer some files 
around and noticed that "getting" files resulted in a transfer rate 
of about 15kb/sec while "putting" files resulted in a transfer rate 
of about 400kb/sec?!?! 

Both sending and receiving nodes were C4's, but one is a server 
and one is a WS.

What gives??

----

Answer some 10 minutes later:

----

The remote system is downhill from your system, resulting in 
a faster rate of transfer when you "put" files, and a lower rate of 
transfer when you "get" files (since you have to pull the bits uphill).

Remember, you should _never_ stack two systems on top of each 
other. Bits cannot handle vertical acceleration, and you could actually cause 
a bit overflow. That's why you should always back away from a machine that has 
an "overflow error", because, chances are, it's about to explode.

Jeeze, you're working at a computer company and you don't even 
know the basics?

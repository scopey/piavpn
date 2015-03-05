# piavpn
Raspberry Pi script for Private Internet Access VPN Service

I love the PIA Service

I love my Raspberry PI

I did not find a clear set of instructions or scripts.  This
is an effort to pull both together into one package. So far
I have managed to work around several of the issues listed
in the forums.  

Specifically:

1.  You do not have to modify the .opvn files from PIA.  I
use command line flags to avoid that problem

2.  You can put the files in any directory you like.  You do 
have to run the script as root (or use sudo).  I assume if 
you are doing this on a Raspberry PI root access is not an
issue for you. 

3.  To use DNS, you need to have the resolvconf package installed
(apt-get install resolvconf).  The update-resolv-conf script
provided with OpenVPN depends on it being present.

4.  After you install resolvconf, make sure /etc/resolv.conf is 
a symbolic link to /etc/resolvconf/run/resolv.conf  Otherwise 
the update-resolv-conf script will not work.

Very Basic Instructions

Someday I will write detailed instructions, but for now I assume
you have enough basic knowledge to figure out how to do the following:

a) pick a directory you want to store all the files in.  It does not have to be
/etc/openvpn  The script uses /home/pi/vpn, but you can modify it to your preferences

b) extract all the .opvn files to this directory
c) copy or mv your  ca.crt and crl.pem file into the same directory
d) create a file called user.txt.  In this file put ONLY the following information:
Your PIA Username
Your PIA Password

Example:

p777777777
E@38sar7ee

Nothing else.. just two lines... one is your user id, the other your password

e) Place piavpn anywhere you like.  I put mine in /usr/local/bin.  Make sure you
have execute (x) perms set

If all goes well, you should be able to use the script.  Make sure the first few
lines in the script are customized to your setup.  For usage, just type 

piavpn help

Ok that's about it.  Good Luck!  It works for me.  I hope it works for you too!

Stan

 


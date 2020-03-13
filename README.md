Tektronix GPL Code
==================

The Tektronix DPO/MSO/MDO 3000 & 4000 series scopes run Linux. A while ago I requested Tek's GPL source code. After like 2 or 3 requests, I finally got a CD mailed to me which contained this stuff here.

Funnily enough, I don't even think they comply to the GPL by sending this to me, because the Linux sources don't compile. Tek deleted a bunch of directories with drivers from the source tree. The dirs are still referenced from Kconfig files etc.

However, Tek overlooked some patch-files which contain all of the proprietary stuff. You can find them in linux2.tar.gz:/linux_DENX/linux/Patches/
Thanks, benevolent Tek-Engineer who didn't do his sanitization job properly 😘 "Grüße gehen raus!" as we say in German.

I didn't go through all of this and recovered a compilable source tree because I currently have no need for it. The oscilloscope magic happens in userspace and the Tek ASICs anyway, so having a compilable kernel doesn't gain you much unless somebody reverses the userspace application as well.

Another interesting fact: In older MDO3000 firmwares, they statically linked their scope application userspace binary against libusb and v2lin which are both LGPL libraries. Just saying... They fixed it in newer versions though. Most likely because I asked them to supply object files and the source of these libraries so I can relink everything. Of course I never got those.

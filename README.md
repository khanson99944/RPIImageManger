# RPIImageManger

This will go over how to take an image of a Raspberry Pi, shrink it and reimage it to another Pi. Exactly the same as the original. 

---

Prerequisites -

A.	Linux system (Linux subsystem on Windows 10 works fine)
a.	Will need to have gzip installed
b.	This is for the shrinking script. It is written in bash.
c.	MacOS should also work.

B.	Windows 10  
a.	Windows is needed as well as the disk imager used is Windows based. Others could work too, needs to be an .img file.

C.	Drewsif’s PiShrink Github
a.	https://github.com/Drewsif/PiShrink

D.	Win32DiskImager
a.	https://sourceforge.net/projects/win32diskimager/

E.	7zip
a.	https://www.7-zip.org/download.html
b.	To open the compressed image


Imaging - 

1.	Once you have completed the setup of the RaspberryPi OS, take the SD card out and use Win32DiskImager to read the card to a file.

2.	Once the image file is saved on the computer, either transfer the file to the Linux computer or open up the Linux subsystem and run the following command on the .img file (this will duplicate the file during the process, make sure there is enough space on the computer to accommodate)
a.	pishrink.sh -vz /path/to/old-image.img /path/to/new-image.img
i.	This command will shrink the ‘old-image.img’ into the path of the ‘new-file.img’. The switches that are set also apply a gzip compression on the image.

3.	The image file will have a .gz extension added to it automatically.

4.	The shrunken and compressed image can be distributed!


Decompressing and unshrinking the Image - 

1.	To decompress the file, open up the file in 7zip and extract the .img.

2.	With the decompressed .img file, then open Win32DiskImager and write the file to the SD card

3.	Put the SD card into the RaspberryPi and boot it up
a.	On first boot, the filesystem will expand to the original size 

4.	All of the settings changes and apps that were installed are all available as last seen on the original image.

5.	That’s it!


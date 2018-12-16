Purpose:
The purpose of this HOWTO is to teach inexperienced users on how to create a USB bootable disk from a Apple Macintosh computer.

Assumption:
You are running OSX 

Steps:
Step 1:
We must download the distro. we are looking to install. Go to the following link:
http://www.freebsd.org/where.html

Step 2:
Select 'i386' if the computer you are setting up FreeBSD on cannot support x64 bits, else it's recommended to select the 'amd64' distro. Once you have decided, select "ISO". If you don't know which one to choose, read up more here

Step 3:
Login in as 'Guest'

Step 4:
Copy the file with the 'memstick' keyword to your desktop. I will select the "FreeBSD-11.2-RELEASE-amd64-memstick.img" and will use it throughout this demonstration.

Step 5:
Load up your terminal. If you don't know where it is, go to:
Applications -> Utilities -> Terminal

Step 6:
Insert the USB stick that you want to use. Note: All data on the disk will be deleted!

Step 7:
Type in the following in the terminal and look for the name of the USB device:
Code:
df -h

Step 8:
Once you found the device in the list, make a note of it because the next step we are going to unmount it (note: disk1s1 is the id of my USB, yours will vary, so make a note of what yours is):
Code:
sudo diskutil umount /dev/disk1s1

Step 9:
Now, I'm assuming you copied your "FreeBSD-{version}-RELEASE-amd64-memstick.img" file to your desktop. In the terminal write the following:
Code:
/~Desktop

Step 10:
Now we will be mounting the bootable disk to our USB stick:
Code:
sudo dd if="FreeBSD"-11.2-RELEASE-amd64-memstick.img of="/dev/disk1s1" bs="10240"
You are now done! The terminal will look like it's hanged but don't worry! The USB is being written and will become available when the writing is done. If you have any questions, feel free to ask. Good luck and best wishes with your FreeBSD journey! :beer
## Sections
- Introduction
- Debian 12 installation
- Post install

## Section 0: Introduction
A home server is a wonderful thing to have inside your home! It can significantly enhance your network's performance, offer increased privacy by moving away from Big Tech, and provide a valuable learning opportunity to enhance your IT skills!

This guide series will walk you through setting up a spare PC as a Debian 12 server using Docker for streamlined operations. Don't get scared when you hear the word "Docker", we will utilize user-friendly web GUIs for server management, making this Guide suitable for beginners.

This Guide will cover the following:
- Installing Debian 12 on an x86_64 Desktop (Raspberry PIs not supported by this guide)
- Static IP router configuration
- Installing the CasaOS Web GUI
- Installing Portainer
## Section 1: Downloading and installing Debian 12

Step 1: Download Debian 12 from https://www.debian.org and flash it to a flash drive using balenaEtcher: https://etcher.balena.io and plug the flash drive to the server

Step 2: Boot into your PC's Bios using the dedicated keyboard key when the OEM's logo pops up at boot, if you don't know the key then just google it, for example Dell is F2

Step 3: Disable Secure Boot and Boot into your Flash Drive, again if you don't know how to do these things google them

Step 4: Install Debian: 

Click on the ``Graphical Install`` option, click on your preferred Language, Select your country of residence, select your preferred keyboard layout, and select your network interface (do the wired one if you have access to ethernet) 

your hostname should be something recognizable such as ``home-server`` or something like that, leave the domain name blank (we don't need it), for security reasons we won't enable the root user so just leave the password blank, type whatever you want for your user and choose a secure password to go with it.

Select your timezone and select the ``Guided - Use entire Disk`` option, select the drive that you want all of this on (I recommend using an SSD for performance reasons if you have one)

Put all the files into one partition for simplicity, it will give you a summary of what it is about to do to your disk (Make sure all important data is backed up first before erasing the disk)

If everything looks good then finish partitioning and hit yes.

Select your country again and select ``deb.debian.org`` unless you know of a mirror closer to you, leave the proxy blank becuase you can access the internet just fine without it, the popularity contest is just a service on your system that tells the Debian Devs which packages you use most so that they can prioritize the ones the community uses most, you can say yes or no to this.

Deselect ``Debian Desktop Environment`` and ``Gnome``, select ``SSH server`` since we will use that later

Everything will install and you should unplug the flash drive and hit continue to reboot

## Section 2: Post install configuration

I need to follow my own steps and do stuff in a vm to make sure everything is good.

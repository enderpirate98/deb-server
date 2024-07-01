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

Click on the ```Graphical Install``` option, click on your preferred Language, Select your country of residence, select your preferred keyboard layout, and select your network interface (do the wired one if you have access to ethernet) 

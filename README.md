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

You should now be put into a terminal interface with nothing but text, don't worry you won't be here long. Log in with the username and password that you set up earlier and type the words: ``ip a``, write down the ip address next to the lower ``inet`` as we will be using that a lot later.

Type ``exit`` and disconnect the monitor, keyboard and mouse. You can now run the system headless!

Assuming that you have access to your router go to ``http://192.168.1.1`` in your web browser and log into the web interface of the router, google how to assign a static ip on your perticular router to your new server, the reason for getting a static ip is that by default the ip of the server could change randomly at any point and then you can't access the services running on the server until you figure out the new ip so a static ip fixes this by assigning a perminant ip that the server can use for the rest of time.

After that is done open up the terminal on your computer and type ``ssh user@192.168.1.182`` replace the user with your username that you setup on the server and replace the 192.168.1.182 with the ip of your server that you wrote down, this allows you to remotely connect to the terminal of the server, you are probably sick of the terminal by now but after these few commands you will have a nice GUI web interface that you can manage everything from!
```
sudo apt update && sudo apt upgrade && sudo apt install curl
```
This command that you can now copy and paste into the terminal checks for any system updates and applies them if any are found, it also installs a program called ``curl`` that will help in a minute
```
curl -fsSL https://get.casaos.io | sudo bash
```
This installs the CasaOS web interface and Docker
```
reboot
```
Reboots the system to make sure that all updates and additonal programs are applied to the system before we move on

The reboot will close your ssh connection to the server and you can close it, in your web browser open a new tab and go to ``http://192.168.1.182`` replacing my ip with yours

Set your username and password and welcome to CasaOS!

This Web GUI allows you to install some Docker containers easily from the app store and if you need the terminal or to reboot the system you can hit the settings gear icon and access them easily!

To prepare for future guides where the Docker apps aren't part of the CasaOS app store we will manually install them through portainer so install that and setup a username and password.

Congrats! You have just laid the foundation for having the ultimate home server!

The next guide will cover how to install Jellyfin on your new server which is found [here](https://github.com/enderpirate98/jellyfin)

This guide was written by enderpirate98 under the GPLv3 but you can freely modify this guide and use it how you like as long as you link back to this page.

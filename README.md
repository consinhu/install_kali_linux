<h1> Step-by-step Guide to Installing Oracle VirtualBox and Kali Linux image on Windows 10 Pro </h1>

<p align="center"><img src="https://linuxiac.com/wp-content/uploads/2021/07/kali-linux-virtualbox.png" alt="kali" /> </p>

## Part I: Downloads and Prerequisites
- **Downloading VirtualBox**: Navigate to [Oracle Virtual Downloads page](https://www.virtualbox.org/wiki/Downloads) and select the VirtualBox installer
- **Downloading Kali Linux**: Go to [Kali Linux Downloads page](https://www.kali.org/get-kali/#kali-installer-images) and select 64-bit installer .iso image
  - Kali Linux image can be a bit finicky, but be sure to select the correct installer which should be the Recommended option on Kali website. torrent and sum may download more quickly, but failed to launch on my system. Regular download for the 4.4G will take a bit of time, even hours, but is more reliable, so be patient! 

## Part II: Creating the Virtual Machine (VM)
-  Once VirtualBox is downloaded and opened, select the **New** icon in the top left corner
- You will be prompted to name the VM (I just went with kali linux)
- Under ISO Image, select the downloaded Kali Linux ISO image from previous step to use. You may have to browse for it. If **Unattended Installation** box is checked, uncheck it.
- **Hardware**: Under hardware specifications, assign at least 2GB of RAM and 2 CPU cores
- **Hard Disk**: Allocate at least 25GB of space, 50 is recommended. Click Finish when done.

## Part III: VM Settings
- Navigate to the Settings on your Kali Linux VM
- Navigate to **General** and set both Shared Clipboard and Drag 'n Drop to Bidirectional
- Navigate to **Display** and slide Video Memory slider to maximum (usually 128MB)
- Navigate to **Network > Attached to:** and verify that it is set to NAT (this will allow VM internet connection). Finish by selecting OK

## Part IV: Kali Linux Installation Steps
- Start newly configured VM
- Once VM boots, select **Graphical Install** and continue
- Select preferred language, location, and keyboard layout
- **Configuring Network**: Enter hostname (I just use kali) and leave domain name blank
- **User Accounts**: Enter Full Name, set a Username, and create a password
- **Partition Disks**: Select **Guided - use entire disk**. Virtual disk option should appear next. As I only received one, I selected that option. Then, be sure to select the first partitioning method **All files in one partition**
- Finish partitioning and select write changes to disk option. Select Yes and then Continue.
- **Software Selection**: Leave default selections checked and continue.
- **Bootloader**: Select Yes to install GRUB bootloader, choose proper virtual drive path, and continue

## Part V: First Bootup
- GRUB boot menu will show up after initial reboot. It will either automatically boot into Kali Linux interface or you will have to manually select the option to
- After booting into Kali, enter the username and password you created in previous steps to log in
- **System Update**: Typically when booting into a new Kali machine for the first time, you will want to update all packages. To do so, open up the terminal and enter the command `sudo apt update && sudo apt upgrade -y`
- The new VM is now complete and ready for use


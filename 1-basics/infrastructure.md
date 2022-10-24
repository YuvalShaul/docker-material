# Infrastructure

I use this infrastructure throughout my training material.  
Linux is important in many new technologies, so I'm using a virtual machine on top of my Windows 11 OS.  

- first, install VirtualBox from [this location](https://www.virtualbox.org/wiki/Downloads).  
(I am currently using is 7.0.2 r154219)
- There are some options there if you are running Mac, especially if it is based on Intel cpu.
- The [osboxes](https://www.osboxes.org/) image will be an X86 based image though.

## Linux Image

- I like using the Ubuntu 22.04 Jammy Jellyfish image.
- the 22.04 is a long term support by Ubuntu, and seems stable.
- Here's the [link to the download page](https://www.osboxes.org/ubuntu/#ubuntu-22-04-jammy-vbox).
- Make sure that you download:
  - choose the correct image: Ubuntu 22.04 Jammy Jellyfish
  - a VirtualBox image (select the correct tab)
  - download the file
- You are downloading a **64bit.7z** file, that you will later extract ()
- Extract the image

## Creating the virtual machine

- Create a new virtual machine, but choose NO virtual disk yet.  
(ignore all warnings for that, you will add it in a moment)
- Creating the virtual machine will create a directory like this:  
     C:\Users\<your-username>\VirtualBox VMs   
Eventually, this is where you want your vdi file to go.
- If you are using the same downloaded file for multiple machines, you will have to change the **uuid** for the file, with this command:  
**VBoxManage internalcommands sethduuid "\<your vdi file name\>"**
- So, copy (or move) the file to the virtual machine directory, change the uuid if you have to, and add it to the virtual machine using the GUI (settings->storage->IDE->...)

## Running the VM

- Start the VM from VirtualBox UI
- Credentials:
  - user: osboxes.org
  - pass: osboxes.org


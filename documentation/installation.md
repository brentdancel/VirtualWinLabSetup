# Install Hypervisor
In my virtual lab environment, I decided to use Oracle VirtualBox as my hypervisor.

Installation link for Oracle VirtualBox:
https://www.virtualbox.org/wiki/Downloads

    - Install the VirtualBox Extension Pack for additional features

Choose the appropriate file location for your application

If you have 2 drives, install hypervisor on your main drive and then the ISOs/VMs on other drive

# Install Windows Server 2025 ISO
For Windows Server, I chose Windows Server 2025.

Installation link for Windows 2025:
https://www.microsoft.com/en-us/evalcenter/download-windows-server-2025


!!!! The ISO that is being installed is a 180-day Evaluation !!!!!!

    - After installation of Windows Server VM, you must activate it within 10 days to avoid automatic shutdown
    - After 180 days, you will have to make another VM using the same ISO or updated ISO (more practice, amirite?)

I installed the ISOs on my other drive; Make folders to organize VMs and ISOs


# Install Windows 11 ISO
To simulate a client machine, I chose the Windows 11 Home Edition. The ISO is at the bottom of the page

Installation link for Windows 11 Home Edition:
https://www.microsoft.com/en-us/software-download/windows11

!!!! Windows 11 Home does not support joining Windows Active Directory (AD) !!!!

    - If you wish to join the client machine to an AD domain, you must upgrade
    - You can still practice key concepts

# Configure Hypervisor
To begin installation, double click the installation file for Oracle VirtualBox hypervisor. I installed it on my Desktop for easier access.

- You must agree to the terms to continue installation
- Verify Install location of your application

!!!! To finalize install, your network will be disconnected momentarily. Save your work !!!!

After successful install, you can now use Oracle VirtualBox

# Install VMs
To install Windows Server and the Windows 11 Client, click on "New" at the top right and a window appears for creating a new VM
(Refer to screenshots)

- Organize your folders and files accordingly
- If you have 2 drives, install VMs on other drive

For the "Set up unattended guest OS installation" window, set your password
- Write down the password
- Change the domain name as well for lab purposes

At the "Specify virtual hardware" window, use the recommended settings for running DC1, Server1, Win11

DC1:
Base Memory -> 4096
Number of CPUs -> 2
Disk Size -> 60

Server1:
Base Memory -> 4096
Number of CPUs -> 2
Disk Size -> 60

Win11:
Base Memory -> 4096
Number of CPUs -> 4
Disk Size -> 60

- This is all dependent on the host machine; Adjust settings accordingly to run all 3 VMs simultaneosly

After inputting the settings, review the configuration settings and create the VM!
- Verify if files were installed at the right location
- The VM will automatically startup

Repeat for Server1 and Win11 Client (Refer to screenshots)

After installing all the VMs, you should have 3 VMs ready to use for the Windows Lab Environment
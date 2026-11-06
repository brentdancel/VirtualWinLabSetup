# Install Hypervisor
In my virtual lab environment, I decided to use Oracle VirtualBox as my hypervisor.

Installation link for Oracle VirtualBox:
https://www.virtualbox.org/wiki/Downloads

    - Also install the VirtualBox Extension Pack for additional features

Choose the appropriate file location for your application (C: drive)

If you have 2 drives, install hypervisor on C: drive and then the ISOs/VMs on other drive

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

# Install VMs
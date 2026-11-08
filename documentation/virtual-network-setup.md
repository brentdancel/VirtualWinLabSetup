# Deploy Windows Server(s) and Windows 11
For the Windows Server VMs, do the following...

1) If you have not turned on the Window Server VMs, start up them up
2) Follow initial wizard for Windows Server
    - For disk allocation, delete the partition and then select the disk again
3) The installation will begin and the VM will restart
4) After successful restart, you should boot up to the main Desktop with Server Manager opening up
5) Shut down the VM
4) Repeat Steps 1-3 for Server1

For the Windows 11 Client VM, do the following...
1) If you have not turned on the Windows 11 Client VM, do so now
2) The VM will automatically begin the install
3) After successful install, you should boot up to the main Desktop

# Configure virtual network
For all three VMs, configure the network adapters as such...
1) Shut down all three VMs
2) Right click on the VM to access the settings of the VM
3) Click on Expert and navigate to the Network section
4) Verify Adapter 1 is set to NAT
    - This allows connectivity to the Internet
5) Enable Adapter 2 to Internal Network and input the desired name
    - This allows private connectivity between the VMs
6) Repeat steps 1-5 for the other VMs

# Test and Troubleshoot Virtual Lab Setup
Turn on the VMs to test connectivity

For my lab setup, I have set static IP addreses for each VM

DC1 (Domain Controller w/ DNS)  
IPv4 Address: 192.168.0.10  
Subnet: 255.255.255.0  
Default Gateway: 192.168.0.1  
Preferred DNS Server: 192.168.0.10  
Alternate DNS Server: 192.168.0.20  

Server1 (DHCP, DNS(Secondary), Other services)  
IPv4 Address: 192.168.0.20  
Subnet: 255.255.255.0  
Default Gateway: 192.168.0.1  
Preferred DNS Server: 192.168.0.20  
Alternate DNS Server: 192.168.0.10  

Win11Client (Static IP)
IPv4 Address: 192.168.0.2  
Subnet: 255.255.255.0  
Default Gateway: 192.168.0.1  
Preferred DNS Server: 192.168.0.10  
Alternate DNS Server: 192.168.0.20  

Commands to use:
- ipconfig /all (To view device's network configuration)  
- ping 8.8.8.8 (Internet Connectivity)  
- ping x.x.x.x (To other devices)  

# Issues I Encountered/Troubleshooting
50 - OS Not Found when I tried to boot the VMs. This occurs if you exit out of the initial install  
of the Windows OS. IT IS IMPORTANT TO KEEP THE VMS ON AFTER CREATION OF THE VMS. To fix the issue,  
I re-installed the VMs

51 - VDI could not be found and even after trying to boot up with the ISO. Like I said earlier, IT  IS IMPORTANT TO KEEP THE VMS ON AFTER CREATION OF THE VMS. After I initially created the VMs, I   decided to shut down the VM when it was first created. The next day the error appeared. To fix   this, I re-installed the VMs

52 - Ping Tests Unsuccessful. After configuring the IP addresses, I tried pinging from each device to ensure there is   connectivity. I kept getting "Destination Host Unreachable." First thing I checked was the network adapters for each VM, ensuring that the same Internal network was present in each one. The last thing that I checked was the Windows Firewall. By default, Windows disables inbound ICMP traffic.

In the VMs, search for "Windows Defender Firewall with Advanced Security"  
In the Inbound Rules, look for "File and Printer Sharing(Echo Request - ICMPv4-In)" and enable it
# pfSenseOnVmware
pfSense Firewall Installation &amp; Basic Configuration  With Vmware 

📌------Overview------📌

With this guide you will learn how to install and configure pfSense as a virtual firewall on VMware also I made it with Kali Linux 

🧰-----------Requirements-------------🧰 

.VMware Workstation 
.pfSense ISO file(you can download from here https://www.pfsense.org/download/)
.Kali Linux operation system on VMware

::::::::::::Step By Step:::::::::::::

1.Open Vmware and than Create Virtual Machine


2.Choose:Typical


3.Choose the Iso file from next to the Select Installer Disk Image File(ISO) 


4.You can name the way you want but to  make it clear pfSense Firewall will be more accurate 


5.You can choose the disk size between 10gb-20gb depens on your storage 


6.Upscale the ram to 2gb 


7.Make sure there is 2 CPU 


8.And last thing is add new Network Adapter so you must have 2 network adapter


9.First network adapter must be set up as NAT(WAN) = that will be the way out for connection to the outside world


10.The second network adapter has to be Host-Only or custom network = with this local area network we can connect devices in to it 


11.Finish and Start The Virutal Machine


12.pfSense first boot there will be a Installion keep going with next 


13.After the installion we need to reboot the system


14.After the reboot you will see WAN LAN selection  screen em0 - em1 


15.For the WAN(For the outside internet connection) select the em0 = IP Address will come via DHCP 


16.For the LAN(For the inside comminication) select em1 = IP Address will be like for example 192.168.1.1/24 


17.After the selections Press Enter 


18.At the end you will see pfSense console menu like multy options (1.Assign Interfaces 2.Set IP address etc.)


19.At this point we have successfuly done with pfSense setup now time to connect our kali linux virtual machine to pfSense


📌------------------------------------Connections Between pfSense And Kali Linux------------------------------------📌


1. Befor power up our kali linux make sure to change the ethernet adapter to (Host-Only or Custom Network) thats how our kali linux operation system cannot communicate with outside word 


2.Now we can start the Kali 


3.Open the Terminal 


4.type  ip a then enter = with this terminal code we can see eth0 or ens33 with their assigned IP addresses


5.If has no IP addresses than type sudo dhclient 


6.If this option also does not work than type this command
sudo ip addr add 192.168.1.100/24 dev eth0
sudo ip route add default via 192.168.1.1
echo "nameserver 8.8.8.8" | sudo tee /etc/resolv.conf

we are giving ip address, default route and DNS address with admin autority 


7.After that we can test it ping 192.168.1.1 and ping 8.8.8.8 


8.Now we are successfly connected  to pfSense 


📌------------------------------------Settings And ------------------------------------📌








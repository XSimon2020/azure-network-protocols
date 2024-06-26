# azure-network-protocols


<p align="center">
<img width="559" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/52119721-42b1-4188-bfdc-9d4f2d7fe3a3">
</p>

<h1>Inspecting Traffic By Protocols Between Azure Virtual Machines</h1>
This demonstration outlines a simulation for ticket lifecycles in osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machines

- Microsoft Remote Desktop

- PowerShell

- Network Protocols (ICMP, SSH, DHCP, DNS, RDP)

- Wireshark (Protocol Analyzer)
- Network Security Groups
  

<h2>Operating Systems Used </h2>

- macOS

- Windows 10 Pro </b> (21H2)

- Ubuntu Server 20.04 LTS </b>

<h2>Steps</h2>

<p>
1) <b>Create Windows 10 Pro virtual machine.</b><br/>
On portal.azure.com, go to the section as shown in the screenshot to create a new vm. When typing out the information for creating the vm, do it as it is shown in the screenshots besides the username and password that will be unique to you. Be sure to check the checkbox for licensing and hosting rights. Click "Review + create" and then click "Create" after validation has passed.
<img width="1800" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/9f783442-f953-4b9a-a1e5-7449f61a2e82">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/4b2d40be-2a5f-415e-bc10-41e42cdd5edd">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/072c93cd-5dce-4c00-b44d-1ecb41c68eab">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/22fd4339-1597-481d-8ba1-fe15bcb9dd87">
</p>
<br/>

<p>
2) <b>Create Ubuntu Server 20.04 LTS virtual machine.</b><br/>
Start creating the next vm and type out the information as it is shown in the screenshot. Preferably use the same username and password typed out when creating the previous vm. Click "Next:Disks >"->"Next:Networking" and make sure this vm is configured for the same virtual network as the previous vm. Click "Review + create" and then click "Create" after validation has passed.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/4ac04608-632a-4279-aba9-359336a5a6ce">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/97f6053e-1952-48f3-98f0-3ca8e9fcbcc8">
</p>
<br/>

<p>
3) <b>Log into Windows 10 Pro virtual machine.</b><br/>
Copy the public IP address for the Windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
<br/>

<p>
4) <b>Install Wireshark.</b><br/>
Go to the search bar in Microsoft Edge within the vm to type out "wirehshark download" for downloading and installing Wirehsark. Be sure to click "Windows x64 Installer" to get the correct variant of Wireshark. Open the file and go through the setup to install Wireshark.
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/e941f031-ccdf-4e64-a29e-c0691a0673cc">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/9a0af9d6-ac55-4411-8777-2990b04b7db9">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6b5a3bea-c43a-4dff-b168-b51079fd19ec">
</p>
<br/>

<p>
5) <b>Observe ICMP traffic.</b><br/>
Search for Wireshark and Windows Powershell using the search bar at the bottom left of the vm's desktop and have both programs opened up. Go back to Microsoft Azure to acquire the private IP address of the other vm that was created and copy it. Go back to the Windows 10 Pro vm and type "ping -t" with the private ip address of the other vm to start a perpetual ping. Type out "icmp" on Wireshark then double-click "Ethernet" to start observing ICMP traffic. 
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6be066d7-a497-4c08-af8a-793d6271f25b">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/7fe17802-101b-4d24-861e-02b75dd86ff2">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/7ca5d70c-6387-401d-a443-64392ad50715">
</p>
<br/>

<p>
6) <b>Block ICMP traffic from the Windows vm.</b><br/>
Go back to Microsoft Azure and get to the network settings of the Linux vm that is receiving perpetual ICMP traffic from the Windows vm. Type out "network security groups" then click for the Linux vm nsg. Click "Inbound security rules" underneath "Settings" on the left side of the screen then click "Add". Configure the settings to how it is shown in the screenshot then click "Add" to add the new rule. This should cause the perpetual ping coming from the Windows vm to time out, so go back to that vm to confirm it. You can delete the rule for ping traffic to start flowing again and press "command+C" within Windows Powershell to stop the traffic.  
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a5e4e294-c164-4d96-8146-e579b0a3620e">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/caa79ca6-65a9-4a54-b304-82e6a76d0583">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a165660d-f094-4d0e-977f-0349616c5f14">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/3a8051cd-0498-4fc3-8aa0-6e88b30d82b9">
<img width="1200" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/34195792-41d7-4c3c-839f-2e1f208ecded">
<img width="664" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a0ae9e09-6ecb-4cee-abb3-1de6755b672b">
</p>
<br/>

<p>
7) <b>Observe SSH traffic.</b><br/>
On Windows Powershell within the Windows vm, type "ssh" then the private IP address of the Linux vm. Type "yes" to continue connecting to the command line of the Linux vm. Type out the password given for the Linux vm when setting it up once prompted to. Note that typing out the password would look invisible, so be sure that it is typed correctly. Type "exit" on Windows Powershell to exit it out of the Linux mv's command line.
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/c7127027-256d-4412-83ef-1c494817da9a">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/fb3eef6c-96cb-4aed-be6a-4cd348ebdda6">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/e0f87b45-e8fa-4e3a-95d5-577cae82585b">
</p>
<br/>

<p>
8) <b>Observe DHCP traffic.</b><br/>
Type "dhcp", "udp.port==67",or "udp.port==68" then press 
"Enter" on Wireshark to filter out all traffic except DHCP traffic. On Windows Powershell, type "ipconfig /renew" to change the public IP address of the Windows vm and observe how Wireshark captures this.
<img width="1204" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/d844582c-5a50-4b42-9cbf-7dfaa23c187e">
</p>
<br/>

<p>
9) <b>Observe DNS traffic.</b><br/>
Type "dns" or "udp.port==53" then press "Enter" on Wireshark to filter out all traffic except DNS traffic. Asides from the DNS traffic already captured, type "nslookup google.com" and notice the traffic that Wireshark picked up on when finding out the various IP addresses that Google uses.
 <img width="1204" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/50152503-858e-4e88-840e-a6a80c413471">
</p>
<br/>

<p>
10) <b>Observe RDP traffic.</b><br/>
Using only Wireshark, type "rdp" then press "Enter" to filter out all traffic but RDP traffic. Afterwards, type "tcp.port==3389" then press "Enter" and notice the perpetual capture of traffic that is occurring. This is due to the continous communication established between the Windows vm and your physical os device behind the scenes.
</p>
<br/>

<b>This marks the end of the demonstration.<b>











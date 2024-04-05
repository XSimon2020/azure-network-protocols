# azure-network-protocols


<p align="center">
<img width="559" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/52119721-42b1-4188-bfdc-9d4f2d7fe3a3">
</p>

<h1>osTicket - Ticket Lifecycle Examples</h1>
This demonstration outlines a simulation for ticket lifecycles in osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine (VM)
- Remote Desktop

<h2>Operating Systems Used </h2>

- macOS

- Windows 10 Pro VM</b> (21H2)

- Ubuntu Server 20.04 LTS VM</b>

<h2>List of Prerequisites</h2>

- Microsoft Azure

- Microsoft Remote Desktop

<h2>Steps</h2>

<p>
1) Create Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5649a472-8c50-4686-b28a-787be6cee83b">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/4b2d40be-2a5f-415e-bc10-41e42cdd5edd">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/072c93cd-5dce-4c00-b44d-1ecb41c68eab">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/22fd4339-1597-481d-8ba1-fe15bcb9dd87">
</p>
On portal.azure.com, go to the section as shown in the screenshot to create a new vm. When typing out the information for creating the vm, do it as it is shown in the screenshots besides the username and password that will be unique to you. Be sure to click the checkbox for licensing. Click "Review + create" and then click "Create" after validation has passed.
<p>
<br/>

<p>
2) Create Ubuntu Server 20.04 LTS VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/4ac04608-632a-4279-aba9-359336a5a6ce">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/97f6053e-1952-48f3-98f0-3ca8e9fcbcc8">
</p>
 Start creating the next vm and type out the information as it is shown in the screenshot. Preferably use the same username and password typed out when creating the previous vm. Click "Next:Disks >"->"Next:Networking" and make sure this vm is configured for the same virtual network as the previous vm. Click "Review + create" and then click "Create" after validation has passed.
<p>
<br/>

<p>
3) Log into Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
Copy the public IP address for the windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<p>
<br/>

<p>
4) Install Wireshark.
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/e941f031-ccdf-4e64-a29e-c0691a0673cc">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/9a0af9d6-ac55-4411-8777-2990b04b7db9">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6b5a3bea-c43a-4dff-b168-b51079fd19ec">
</p>
Go to the search bar in Microsoft Edge within the vm to type out "wirehshark download" for downloading and installing Wirehsark. Be sure to click "Windows x64 Installer" to get the right variant of Wireshark. Open the file and go through the setup to install Wireshark.
<p>
<br/>

<p>
5) Explore ICMP traffic.
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/fd2661a8-402a-429d-9451-70c27952021c">
<img width="1201" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6be066d7-a497-4c08-af8a-793d6271f25b">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/7fe17802-101b-4d24-861e-02b75dd86ff2">
<img width="1109" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/7ca5d70c-6387-401d-a443-64392ad50715">
</p>
Search for Wireshark and Windows Powershell using the search bar at the bottom left of the vm's desktop and have both programs opened up. Go back to Microsoft Azure to acquire the private IP address of the other vm that was created and copy it. Go back to the Windows 10 Pro vm and type "ping -t" with the private ip address of the other vm to start a perpetual ping. Type out "icmp" on Wireshark then double-click "Ethernet" to start observing ICMP traffic. 
<p>
<br/>

<p>
6) Log into Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
Copy the public IP address for the windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<p>
<br/>

<p>
7) Log into Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
Copy the public IP address for the windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<p>
<br/>

<p>
8) Log into Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
Copy the public IP address for the windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<p>
<br/>

<p>
9) Log into Windows 10 Pro VM.
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/6bee73d9-c96a-4ebd-b37b-3b4188e02f05">
<img width="998" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/5b9edd1e-292b-4a06-a5aa-84fa60f4c4c4">
<img width="443" alt="image" src="https://github.com/XSimon2020/azure-network-protocols/assets/111246513/a1cc75ab-cba0-4e9d-b603-b81e8e1f22d4">
</p>
Copy the public IP address for the windows vm then paste it onto Microsoft Remote Desktop after clicking to add a new PC. Put the username and password you typed out when setting up the vm to log in.
<p>
<br/>









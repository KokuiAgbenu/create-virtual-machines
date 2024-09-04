<p align="center">
  
![image](https://github.com/user-attachments/assets/cbea1f9e-27d8-46eb-b301-e90a4a41697b)

</p>

<h1>Creating Multiple Azure Virtual Machines On The Same Network</h1>
In this tutorial, we create two Azure virtual machines and observe the succesful pings between them to ensure they're on the same network.  <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Creating Multiple Azure VMs in The Same Network](https://youtu.be/E1hj79hndJo)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Windows Powershell
- Network Protocol ICMP
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1: Create a resource group within Azure.
- Step 2: Create a virtual machine, virtual network and subnet.
- Step 3: Create a second virtual machine and ensure this virtual machine is in the same resource group and virtual network as the first virtual machine created.
- Step 4: Use remote desktop to connect to the first virtual machine.
- Step 5: Download Wireshark on the first virtual machine.
- Step 6: From within VM1 ping VM2 using its private IP address and observe the successful pings in Wireshark.

<h2>Actions and Observations</h2>

<p>

![image](https://github.com/user-attachments/assets/5db0727e-75ee-46a4-a649-a2a2cf01eb35)

</p>
<p>
After creating the resource group, the first virtual machine, virtual network, and subnet (walkthrough found in the tutorial video above) create the second virtual machine and put it in the same virtual network as virtual machine one. The highlighted virtual network above is the same as the one created during the creation of virtual machine 1 (VM1).
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/5e776080-619b-48e2-851b-0474039b5ae4)
![image](https://github.com/user-attachments/assets/0b2cd230-6220-41cc-b22c-46a4c4acddb0)

</p>
<p>
Use Windows Remote Desktop Connection to connect to VM1 using its public IP address and the username and password created during the Azure virtual machine creation process.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/3fa84707-2b6b-4c15-b39a-fd3af0c6dfd4)

</p>

<p>
When connected to VM1, download Wireshark to use as a packet analyser to observe the pings between VM1 and VM2.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/8c099887-21e5-4643-a7bf-c45227cd3fdd)

<p>
With Wireshark open (within VM1), filter the traffic by ICMP protocol and ping the private IP address of VM2 using Windows Powershell.
</p>
  
</p>
<br />

<p>
<img src="https://i.imgur.com/w8eNhQJ.png" height="80%" width="80%" alt="Wireshark filtered by ICMP traffic"/>

<p>
Observe the succesful pings between VM1 and VM2 using VM2's private IP address, confirming that the two VMs are on the same network.
</p>
 
</p>
<br />

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Virtual Machine that will automatically create a Resource Group in Azure
- Create a Virtual Network and Subnet
- Create the Domain Controller VM (Windows Server 2022) named "DC-1"
- Create the Client VM (Windows 10) named "Client-1"
- Set the NIC's Private IP address to be static


<h2>Deployment and Configuration Steps</h2>

<p>
<h3>Step 1</h3>The very first step is to create a Virtual Machine in Azure. In Azure, when you create a VM, a Resource Group will automatically be created. The very first VM that we will create is a Windows Server 2022 machine that will be our Domain Controlled. We will name this "DC-1". Take note of the Region that you placed this VM in as you want the same Region for the Client-1 machine once that is created. 
</p>
<p>
<img src="https://i.imgur.com/2MvyY8e.png" height="80%" width="80%" alt="Configuration"/>
</p>
<p>
  <img src="https://i.imgur.com/51nioYx.png" height="80%" width="80%" />
</p>
<p>
Make sure that your configurations look like the the screenshots above.<br><br>
  <b>Note:</b> you will be asked to create a username and password for admin rights. Go ahead and create that to your liking, just make sure you remember your credentials as you will need them later on in this lab. 
</p>
<br />

<h3>Step 2</h3>
<p>Next we want to create a second VM only this time we want to set the Image for Windows 10. Also making sure that you are in the same Resource Group that was created for step 1, and make sure you are on the same Region. Check configurations with the screenshot below. </p>
<img src="https://i.imgur.com/cSV3Ina.png" height="80%" width="80%" /><br>
<p>Click Next: Disk and then Next: Networking on the lower part of the portal. Before we Review and Create this VM we want to make sure that it is in the same virtual network and subnet. In this section we want to make sure we click on "AD-Lab-vnet" or whatever you named your resource group, usually it is the defualt selection, the same for the Subet drop down menu. Now, we wait for the machine to be created.</p>
<p>
  <img src="https://i.imgur.com/MDQild4.png" height="80%" width="80%" /><br>
</p>

<p>
  <h3>Step 3</h3>
The very next step is to set the Domain Controllers IP address to Static as the default is Dynamic. To do this click on the DC-1 VM in the VM section of Azure. On the left hand menu you will see Networking.
<img src="https://i.imgur.com/YBj9dtZ.png" height="80%" width="80%" /><br>
Once in the Networking section, click on the "Network Interface:" The one in the screenshot below is dc-1354_z1, your machine might have a different interace name but it will be in the same section.
<img src="https://i.imgur.com/irTlvzM.png" height="80%" width="80%" />
In the Network Interface section, you will see a section on the left that is called "Settings" and under Settings you will see IP configuration. Click that. Once in the IP Configuration section you will see ipconfig1. Click on that and make sure that you have the Assigned IP address set to "Static" like the image below. Make sure to hit Save at the top.
<img src="https://i.imgur.com/2Do6Yo8.png" height="80%" width="80%" />

</p>
  <br />

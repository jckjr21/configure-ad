<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure
- Install Active Directory
- Join Client-1 to your domain
- Create additional users and attempt to log into client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

<p>
  <img width="430" alt="image" src="https://github.com/jckjr21/configure-ad/assets/142818746/f62c493d-377b-4fc9-9bc6-eca8fc8b7d38">
</p>
<p>

1. Create the Domain Controller VM (Windows Server 2022) named “DC-1”

    a. Take note of the Resource Group and Virtual Network (Vnet) that get created at this time
  
2. Set Domain Controller’s NIC Private IP address to be static

3. Create the Client VM (Windows 10) named “Client-1”. Use the same Resource Group and Vnet that was created in Step 1.a

4. Ensure that both VMs are in the same Vnet (you can check the topology with Network Watcher

<br />

<p>
 <img width="377" alt="image" src="https://github.com/jckjr21/configure-ad/assets/142818746/b12f9e42-77bd-42be-9c14-7bebc65f0b8a">
</p>
<p>

1. Login to DC-1 and install Active Directory Domain Services


2. Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)


3. Restart and then log back into DC-1 as user: mydomain.com\labuser


</p>
<br />

<p>
 <img width="667" alt="image" src="https://github.com/jckjr21/configure-ad/assets/142818746/c007664c-f2e2-4f92-a204-c56fb6b8ada6">
</p>
<p>

1. Login to DC-1 as ("created user name"_admin)
  
2. Open PowerShell_ise as an administrator

3. Create a new File and paste the contents of the script into it

4. Run the script and observe the accounts being created

5. When finished, open ADUC and observe the accounts in the appropriate OU

6. Attempt to log into Client-1 with one of the accounts (take note of the password in the script)

</p>
<br />

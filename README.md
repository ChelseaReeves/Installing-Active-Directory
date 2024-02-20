<p align="center">
<img src="https://i.imgur.com/gLK8kv9.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1 align = "center">Installing Active Directory in Azure </h1>
This tutorial serves as additional info from the previous lab, focusing on the configuration of the Active Directory.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Installment and Configuration Steps</h2>

<p>
Now that the Active Directory is successfully installed on the domain controller VM, the next step is to create new Organizational Units called ‘_EMPLOYEES’ and ‘_ADMINS’
</p>
<p align="center">
<img src="https://i.imgur.com/Zsk9KuG.png" height="45%" width="45%" />

<p>
In the Employee (OU), I established a new employee profile for 'Jane Doe', I created and added the account 'jane_admin' to the 'Domain Admins' security group.
</p>
<p align="center">
<img src="https://i.imgur.com/7cJaZvU.png" height="45%" width="45%" />
<p align="center">
<img src="https://i.imgur.com/8oCFy2u.png" height="45%" width="45%" />
  
<p>
Next I logged out and closed the Remote Desktop connection to DC-1. Upon re-login, I used the credentials 'mydomain.com\jane_admin.' From this point forward, I will exclusively utilize 'jane_admin' as the administrative account.
</p>
<p align="center">
<img src="https://i.imgur.com/THbcicK.png" height="45%" width="45%" />
<p align="center">
<img src="https://i.imgur.com/d6sliqo.png" height="45%" width="45%" />

<p>
I configured Client-1's DNS settings in the Azure Portal to DC’s Private IP address.
</p>
<p align="center">
<img src="https://i.imgur.com/4TBfVJz.png" height="45%" width="45%" />

<p>
From the Azure Portal, I restart and log in to the remote desktop of Client-1 as the original admin (chels31218), then join it to the domain. The computer is restarting
</p>
<p align="center">
<img src="https://i.imgur.com/TUjM9AA.png" height="45%" width="45%" />
<p align="center">
<img src="https://i.imgur.com/P0mzPtK.png" height="45%" width="45%" />

<p>
In the Domain Controller's Remote Desktop environment, I confirm the presence of Client-1 within the 'Computers' container in Active Directory Users and Computers (ADUC) at the root of the domain.
</p>
<p align="center">
<img src="https://i.imgur.com/CQYSgcI.png" height="45%" width="45%" />

<p>
I log in to Client-1 using the credentials mydomain.com\jane_admin. Afterward, I access system properties, proceed to the 'Remote Desktop' settings, and grant remote desktop access to 'domain users.
</p>
<p align="center">
<img src="https://i.imgur.com/7qidnMk.png" height="50%" width="50%" />

<p>
I am now able to log into Client-1 using a non-administrative user account.
Using the credentials of 'jane_admin,' I access DC-1 and then open PowerShell_ISE as an administrator.
</p>
<p align="center">
<img src="https://i.imgur.com/kjTvZI3.png" height="60%" width="60%" />

<p>
I generate a new file, paste the script contents into it, and proceed to execute the script. Following that, I examine the accounts that have been created.
</p>
<p align="center">
<img src="https://i.imgur.com/sCPxZfB.png" height="70%" width="70%" />

<p>
After completion, I launch ADUC to observe the accounts within the employee OU. Successfully, I log into Client-1 using the user account 'bego.gip’.
</p>
<p align="center">
<img src="https://i.imgur.com/st8wZPo.png" height="50%" width="50%" />

<p>
Thank for dropping by!
</p>

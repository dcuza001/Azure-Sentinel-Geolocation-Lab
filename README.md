
<h1>Failed RDP to IP Geolocation Information</h1>




<h2>Description</h2>
<b>The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.
</b>
<br />
<br />
I setup Microsoft Sentinel (SIEM) and connected it to a live Azure virtual machine acting as a honey pot.
I then observed live attacks (RDP Brute Force) from all around the world. I used a custom PowerShell script to
look up the attackers geolocation information and plot it on an Azure Sentinel Map.
In order to create custom fields/labels from the raw data extracted with the PowerShell script, I also had to use the included custom KQL query.
With the location data from this query, I could make the map in Sentinel to plot the attack points geographically!
<br />
<br />

- Before and after pinging the VM after turning off it's firewall to be more easily discovered/respond to ICMP

<p align="center">
<img height="85%" width="85%" alt="Screen Shot 2024-10-23 at 6 38 24 PM" src="https://github.com/user-attachments/assets/33e097a0-b376-44eb-bb70-dd40fb38a743">
</p>
<h2>Key Technologies</h2>

- <b>PowerShell:</b> Extract RDP failed logon logs from Windows Event Viewer 
- <b>Microsoft Sentinel:</b> Microsoft's SIEM for real-time analytics and mapping of cyber attacks
- <b>Microsoft Azure Virtual Machine:</b> Set up inside Azure cloud environment as a honeypot to monitor/analyze RDP brute force attacks

<h2>Geolocation API Used</h2>

- <b>ipgeolocation.io:</b> IP Address to Geolocation API


<h2>Attacks from Ukraine coming in; Custom logs being output with geodata</h2>

<p align="center">
<img height="85%" width="85%" alt="Screen Shot 2024-10-23 at 11 09 11 PM" src="https://github.com/user-attachments/assets/8e22e961-6f59-4dea-a8be-0e4bb93b7c19">
</p>

- After taking a closer look at the final logs, we can see many failed logins from the Ukraine with username attempts like "ADMINISTRATOR," "ADMIN1," "ACCOUNTS," "BILLING," and other common names of people and departments

  
<p align="center">
<img height="85%" width="85%" alt="Screen Shot 2024-10-24 at 12 02 48 AM" src="https://github.com/user-attachments/assets/4950e893-deb3-436a-81df-f30425795328">
</p>


<h2>World map of incoming attacks after around 12 hours (built custom logs including geodata)</h2>

<p align="center">
<img height="85%" width="85%" alt="Screen Shot 2024-10-24 at 5 34 33 PM" src="https://github.com/user-attachments/assets/744359c6-70f7-4c25-8f79-0039d8588360">
</p>



<!--

 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

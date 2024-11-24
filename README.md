<p align="center">
<img src="https://i.imgur.com/sZVzrrQ.png" alt="Azure Sentinel Logo"/>
</p>

<h1>Azure Sentinel (SIEM) Tutorial with Map of Live Cyber Attacks</h1>
This tutorial outlines the implementation of an SIEM within Azure Virtual Machines. The environment utilizes Microsoft Azure Sentinel, Remote Desktop, and Windows 10. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure Sentinel (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Resources in Azure
- Create Log Analytics Workspace
- Enable gathering VM logs in the Security Center
- Setup Azure Sentinel
- Create custom fields/extract fields from raw custom log data
- Setup map in sentinel with Latitude and Longitude (or country)

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/Y1wnBlJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Resource Group and VM
</p>
<br />

<p>
<img src="https://i.imgur.com/3gntJtQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a new NIC by clicking advanced
</p>
<br />

<p>
<img src="https://i.imgur.com/SW0mXPc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Remove the default NIC
</p>
<br />

<p>
<img src="https://i.imgur.com/SW0mXPc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add Inbound Rules
</p>
<br />

<p>
<img src="https://i.imgur.com/NiW5unD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/KtjmMF2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a Logs Analytics Workspace
</p>
<br />

<p>
<img src="https://i.imgur.com/K83UwFs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name the Analytics Workspace
</p>
<br />

<p>
<img src="https://i.imgur.com/MVFhzlQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Turn on Microsoft Defender
</p>
<br />

<p>
<img src="https://i.imgur.com/NrOjt6w.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Turn SQL Servers Off for the honeypot and click save
</p>
<br />

<p>
<img src="https://i.imgur.com/FFGq3uD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Refresh the page and install Data Collections
</p>
<br />

<p>
<img src="https://i.imgur.com/P7KTU79.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to environment settings, open Azure Subscription, and click on the honeypot
</p>
<br />

<p>
<img src="https://i.imgur.com/HD3YAOY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Data Collection, select All Events, and save
</p>
<br />

<p>
<img src="https://i.imgur.com/QWGI6uI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to the log analytics workspace to connect it to the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/Coft8wn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the log analytics workspace and click on virtual machines on the left
</p>
<br />

<p>
<img src="https://i.imgur.com/0KVE0oD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on the VM created at the beginning
</p>
<br />

<p>
<img src="https://i.imgur.com/o0XjLew.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click connect
</p>
<br />

<p>
<img src="https://i.imgur.com/P0qYph1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Setup Sentinel
</p>
<br />

<p>
<img src="https://i.imgur.com/bqvgDTn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Choose the honeypot
</p>
<br />

<p>
<img src="https://i.imgur.com/NLoe1f6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to the main page on Azure and click on the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/zDjHS9m.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Copy the public IP Address
</p>
<br />

<p>
<img src="https://i.imgur.com/DVdXBtH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the remote desktop and log into the machine with the credentials that were created in the beginning. Purposefully put in the wrong password on the first try.
</p>
<br />

<p>
<img src="https://i.imgur.com/OxymI2u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The initial password input was wrong. This will be logged for us to see.
</p>
<br />

<p>
<img src="https://i.imgur.com/YD945KJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once logged in, go to Event Viewer
</p>
<br />

<p>
<img src="https://i.imgur.com/kp6vweV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to Windows Logs and Security on the left
</p>
<br />

<p>
<img src="https://i.imgur.com/u1w2Jau.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here we can see our login failure
</p>
<br />

<p>
<img src="https://i.imgur.com/93t09Ln.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You can double-click to see the details of that log
</p>
<br />

<p>
<img src="https://i.imgur.com/tfLdMxA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, try to log in again, but this time, put in the wrong username and password.
</p>
<br />

<p>
<img src="https://i.imgur.com/mgazUXV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login attempt with the wrong username
</p>
<br />

<p>
<img src="https://i.imgur.com/1rFWLKp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, an IP address shows from the attempted login.
</p>
<br />

<p>
<img src="https://i.imgur.com/CRlFHpI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open the firewall on the VM. wf.msc in the search bar
</p>
<br />

<p>
<img src="https://i.imgur.com/ThycBdp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on Windows Defender Firewall properties
</p>
<br />

<p>
<img src="https://i.imgur.com/otU6e00.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Ping the VM's IP Address and notice that echo requests are allowed, and we are getting return messages
</p>
<br />

<p>
<img src="https://i.imgur.com/7NnMtd8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Turn off the Domain, Public, and Private firewalls and click apply
</p>
<br />

<p>
<img src="https://i.imgur.com/H710fL6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Launch Powershell ISE and copy and paste the Log Exporter script
</p>
<br />

<p>
<img src="https://i.imgur.com/jCbQ72U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Make an account on ipgeolocation.io and copy and paste your API key into the script
</p>
<br />

<p>
<img src="https://i.imgur.com/ziPaknT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The script is a loop that runs perpetually and looks through the event viewer and security log, grabs the IP addresses of failed logins and geo locates them, and creates a new log file
</p>
<br />

<p>
<img src="https://i.imgur.com/DMRWJ6d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The file will be created in the ProgramData file, which you must access manually.
</p>
<br />

<p>
<img src="https://i.imgur.com/ZdmWUIF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Run the script to see the failed login file being created from the failed attempts earlier
</p>
<br />

<p>
<img src="https://i.imgur.com/uZ0JS8p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to log analytics workspaces
</p>
<br />

<p>
<img src="https://i.imgur.com/6YhzFUR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to custom logs and add a custom log
</p>
<br />

<p>
<img src="https://i.imgur.com/T7nyr4h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Copy and paste the logs within the VM file
</p>
<br />

<p>
<img src="https://i.imgur.com/t12IHCU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a text file on your computer, paste the logs, and save it on your desktop to upload to the custom logs on Azure
</p>
<br />

<p>
<img src="https://i.imgur.com/vK2DGHN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Upload the custom log
</p>
<br />

<p>
<img src="https://i.imgur.com/2HhzEri.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Hit next, and it should look like this
</p>
<br />

<p>
<img src="https://i.imgur.com/DQlHP3R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Direct the custom log on Azure to be fetched from the file on the VM
</p>
<br />

<p>
<img src="https://i.imgur.com/f513rq2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name the custom log
</p>
<br />

<p>
<img src="https://i.imgur.com/eeXgRJ9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Head over to Log analytics workspaces and to the honeypot logs on the bottom left. Run a search query on the log file to show the failed attempts.
</p>
<br />

<p>
<img src="https://i.imgur.com/nEkDEaf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click and click extract fields from.
</p>
<br />

<p>
<img src="https://i.imgur.com/9FgYHuN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Highlight the fields to extract them
</p>
<br />

<p>
<img src="https://i.imgur.com/12wsGTp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Check to see if the extraction is properly trained and save
</p>
<br />

<p>
<img src="https://i.imgur.com/HI4vmD3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat steps for longitude and modify incorrect data to train the algorithm
</p>
<br />

<p>
<img src="https://i.imgur.com/FNxTrDB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat steps for the destination host
</p>
<br />

<p>
<img src="https://i.imgur.com/yXW4gPz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat the steps for the username
</p>
<br />

<p>
<img src="https://i.imgur.com/5EDaalf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat steps for sourcehost
</p>
<br />

<p>
<img src="https://i.imgur.com/cR8mwmH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat steps for State
</p>
<br />

<p>
<img src="https://i.imgur.com/gm9ghQy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat steps for Country
</p>
<br />

<p>
<img src="https://i.imgur.com/UHKauOy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Repeat the steps for the label
</p>
<br />

<p>
<img src="https://i.imgur.com/geBoyGm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, finish up with the timestamp
</p>
<br />

<p>
<img src="https://i.imgur.com/XFfPYzw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Run the query again and notice the custom fields that have been created. On subsequent logs, they will be properly parsed out
</p>
<br />

<p>
<img src="https://i.imgur.com/M47ciYc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on custom logs and custom fields to see the fields
</p>
<br />

<p>
<img src="https://i.imgur.com/H0KQAMF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to Azure Sentinel
</p>
<br />

<p>
<img src="https://i.imgur.com/vmC692M.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add a new Workbook on the left
</p>
<br />

<p>
<img src="https://i.imgur.com/Fwzr6DV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Add a new workbook and edit
</p>
<br />

<p>
<img src="https://i.imgur.com/oIt8BQ7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Remove the default widgets
</p>
<br />

<p>
<img src="https://i.imgur.com/2b1SteH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Edit and run query with a map visualization. Choose country as location info
</p>
<br />

<p>
<img src="https://i.imgur.com/ks5F1rf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set map settings and labels
</p>
<br />

<p>
<img src="https://i.imgur.com/X9znNU5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set additional map settings and labels. Now, you can observe as you track the hackers worldwide!
</p>
<br />

<p>
<img src="https://i.imgur.com/dwrk3Lg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Roughly 30 minutes after the lab has been completed
</p>
<br />

<p>
<img src="https://i.imgur.com/1hI68xX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Roughly 7 hours after the lab was complete
</p>
<br />

<p>
<img src="https://i.imgur.com/kgBCK3L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Approximately 12 hours after lab completion
</p>
<br />

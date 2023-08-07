# Cybersecurity Project
<h1>Welcome to My Cybersecurity Projects Page!<br/></h1>
<h4>My name is Michael Chronicle.  I'm having a great time learning about Cybersecurity along with some of the software used in the space. Please reach out if you have any questions.<br/></h4>
<h4><a href="https://github.com/mchronicle/cybersecurity">Cyber Security Project</a><br/> <a href="https://www.linkedin.com/in/michael-chronicle/">Cyber Security Professional - LinkedIn</a></h4>

<h2>Cybersecurity Project Using Microsoft Azure and Sentinel:</h2>
<p>In this project, I created a honeynet using Microsoft Azure. I have included the steps below:<br/>
- Created an Azure account<br/>
- Created one subscription<br/>
- Created one Resource Group<br/>
- Deployed two Virtual Machines in the same region<br/>
<li>Windows VM</li>
<li>Linux VM</li><br/>
- Deployed one VM in a different region and a different Virtual Network<br/>
<li>Windows VM (used as an attack VM against the previously mentioned VMs for testing)</li></p>
<p>All with the Security type being Standard in order to ensure vulnerability</p><br/>
- Configured the Firewall in Network Security Group (NSG) to let all traffic in<br/>
- All ports were left open<br/>
- Logged into the Windows VM via Remote Desktop Protocol (RDP) and changed the Firewall state to Off<br/>
- Installed SQL Server 2022 on the Windows VM<br/>
- Installed SQL Server Management Studio<br/>
- Enabled logging for SQL Server to Windows Event Viewer (for successful and failed logins)<br/>
- Installed Azure Active Directory<br/>
- Created users and assigned permissions to access different resources<br/>
- Created an Azure Blob Storage account<br/>
- Created Log Analytics Workspace<br/>
- Configured the AuditLogs & SignInLogs in Azure Active Directory.
- Created Sentinel<br/>
- Ingested CSV files that consisted of IP Address blocks along with locations (country, latitude and longitude) into Sentinel from Azure Storage for my attack map<br/>
<p>Ran multiple queries using KQL (Kusto Query Language) after the logs were configured in Log Analytics Workspace</p>
Windows:
<li>SecurityEvent<br/>
| where EventID == 4625<br/>
| count</li><br/>
<li>SecurityEvent<br/>
| where EventID == 4625 and Account == '\\ADMINISTRATOR'<br/>
| where TimeGenerated > ago(10m)<br/>
| count</li><br/>
Network Security Group logs:
<li>AzureNetworkAnalytics_CL<br/>
| where FlowType_s == "MaliciousFlow"</li><br/>
<p>Used PowerShell to ssh into the Linux VM in order to create failed login attempt logs:</p>
Linux:
<li>Syslog<br/>
| where SyslogMessage contains "Mike"<br/>
| order by TimeGenerated desc</li><br/>
<p>Used Microsoft Sequel Server to log into the database in order to create failed login attempt logs:</p>
<li>Event<br/>
| where EventLog == "Application"<br/>
| where Source == "MSSQLSERVER"<br/>
| where RenderedDescription startswith "Login failed"</li><br/>

<h2>Before Hardening:</h2>
![Unsecured_Cloud_Honeynet_and_SOC](https://github.com/mchronicle/cybersecurity/assets/18021322/6c3e9c35-4534-427d-8019-46d72e796ea8)

<h2>After Hardening</h2>
![Hardened_Cloud_Honeynet_and_SOC](https://github.com/mchronicle/cybersecurity/assets/18021322/c0a8a585-ea69-461f-8d11-0e7ba6430400)


<h2>Connect with me:</h2>
<img align="left" alt="Michael Chronicle | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
<a href="https://www.linkedin.com/in/michael-chronicle/">LinkedIn Profile</a><br/>



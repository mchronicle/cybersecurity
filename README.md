# Cybersecurity Project
<h1>Welcome to My Cybersecurity Projects Page!<br/></h1>
<h4>My name is Michael Chronicle.  I'm having a great time learning about Cybersecurity along with some of the software used in the space. Please reach out if you have any questions.<br/></h4>
<h4><a href="https://github.com/mchronicle/cybersecurity">Cyber Security Project</a><br/> <a href="https://www.linkedin.com/in/michael-chronicle/">Cyber Security Professional - LinkedIn</a></h4>

<h2>Security Operations Center (SOC) and Honeynet Using Microsoft Azure and Sentinel:</h2>
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

<h2>Tested failed logins using:</h2>
<li>Microsoft Sequel Server to log into the database</li>
<li>PowerShell to ssh into the Linux VM</li>

<h2>Before Hardening:</h2>
<img src="Unsecured_Cloud_Honeynet_and_SOC_rev.png">

<h2>KQL script for Windows RDP Auth Fail with Attack Map (24HR Period):</h2>
<p>SecurityEvent<br/>
| where EventID == 4625<br/>
| count
</p>
<p>SecurityEvent<br/>
| where EventID == 4625 and Account == '\\ADMINISTRATOR'<br/>
| where TimeGenerated > ago(10m)<br/>
| count
</p>
<img src="windows-rdp-smb-auth-fail_before.PNG">

<h2>KQL script for Network Security Group Inbound Malicious Flows Allowed with Attack Map (24HR Period):</h2>
<p>AzureNetworkAnalytics_CL<br/>
| where FlowType_s == "MaliciousFlow" and AllowedInFlows_d > 0<br/>
| where TimeGenerated >= ago(24h)<br/>
| count
</p>

<p>AzureNetworkAnalytics_CL<br/>
| where FlowType_s == "MaliciousFlow"<br/>
</p>
<img src="nsg-malicious-allowed-in.PNG">

<h2>KQL script for MSSQL Server with Attack Map (24HR Period):</h2>
<p>Event<br/>
| where EventLog == "Application" and Source == "MSSQLSERVER" and RenderedDescription startswith "Login failed"</p>
<img src="mssql-auth-fail.PNG">

<h2>KQL script for Syslog SSH Auth Fail with Attack Map (24HR Period):</h2>
<p>Syslog<br/>
| where SyslogMessage contains "Mike"<br/>
| order by TimeGenerated desc<br/>
<img src="syslog-ssh-auth-fail_before.PNG">

<h2>After Hardening</h2>
<img src="Hardened_Cloud_Honeynet_and_SOC_rev.png">

<h2>Spreadsheet Comparison Showing Before and After:</h2>
<h2>Before Hardening</h2>
<img src="before_securing_environment.png">

<h2>After Hardening</h2>
<img src="after_securing_environment.png">

<h2>Changes in Percentage Once Hardened:</h2>
<img src="secured_percentages.png">

<h2>Connect with me:</h2>
<img align="left" alt="Michael Chronicle | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
<a href="https://www.linkedin.com/in/michael-chronicle/">LinkedIn Profile</a><br/>
<p>Resume:</p>


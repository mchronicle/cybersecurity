# Cybersecurity Project
<h1>Welcome to My Cyber Security Projects Page!<br/></h1>
<h4>My name is Michael Chronicle.  I'm having a great time learning about Cyber Security along with some of the software used in the space. Please reach out if you have any questions.<br/></h4>
<h4><a href="https://github.com/mchronicle/cybersecurity">Cyber Security Project</a><br/> <a href="https://www.linkedin.com/in/michael-chronicle/">Cyber Security Professional - LinkedIn</a></h4>

<h2>Cyber Security Project Using Microsoft Azure and Sentinel:</h2>
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

- <b>Data Structures and Algorithms Practice (AlgoExpert)</b>
  - [Praciting DS & Algos in Python](https://github.com/joshmadakor1/Algorithms-Practice)
- <b>Full Stack Web App (React, NodeJS, Azure, and Machine Learning Components)</b>
  - [Image Analysis Middleware](https://github.com/joshmadakor1/4chan-Image-Analysis-Middleware-C964) <b><i>(Potentially NSFW)</b></i>
- <b>PowerShell</b>
  - [Windows EventLog: Failed RDP Logins Source IP to full GeoData Conversion](https://github.com/joshmadakor1/Sentinel-Lab)
  - [JWipe (Disk Wiping Utility)](https://github.com/joshmadakor1/Jwipe.PowerShell)
  - [Active Directory Bulk User Creation](https://github.com/joshmadakor1/AD_PS)
  - [FIM (File Integrity Monitor)](https://github.com/joshmadakor1/PowerShell-Integrity-FIM)
- <b>C# (.NET Desktop Applications)</b>
  - [Ransomware Proof of Concept (Encrypter)](https://github.com/joshmadakor1/EncrypterPOC)
  - [Ransomware Proof of Concept (Decrypter)](https://github.com/joshmadakor1/DecrypterPOC)
  - [Keylogger with Email Capability](https://github.com/joshmadakor1/Key-Logger-With-Email)
- <b>Python</b>
  - [Package Delivery Application (Datastructures and Algorithms Demo)](https://github.com/joshmadakor1/Package-Delivery-Pathfinding-Algorithm)

<h2>📺 Popular YouTube Videos</h2>

- [How to get into Cybersecurity Starting From Zero](https://www.youtube.com/watch?v=a83ASGn_V_s)
- [A Day in the Life of a Cybersecurity Anayst](https://www.youtube.com/watch?v=uHy3oM7NnoU)
- [How to Create a KeyLogger (C#)](https://www.youtube.com/watch?v=N-L9hklSlNk)
- [Ransomware Demonstration (C#)](https://www.youtube.com/watch?v=OfvdQeh79s0)
- [Is WGU Legit?](https://www.youtube.com/watch?v=E2MwRWxDBkA)

<h2>Connect with me:</h2>
<img align="left" alt="Michael Chronicle | LinkedIn" width="22px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/linkedin.svg" />
<a href="https://www.linkedin.com/in/michael-chronicle/">LinkedIn Profile</a><br/>

<!--
**joshmadakor1/joshmadakor1** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

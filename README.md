# Honeynet-In-Azure
<br>
<img src="https://imgur.com/hbmU1lj.png"  height="60%" width="80%" alt="Disk Sanitization Steps"/>
</br>
<h1>Description</h1>
In this project, I created a mini honeynet in Azure by deploying Windows and Linux virtual machines with intentionally open firewall rules to attract attackers. To make the setup more appealing, I installed a vulnerable SQL Server on one of the VMs, encouraging brute force and SQL injection attempts. Logs from the VMs were collected in a Log Analytics workspace and connected to Microsoft Sentinel, where I built real-time attack maps and monitored threats. Over 24 hours, I observed security metrics in this insecure environment, applied controls to harden it, and measured the impact of those changes. This hands-on experience helped me better understand threat behavior, log management, and SIEM configuration.


<h2>Honeynet key Components</h2>
<br>
<img src="https://imgur.com/CDaTaLt.png"  height="50%" width="50%" alt="Disk Sanitization Steps"/>
</br>

- Azure Key Vault
- Azure Storage Account
- Log Analytics Workspace
- Microsoft Sentinel
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Virtual Network (VNet)
  
Prior , All the resources that were deployed was configured to be exposed to the internet in order to attract bad actors. I configured the Network Security Group on both Virtual Machines and created an inbound rule with low priority in order for the traffic to be evaluate first.


<h3>Conclusion</h3>
This project involved setting up a small honeynet in Microsoft Azure and connecting log sources to a Log Analytics workspace. Microsoft Sentinel was used to generate alerts and incidents from the logs. Metrics were recorded both before and after applying security controls. The results showed a significant drop in security events and incidents after implementing the controls, highlighting their effectiveness.

<h4></h4>
Also If the network resources were heavily used by more users, it’s likely that more security events and alerts would have been triggered within the 24 hours after the security controls were applied.

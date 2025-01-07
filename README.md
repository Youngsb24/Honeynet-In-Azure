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

**Before** applying any security measures, all the resources I deployed were intentionally exposed to the internet to attract bad actors. Both Virtual Machines had their Network Security Groups (NSGs) configured with an inbound rule that allowed all incoming traffic, meaning there were no restrictions in place. This made the VMs fully accessible to anyone on the internet, creating an easy target for brute-force attacks or other types of intrusion attempts. Additionally, the resources had public endpoints, leaving them completely open and vulnerable to malicious activity. The idea behind this was to create an environment where attackers could freely attempt to exploit the resources and attempt attacks.

**"AFTER"** phase, I implemented security controls to protect the environment. The Network Security Groups on the VMs were adjusted to block all traffic except from my admin workstation, restricting access to only trusted sources. Furthermore, the built-in firewalls for each VM and other resources were turned on, adding an extra layer of defense. Private endpoints were also configured to ensure that sensitive resources were no longer accessible via public IPs, making the environment more secure and harder to target. By comparing the "before" and "after" metrics, I could clearly see the difference in security posture and how effective these controls were in reducing exposure to potential attacks.



<h4>Conclusion</h4>
This project involved setting up a small honeynet in Microsoft Azure and connecting log sources to a Log Analytics workspace. Microsoft Sentinel was used to generate alerts and incidents from the logs. Metrics were recorded both before and after applying security controls. The results showed a significant drop in security events and incidents after implementing the controls, highlighting their effectiveness.

<h5></h5>
Also If the network resources were heavily used by more users, it’s likely that more security events and alerts would have been triggered within the 24 hours after the security controls were applied.

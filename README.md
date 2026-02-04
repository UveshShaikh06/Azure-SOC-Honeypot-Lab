 Azure SOC Honeypot & Attack Visualization Lab

  Overview
A hands-on security lab that simulates a real Security Operations Center (SOC) environment in Microsoft Azure. The project deploys a deliberately vulnerable Windows honeypot, uses Microsoft Sentinel (SIEM) to collect live attack logs, and visualizes global threat sources on a real-time attack map.

Key Skills Demonstrated: Microsoft Sentinel, KQL (Kusto Query Language), Azure Security, Log Analysis, SIEM Dashboard Creation, Threat Intelligence Enrichment.

  Lab Objectives
- To understand how unprotected systems are discovered and attacked on the internet.
- To gain hands-on experience with core Microsoft security tools: Azure, Log Analytics, and Sentinel.
- To practice the SOC workflow: log ingestion, querying, enrichment, and visualization.
- To create a tangible portfolio piece demonstrating cloud security and analytical skills.

  Architecture
![Architecture Diagram](/screenshots/architecture_diagram.png)

1.  Honeypot: A Windows 10 Virtual Machine in Azure with open RDP and disabled firewalls.
2.  Log Collection: Azure Log Analytics Workspace ingests Windows Security Events via the Azure Monitor Agent.
3.  SIEM & Analysis: Microsoft Sentinel queries the logs using KQL and enriches them with geolocation data.
4.  Visualization: A Sentinel Workbook displays a real-time world map of attack sources.

  Implementation Steps
1.  Provision Azure Resources: Created a Resource Group, Virtual Network, and Windows 10 VM.
2.  Configure Security (Insecure for Lab): Opened the Network Security Group (NSG) to all traffic and disabled the VM's Windows Firewall.
3.  Set Up Monitoring: Deployed a Log Analytics Workspace and Microsoft Sentinel.
4.  Forward Logs: Installed the Azure Monitor Agent on the VM to forward `SecurityEvent` logs (especially Event ID 4625 for failed logins).
5.  Analyze with KQL: Wrote KQL queries to filter, analyze, and enrich the attack data.
6.  Visualize Threats: Built a geospatial dashboard in Sentinel to map attack origins.

  Key Results & Screenshots
- Live Attack Data: Captured thousands of RDP brute-force attempts within hours of deployment.
- Threat Map: Visualized attackers from multiple continents, with hotspots in Europe and Asia.
  ![Sentinel Dashboard](/screenshots/attack_map.png)
- Query Analysis: Used KQL to isolate attack patterns and identify common usernames used by attackers.
  ![KQL Results](/screenshots/kql_query_results.png)

  Repository Contents
- `/sentinel` - Exported Sentinel Workbook JSON and sample watchlist.
- `/screenshots` - Visual proof of the deployed lab and outputs.

  Technologies Used
- Cloud: Microsoft Azure (Virtual Machines, Networking, Log Analytics)
- SIEM & Security: Microsoft Sentinel, Azure Monitor Agent
- Query Language: Kusto Query Language (KQL)
- Visualization: Sentinel Workbooks (Azure Maps integration)

  Notes & Disclaimer
- This lab uses intentionally insecure configurations (open RDP, disabled firewalls) for educational purposes only.
- All resources were deployed using a free Azure credit and were decommissioned after the lab to avoid costs.
- The geolocation data is for demonstration; accuracy depends on the IP-to-location database used.

  Author
- Uvesh Shaikh [LinkedIn](https://www.linkedin.com/in/uveshshaikh)

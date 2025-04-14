# Cyber-Security-Operations
Documentation of TheHive &amp; MISP Deployment

TheHive & MISP Deployment

Environment Setup
Virtual Machines Used:
•	Ubuntu Server VM – Hosts TheHive.
•	Kali Linux VM – Used for testing, analysis, and accessing TheHive’s web interface.
________________________________________
Installation Steps
1.	Install Java (Required by TheHive):
bash
CopyEdit
sudo apt install openjdk-11-jdk -y
2.	Install TheHive:
•	Download and install TheHive from the official repository.
•	Ensure all required dependencies are installed.
________________________________________
 Port Configuration
•	TheHive Web Interface: Port 9000
•	Firewall rules were configured to allow secure traffic between VMs on the necessary ports.
________________________________________
TheHive Setup and Configuration
•	TheHive was installed on the Ubuntu Server VM.
•	Based on internal policy, testing and analysis were done separately on the Kali VM to follow a segmented architecture.
•	Verified that TheHive UI is accessible from the Kali VM via a browser on port 9000.
•	Configured basic settings (users, organization, roles) to prepare the system for operational use.
________________________________________
VM Communication & Testing
•	Verified connectivity between the two VMs.
•	Confirmed TheHive service status and network accessibility.
•	Ensured firewall rules and IP-based communication paths were correctly configured.
________________________________________
MISP Integration (In Progress)
•	Initial groundwork has begun for integrating MISP with TheHive.
•	Future steps include:
o	Generating API keys in MISP.
o	Connecting MISP as a source for threat intelligence within TheHive.
o	Enabling module support for observable enrichment.
________________________________________
Setup Summary
Component	Host VM	Purpose/Status
TheHive	Ubuntu Server	Installed, configured, accessible via port 9000
Testing Access	Kali Linux	Used to access TheHive UI and validate functionality
MISP	(Planned Setup)	Pending integration for threat intelligence enrichment


Aligned Tasks and Their Relevance:
1. Setting Up Virtual Machines (Ubuntu + Kali)
•	Relevance: Provided isolated, controlled environments for hosting TheHive and performing analysis.
•	Alignment: Supports the project’s need for a secure, local, and modular testbed for incident response.
2. Installing and Configuring TheHive
•	Relevance: TheHive is the central platform for managing and analyzing security incidents.
•	Alignment: Core task aligned directly with the objective of deploying a functioning incident response system.
3. Configuring Network and Firewall Rules
•	Relevance: Ensures communication between VMs and access to TheHive's interface.
•	Alignment: Reflects real-world SOC practices and supports smooth operational connectivity.
4. Documenting Installation and Configuration Steps
•	Relevance: Enhances repeatability, simplifies troubleshooting, and ensures knowledge transfer.
•	Alignment: Supports project sustainability, scalability, and potential handover to other teams.
5. Preparing for MISP Integration
•	Relevance: MISP will enhance TheHive’s functionality by providing threat intelligence and enrichment.
•	Alignment: Reflects a phased deployment strategy that prioritizes stability and prepares for future capability expansion.
Notes:
•	All terminal commands, configuration settings, and port rules were recorded for future replication and troubleshooting.
•	Architecture decisions were made to support modularity, security, and scalability.
•	The environment is now ready for integrating MISP to enhance threat intelligence capabilities.




lessons learned from deployment documentation.

1. Performance, security, and troubleshooting are enhanced when TheHive and associated services are installed on different virtual machines.

This division reduces the possibility of cross-service conflicts and promotes best practices in system architecture.

2. Reliance Being Aware Is Essential
TheHive makes extensive use of services like Elasticsearch and Java.

Compatibility problems and runtime errors can be avoided by making sure the versions and installation order are right.

3. Comprehensive Confirmation Avoids Downtime
Services were operating correctly, as demonstrated by the use of straightforward commands like curl and systemd service status checks.

Early port verification (9200 for Elasticsearch, 9000 for TheHive) aided in the effective troubleshooting of network and firewall problems.

4. Port management and firewalls are crucial.
For smooth communication, it was essential to configure firewall rules and open the appropriate ports between virtual machines.

By recording these values, future situations can avoid frequent configuration errors.

5. Documentation Makes Things More Repeatable
Maintaining a record of each installation command, configuration file, and system modification enables the setup to be replicated and transferred to different groups or settings.

Effective documentation facilitates disaster recovery and cuts down on the amount of time new team members must spend onboarding.

6. Scalability is Prepared by Modular Deployment
Planning ahead for MISP integration while beginning with just TheHive and Elasticsearch shows a scalable and phased deployment approach.

Because each component is added progressively, this lowers the initial complexity and facilitates debugging.

7. Practical Understanding is Developed by Hands-on Deployment
Understanding how TheHive functions in actual settings was enhanced by going through every stage of the setup, from virtual machine configuration to software installation.

learned about integration procedures, security factors, and dependencies that are pertinent to actual SOC operations.

Workflow: TheHive + MISP Deployment

             ┌─────────────────────┐
             │     Analyst VM      │
             │     (Kali Linux)    │
             │  - Web browser      │
             │  - API testing      │
             └────────┬────────────┘
                      │
                      ▼
             ┌─────────────────────┐
             │     TheHive VM      │
             │    (Ubuntu Server)  │
             │ - Web Interface     │
             │ - Incident Response │
             └────────┬────────────┘
                      │
                      ▼ (Planned Integration)
             ┌─────────────────────┐

              │        MISP         │






Knowledge, Skills, and Abilities (KSAs) Acquired
Knowledge Gained
1.	Understanding of Incident Response Systems
o	Gained in-depth knowledge of how TheHive functions as an open-source incident response platform.
o	Learned the purpose and workflow of case creation, task assignments, and incident tracking.
2.	Knowledge of Network Configuration & Security
o	Understood how firewall rules, ports, and IP-based configurations enable secure communication between systems.
3.	Deployment Architecture Planning
o	Learned the benefits and rationale behind separating services across virtual machines for modularity and security.
4.	Threat Intelligence Integration Concepts
o	Developed foundational understanding of MISP’s role in providing threat data for enrichment and correlation.
________________________________________
Skills Developed
1.	Virtual Machine Setup and Management
o	Installed, configured, and managed Ubuntu and Kali Linux virtual machines for a testbed environment.
2.	TheHive Installation and Configuration
o	Carried out full deployment and initial configuration of TheHive, including UI access and system tuning.
3.	Command Line Proficiency
o	Used Linux CLI effectively for installing packages, starting services, managing ports, and performing connectivity tests.
4.	System Troubleshooting
o	Diagnosed and resolved common setup issues, including service failures and firewall misconfigurations.
5.	Technical Documentation
o	Recorded all steps clearly and methodically to produce repeatable, understandable setup documentation.
________________________________________
Abilities Acquired
1.	Ability to Design a Secure Deployment Environment
o	Confident in planning and executing segmented deployments to reduce risk and increase clarity in system roles.
2.	Ability to Work Independently and Collaboratively
o	Took ownership of specific deployment tasks while aligning efforts with broader team objectives.
3.	Ability to Think Ahead and Plan for Integration
o	Set up systems in a way that anticipates future integration with tools like MISP, showing forward-thinking and adaptability.
4.	Ability to Translate Technical Work into Project Deliverables
o	Converted practical tasks into professional documentation and insights that align with the project’s goals.


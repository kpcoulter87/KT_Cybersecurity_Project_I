# ELK_Project
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

[ELK Stack Deployment Network Diagram] (https://github.com/kpcoulter87/KT_Cybersecurity_Project_I/blob/main/Diagrams/ELK%20VM.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to recreate the entire deployment pictured above. Select portions of the Ansible file may be used to install only certain pieces of it, such as Filebeat.

[ELK Stack Deployment Ansible Playbook] (https://github.com/kpcoulter87/KT_Cybersecurity_Project_I/blob/main/Ansible/elk-playbook)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly flexible, in addition to restricting access to the network. This protects the machines on the network while also ensuring if one goes down or gets overloaded with requests, another server is capable of fulfilling those requests. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system metrics from the operating system and from services running on the server.

The configuration details of each machine may be found below.


| Name 	   | Function | IP Address | Operating System |
|----------|----------|----------  |------------------|
| Jump Box | Gateway  | 10.0.0.4   |   Linux        	|
| Web-1	   |   VM     | 10.0.0.5   |   Linux          |
| Web-2	   |   VM     | 10.0.0.6   |   Linux          |
| Web-3	   |   VM     | 10.0.0.7   |   Linux          |
| elk-vm	 |   ELK    | 10.1.0.4   |   Linux          |

### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
72.94.151.52 (personal IP)

Machines within the network can only be accessed by the Jump Box gateway 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses        |
|----------|---------------------|-----------------------------|
| Jump Box | Yes (SSH)           | (personal IP)                 |
| Web-1    | NO                  | 10.0.0.4|
| Web-2    | NO                  | 10.0.0.4|
| Web-3    | NO                  | 10.0.0.4,|
| ELK      | YES(HTTP)           | (personal IP), 10.0.0.4       |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually. This is advantageous because it is simplifies network management, it reduces errors, it optimizes performance, and reduces risk of vulnerabilities due to human error.  

The playbook implements the following tasks:
- Increases memory to enable machine to run docker elk container
- Installs Docker.io
- Installs python3.pip
- Installs Docker Python package
- Downloads and launches a Docker ELK container 
- Enable Docker service on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web1- 10.0.0.5
Web2- 10.0.0.6
Web3- 10.0.0.7

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat: This collects and monitors log data from each machine and collects log events
  -ex. 
-Metricbeat: This collects metrics from the operating system and from services running on the server. 
  -ex. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the host file to include the IP address of the new Virtual Machine
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? KT_Cybersecurity_Project_I/Ansible/elk-playbook Where do you copy it? Copy it to 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc.
Download playbook: ansible-playbook <playbook_name>

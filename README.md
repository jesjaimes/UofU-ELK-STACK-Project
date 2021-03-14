# UofU-ELK-STACK-Project
Project-1 
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1GpMdzp6rgMHqOgr02XkX6iQreD9sUuKc/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the (Project_1/Ansible/filebeat/filebeatplaybook.txt) file may be used to install only certain pieces of it, such as Filebeat.

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build 

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly resiliant, in addition to restricting acces to the network.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system metrics.

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web1     |   VM     | 10.0.0.5   | Linux            |
| Web2     |   VM     | 10.0.0.6   | Linux            |
| Web3     |   VM     | 10.0.0.7   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 199.30.186.21

Machines within the network can only be accessed by Jumpbox.
Jumpbox IP: 13.66.251.7

A summary of the access policies in place can be found in the table below.

| Name    | Publicly accessible | Allowed IP Addresses |
|---------|---------------------|----------------------|
| Jumpbox | Yes                 | 199.30.186.21        |
| Web1    | No                  | 10.0.0.4             |
| Web2    | No                  | 10.0.0.4             |
| Web2    | NO                  | 10.0.0.4             |
| ELKVM   | Yes                 | 10.1.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it does not require agent installation. Ansible allows us to roll out simple tasks like, reboots, or trigger updates across many machines.

The playbook implements the following tasks:
- The playbook implements the following tasks: 
- 1- The playbook begins by installing Docker. This will allow us to begin creating containers. 
- 2- Next we will begin the installation of pip. This will manage software packages written in Python. 
- 3- We will then begin to download and launch a docker Elk container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

DockerPS.jpg.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web1 10.0.0.5
  Web2 10.0.0.6
  Web3 10.0.0.7
  
We have installed the following Beats on these machines:
-Filebeat
-Metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat will allow us to monitor log files or locations we decide to watch. 
-More importantly it will collect these log events and send them to Elasticsearch or Logstash for analysis.
-Metricbeat will show us the metrics and statistics of our servers. This will send this data to Elasticsearch or Logstash for further analysis.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

Copy the file to /etc/ansible/.
Update the Ansible Host file to specify which machine you wish to run your playbooks. Create groups in the host file by using [your group here]. After making your group assign your ip address to the group or groups.
Run the playbook, and navigate to http//52.179.213.172:5601:/app/Kibana to check that the installation worked as expected.


_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

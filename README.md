## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![diagram](https://github.com/Jeffror/JeffRorvig/Diagrams/Jrorvig_Cloud_ network_drawing.png "Azure Machines Network")

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the Beat.YML file may be used to install only certain pieces of it, such as Filebeat.

[Ansible Files](https://github.com/Jeffror/JeffRorvig/tree/main/Ansible)
  
  
This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly Redundent, in addition to restricting access to the network.
- The Load Balancer monitors the load and distributes it evenly, if a machine goes down the Load Balancer will route traffic to the working machine.
- Using a Jump Box allows users to connect via the Remote Desktop Protocol (RDP) or Secure Shell (SSH)

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the File Structure and system Files.
- Filebeat monitors the log files or locations that the user selects, collects log events, and forwards them either to Elasticsearch or Logstash for indexing
- Metricbeat monitors your servers by collecting metrics and statistics from the system and services running on the server, and then sends them to the output that you specify, such as Elasticsearch or Logstash. 

The configuration details of each machine may be found below.

| Name     | Function | IP Address | Operating System |
|:--------:|:--------:|:----------:|:----------------:|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web 1    | Gateway  | 10.0.0.5   | Linux            |
| Web 2    | Gateway  | 10.0.0.6   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 
- 98.165.70.102

Machines within the network can only be accessed by using an SSH.Key.
- The Jump Box is able to access the Elk Machine using the IP Address 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|:--------:|:-------------------:|:--------------------:|
| Jump Box |     No              | 98.165.70.102        |
| Web 1    |     No              | 10.0.0.4             |
| Web 2    |     No              | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Installs steps in order, is easily repeatable, notifies you if a step fails.

The playbook implements the following tasks:
- Pulls the application from the web
- Downloads the content
- Installs the content to the file structure

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1 with an IP Address of 10.0.1.05
- Web 2 with an IP Address of 10.0.1.06

We have installed the following Beats on these machines:
- Filebeat and Metricbeat

These Beats allow us to collect the following information from each machine:
- **Filebeat** helps generate and organize log files to send to LogStash and Elasticsearch. Specifically, it logs information about the file system, including files which have changed and when. Filebeat is often used to collect log files from very specific files, such as those generated by Apache, Microsoft Azure tools, the Nginx web server,and MySQL databases.  **Activity Logs** will retrieve azure activity logs. Control-plane events on Azure Resource Manager resources. Activity logs provide insight into the operations that were performed on resources in your subscription. 
- **Metricbeat** consists of modules and metricsets. A Metricbeat module defines the basic logic for collecting data from a specific service, such as Redis, MySQL, and so on. The module specifies details about the service, including how to connect, how often to collect metrics, and which metrics to collect. **Apache** The Apache status metricset collects data from the Apache mod_status module. It scrapes the server status data from the web page generated by mod_status.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_**Finish**
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

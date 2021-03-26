# ELK-Project
Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __yml___ file may be used to install only certain pieces of it, such as Filebeat.
filebeat-playbook.yml: Enter the playbook file.
This document contains the following details:
Description of the Topology
Access Policies
ELK Configuration
Beats in Use
Machines Being Monitored
How to Use the Ansible Build
Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly efficient, in addition to restricting traffic to the network.
It protects availability. Jump-Box provides secure access to web servers .: What aspect of security do load balancers protect? What is the advantage of a jump box?
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data  and system logs.
Filebeat is for forwarding and centralizing log data, it monitors log files or specified locations: What does Filebeat watch for?
Metricbeat helps you monitor your servers by collections metrics from the system and services running on the server: What does Metricbeat record?
The configuration details of each machine may be found below. Note: Use the Markdown Table Generator to add/remove values from the table.
Name
Function
IP Address
Operating System
Jump Box
Gateway
10.0.0.1
Linux
Web1
Web server
10.0.0.6
Linux
Web2
Web server
10.0.0.5
Linux
Elk server
Elk stack
10.1.0.4
Linux

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump-box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
My Ip 172.103.68.175.: Add whitelisted IP addresses
Machines within the network can only be accessed by the jumpbox.
Jump-box 40.76.44.113: Which machine did you allow to access your ELK VM? What was its IP address?
A summary of the access policies in place can be found in the table below.
Name
Publicly Accessible
Allowed IP Addresses
Jump Box
Yes/No
10.0.0.1 10.0.0.2
Jump-Box
No
172.103.68.175







Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
It allows us to run commands on several machines automatically instead of doing them one by one on each machine: What is the main advantage of automating configuration with Ansible?
The playbook implements the following tasks:
TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc.
Install docker
Create and start container
Install required program using ansible playbook
Install filebeat and metricbeat
Open kibana to upload data
The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

Target Machines & Beats
This ELK server is configured to monitor the following machines:
Web1 10.0.0.6
Web2 10.0.0.5: List the IP addresses of the machines you are monitoring
We have installed the following Beats on these machines:
Filebeat and Mtericbeat: Specify which Beats you successfully installed
These Beats allow us to collect the following information from each machine:
Filebeat- collets system logs. E.g. error codes, file type scatter
Metricbeat- monitors server. E.g. cpu usage and network traffic
 In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.
Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:
Copy the __public key___ file to __VM password___.
Update the ____hosts_ file to include… webserver IPs and Elk server IPs
Run the playbook, and navigate to __Kibana__ to check that the installation worked as expected.
TODO: Answer the following questions to fill in the blanks:
Which file is the playbook? Where do you copy it?
Docker.yml
ELK.yml
Filebeat-playbook.yml
mtericbeat-playbook.yml
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
You can change machine in the config files
_Which URL do you navigate to in order to check that the ELK server is running?
http://ELK serverip/app/kibana

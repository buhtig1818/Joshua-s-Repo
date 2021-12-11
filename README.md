## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://drive.google.com/file/d/1iQNK_R7tKcRTRzPGQ5NUcNWWP-aG3tng/view?usp=sharing

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _YML_ file may be used to install only certain pieces of it, such as Filebeat.

# Joshua-s-Repo
Ansible and Linux scripts for my class

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
 Load balancers work on the Availability aspect of security. By using Jumpbox paired with ansible the creation of the settings for each VM and YML files can be automated. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the metric and system files.
Filebeat logs file access and modifications
Metricbeat logs the RAM/CPU usage

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  |   |     40.83.55.31 10.0.0.6      |Linux  |
| Web 1         | DVWA Server         |10.0.0.4            |   Linux               |
| Web 2     | DVWA Server         |10.0.0.5          |    Linux              |
| ELk          |  Elk Server          |23.100.47.91              | Linux|

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JUMPBOX machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
Whitelisted IP address 71.231.185.246

Machines within the network can only be accessed by the Jumpbox.
- 40.83.55.31


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes              | 71.231.185.246    |
|    Web 1   |  No   |        |   None  |
|     Web 2 | No  | None   |
|     ELK  |     Yes   | 71.231.185.246 |

### Elk Configuration 

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because the process is sped up and  human error risks are eliminated.


The playbook implements the following tasks:
- Use apt module install docker.io
- Install pip3
- Use pip module Install Docker python module
- Use sysctl mdoule Use more memory
- Use docker_container module download and launch a docker elk container
- Use systemd module Enable service docker on boot

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

https://drive.google.com/file/d/1ilZgep6f7g0K_U2ngeBZT0csUhnS0hns/view?usp=sharing

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
10.0.0.5/10.0.0.4

We have installed the following Beats on these machines:
File Beat and Metric Beat

These Beats allow us to collect the following information from each machine:
File beat collects and sends log data. An example of what I might see would be file beat centralizing and shipping log data for indexing to Elastisearch.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the  file to pentest 2.yml.
- Update the Hosts file to include Elk Server
- Run the playbook, and navigate to _http://13.64.182.99:5601/app/kibana#/home to check that the installation worked as expected.



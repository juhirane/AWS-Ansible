## MCAFEE VIRUS SCAN ENTERPRISE INSTALLATION

Intial Draft version v1.0

### Requirements
- Requires Ansible 2.4.0 or newer
- Winrm for windows and Linux machine connectivity
- ssh connection required


This repository includes the following files and directories:
  - `roles` directory
  - win_software_install.yml 
  - VSE880EMLRP7     "setup file of virus scan"
  - inventory
  - README.md


In the inventory file `inventory`, mention the ip address of the server , where the task has to be perfomed and even provide the username, password and other paramters.

Kindly Check the `inventory` inventory file example below

[windows] \
192.168.1.**  `mention the ip address of the servers`  

[windows:vars] \
ansible_ssh_user=`provide username` \
ansible_ssh_pass=`provide password`   \
ansible_ssh_port=5986   `port name`\
ansible_connection=winrm       `connection state`\
host_key_checking=false

The  win_software_install.yml is used  to install the mcafee virus scan enterprise edition.To use, edit the `inventory` file to include the names or IP address of the servers you want to deploy.

Run the playbook, like this:

	ansible-playbook -i inventory  win_software_install.yml

The playbook will call the role that is situated inside the `roles` directory and will do the following steps:

- Install the mcafee virus scan enterprise edition.

The Detailed Document is available in the share point.

URL= https://sp2013.myatos.net/si/coe/development/COE%20Dev%20Cloud/cloudification/_layouts/15/WopiFrame.aspx?sourcedoc=/si/coe/development/COE%20Dev%20Cloud/cloudification/Decision%20Factory/3.%20Ansible%20Automation/IDM/Arlington_Umar_Documents/win_mcafee_install.docx&action=default

## Authors

* **Ajish Chovallur** - *Initial work*
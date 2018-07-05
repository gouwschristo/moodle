# Ansible deployment for Moodle

[![N|Solid](https://moodle.org/theme/image.php/moodleorgcleaned_moodleorg/theme_moodleorgcleaned/1529516985/moodle-logo)](https://moodle.org)

# Configuration options
All tunable parameters resides in the **host_vars/moodle** file.

  - **install_dir:** Is the location where moodle files will be installed & used as your root directory for Nginx webserver.
  - **www_root:** This is the URL that the site will respond on, it may be a DNS resolveable name or IP address prefixed with "http://"
  - **data_dir:** The is the location where moodle will store its data files.
  - **db_name:** The moodle database name.
  - **db_user:** The user account to be created for access to the database mentioned above.
  - **db_password:** The password to be set for access to the database mentioned above.
  - **admin_user:** The default administrative login name for web-console.
  - **admin_password:**  The default administrative login password for web-console.
  - **admin_email:** "admin@domain.com" The default administrative email details for web-console.
  - **site_fullname:** This is the full title of the site.
  - **site_shortname:** This is a short name title for the site.

### Installation

This playbook will install the Moodle framework on a Ubuntu 16.04 LTS server. 

Install Ansible on your local workstation using the following commandsL

**Ubuntu**
```sh
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository ppa:ansible/ansible
$ sudo apt-get update
$ sudo apt-get install ansible
```

** Redhat/CentOS**
```sh
# install the epel-release RPM if needed on CentOS or RHEL
$ sudo yum install ansible
```

Clone the this repository to your workstation and update the hosts file with your server's IP address
and the host_vars/moodle file with your desired configuration.
Ater making your change you are ready to boostrap the environment.

```sh
$ git clone https://github.com/gouwschristo/moodle
$ cd moodle
# Make you desire configuration changes
# Boostrap the environment, using your SSH key.
$ ansible-playbook --private-key ~/.ssh/aws -i ./hosts ./main.yml
```
Once complete you will be able to access the website on the IP address/DNS name that you have specified.

### Supported Platform

Deployment has been tested on the following environment.

| Application | Version |
| ------ | ------ |
| Ubuntu | 16.04 |
| Nginx | 1.4 |
| PHP | 7.0 |
| MariaDB | 10.0 |
| Moodle | 3.5 |
| Ansible | 2.5.3 |


